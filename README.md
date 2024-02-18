# practice-musicid

A game to practice identifying music.
I mainly just made this for myself,
but perhaps someone else finds it neat too.

## Setup

Create a directory `practice-musicid` in your `~/.config` directory
(or `$XDG_CONFIG_HOME` if you customize it).
In it, create a subdirectory for some group of music you want to practice on.
Inside that subdirectory, create symlinks to audio files of the music you want to use.
The names of the symlinks will be used as short names for each music file,
and you’ll have to enter these short names later,
so you probably want to make them concise and succinct.

In `~/.config/practice-musicid`, symlink `default` to the subdirectory you just created and populated.
(You can also have more than one subdirectory and switch the `default` symlink between them if you like.)

For example, I have:

```sh
$ tree ~/.config/practice-musicid/
/home/lucas/.config/practice-musicid/
├── default -> piano-concertos
├── piano-concertos
│   ├── rach2-1 -> /home/lucas/Music/Sergei Rachmaninoff, Pyotr Ilyich Tchaikovsky; Sviatoslav Richter, Stanisław Wisłocki, Herbert von Karajan/Rachmaninov: Piano Concerto no. 2 - Tchaikovsky: Piano Concerto no. 1/Disc 1 - 01 - Piano Concerto no. 2 in C minor, op. 18: I. Moderato.flac
│   ├── rach2-2 -> /home/lucas/Music/Sergei Rachmaninoff, Pyotr Ilyich Tchaikovsky; Sviatoslav Richter, Stanisław Wisłocki, Herbert von Karajan/Rachmaninov: Piano Concerto no. 2 - Tchaikovsky: Piano Concerto no. 1/Disc 1 - 02 - Piano Concerto no. 2 in C minor, op. 18: II. Adagio sostenuto.flac
│   ├── rach2-3 -> /home/lucas/Music/Sergei Rachmaninoff, Pyotr Ilyich Tchaikovsky; Sviatoslav Richter, Stanisław Wisłocki, Herbert von Karajan/Rachmaninov: Piano Concerto no. 2 - Tchaikovsky: Piano Concerto no. 1/Disc 1 - 03 - Piano Concerto no. 2 in C minor, op. 18: III. Allegro scherzando.flac
│   ├── tchaik1-1 -> /home/lucas/Music/Sergei Rachmaninoff, Pyotr Ilyich Tchaikovsky; Sviatoslav Richter, Stanisław Wisłocki, Herbert von Karajan/Rachmaninov: Piano Concerto no. 2 - Tchaikovsky: Piano Concerto no. 1/Disc 1 - 04 - Piano Concerto no. 1 in B-flat minor, op. 23: I. Allegro non troppo e molto maestoso – Allegro con spirito.flac
│   ├── tchaik1-2 -> /home/lucas/Music/Sergei Rachmaninoff, Pyotr Ilyich Tchaikovsky; Sviatoslav Richter, Stanisław Wisłocki, Herbert von Karajan/Rachmaninov: Piano Concerto no. 2 - Tchaikovsky: Piano Concerto no. 1/Disc 1 - 05 - Piano Concerto no. 1 in B-flat minor, op. 23: II. Andantino semplice – Prestissimo – Tempo I.flac
│   └── tchaik1-3 -> /home/lucas/Music/Sergei Rachmaninoff, Pyotr Ilyich Tchaikovsky; Sviatoslav Richter, Stanisław Wisłocki, Herbert von Karajan/Rachmaninov: Piano Concerto no. 2 - Tchaikovsky: Piano Concerto no. 1/Disc 1 - 06 - Piano Concerto no. 1 in B-flat minor, op. 23: III. Allegro con fuoco.flac
└── star-wars-opening
    ├── ep1 -> /home/lucas/Music/London Symphony Orchestra/Star Wars Episode I- The Phantom Menace [Original Motion Picture Soundtrack] [The Ultim Disc 1/02 Treachery within the Federation - The Invasion of Naboo. Star Wars main.wma
    ├── ep2 -> /home/lucas/Music/London Symphony Orchestra/Star Wars Episode II- Attack of the Clones [Original Motion Picture Soundtrack]/01 Main Title - Ambush on Coruscant.mp3
    ├── ep3 -> /home/lucas/Music/London Symphony Orchestra/Star Wars- Episode III – Revenge Of The Sith/01 Star Wars And Revenge Of The Sith.mp3
    ├── ep4 -> /home/lucas/Music/London Symphony Orchestra/Star Wars- Episode IV – A New Hope/02 Main Title-Rebel Blockade Runner.mp3
    ├── ep5 -> /home/lucas/Music/London Symphony Orchestra/Star Wars- Episode V – The Empire Strikes Back/02 Main Title-The Ice Planet Hoth.mp3
    ├── ep6 -> /home/lucas/Music/London Symphony Orchestra/Star Wars- Episode VI – Return Of The Jedi/02 Main Title-Approaching The Death Star-Tatooine Rendezvous.mp3
    ├── ep7 -> /home/lucas/Music/John Williams/Star Wars_ The Force Awakens_ Original Motion Picture Soundtrack/01. Main Title and the Attack on the Jakku Village.flac
    ├── ep8 -> /home/lucas/Music/John Williams/Star Wars: The Last Jedi/Disc 1 - 01 - Main Title and Escape.flac
    └── ep9 -> /home/lucas/Music/John Williams/Star Wars: The Rise of Skywalker/Disc 1 - 01 - Fanfare and Prologue.flac

4 directories, 15 files
```

Of course, on your system the paths will be very different.
(You can see that I imported these albums at different times using different programs with different settings and the paths are in no way regular.)

## Play

Run `./practice-musicid`.
If you want to use a subdirectory other than the one you symlinked `default` to,
pass its name as an argument, e.g. `./practice-musicid star-wars-opening`.

The game will show you the short names of all the music files,
then pick a random one and start playing it at a random position.
Your task is to identify which one it picked, and enter its short name.
If you identified it correctly, the game starts again with a new file.
If you identified it incorrectly, the game will tell you what it actually was,
and then play it again from the same position so you can remember it.

If you want to always listen to the music files from the beginning,
pass the `-n` option (or `--no-random-start`),
e.g. `./practice-musicid -n star-wars-opening`.

## License

[Blue Oak Model License 1.0.0](./LICENSE.md).
