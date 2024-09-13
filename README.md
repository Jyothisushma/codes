#Songs Playlist
# Songs Playlist program using Java Program

As an illustration, if a user were to play four distinct songs and the initial capacity was three:
Assume that the user has listened to S1, S2, and S3 tracks.
This is how the playlist would appear: S1, S2, S3

● S2,S3,S4 when the S4 song is performed

● S3,S4,S2 when S2 music is played

## Acknowledgements

 - [ArrayList in Java](https://www.javatpoint.com/java-arraylist)
 - [Java List](https://www.javatpoint.com/java-list)
 - [How to run a Java Program in eclipse](https://www.javatpoint.com/how-to-run-java-program-in-eclipse)


## API Reference

#### Get all items

```http
  GET /api/java.util
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| java.util | `string` | Contains the collections framework, legacy collection classes, event model, date and time facilities, internationalization, and miscellaneous utility classes (a string tokenizer, a random-number generator, and a bit array).


```http
  GET /api/items/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `song`      | `string` | s1 s2 s3 |
| `capacity`      | `int` | 3 |

#### add song(S1, S2, S3)
     capacity less then 3 songs

Song PlayList with a capacity of 3.


## Appendix

Any additional information goes here


## Installation

Steps to install Java on a Windows computer:

Download Java:
Visit the official Java download page.
Click on the download link for the latest version of Java.
Run the Installer:
Once the download is complete, locate the downloaded file (usually in your Downloads folder) and double-click it to run the installer.
If prompted by User Account Control, click “Yes” to allow the installer to make changes to your device.
Install Java:
In the Java Setup window, click the “Install” button to start the installation process.
The installer will guide you through the installation steps. Follow the on-screen instructions.
Complete Installation:
Once the installation is complete, you will see a confirmation message. Click “Close” to finish the installation.
Verify Installation:
Open a command prompt (you can search for “cmd” in the Start menu).
Type java -version and press Enter. You should see the version of Java that you installed.

    
## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

Control Panel > System > Advanced system settings > Advanced > Environment Variables

JAVA_HOME = C:\Program Files\Java\jdk-19
PATH = PATH + C:\Program Files\Java\jdk1-19\bin

%JAVA_HOME%\bin


## Code
import java.util.ArrayList;
import java.util.List;

public class SongPlaylist {
    private String name;
    private int capacity ;
    private List<String> songs;

    public SongPlaylist(String name, int capacity) {
        this.name = name;
        this.capacity = capacity;
        this.songs = new ArrayList<>();
    }

    public void addSong(String song) {
        if (songs.size() < capacity) {
            songs.add(song);
        } else {
            songs.remove(0);
            songs.add(song);
        }
    }

    public void playSong(String song) {
        if (songs.contains(song)) {
            int index = songs.indexOf(song);
            songs.remove(index);
            songs.add(song);
        }
    }

    public void displayPlaylist() {
        System.out.println("Playlist: " + name);
        for (String song : songs) {
            System.out.println(song);
        }
    }

    public static void main(String[] args) {
        SongPlaylist playlist = new SongPlaylist("My Playlist", 3);

        playlist.addSong("S1");
        playlist.addSong("S2");
        playlist.addSong("S3");
        playlist.displayPlaylist();

        playlist.addSong("S4");
        playlist.displayPlaylist();

        playlist.playSong("S2");
        playlist.displayPlaylist();

        playlist.playSong("S1");
        playlist.displayPlaylist();
    }
}


## Running Tests

To run tests, run the following command

```in the cmd > navigate to the path where java file is saved

  javac SongPlaylist.java
  java  SongPlaylist
```


## Authors

- [java](https://www.java.com/en/)
- [eclipse](https://www.eclipse.org/)

