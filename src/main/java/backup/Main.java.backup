package org.example;

import java.io.File;
import java.io.IOException;
import java.nio.file.*;

public class Main {
    public static void main(String[] args) {

        backup(getFileInFolder("src/main/java/org/example/"));

    }

    public static void backup(File[] files){

        try {
        for (File file : getFileInFolder("src/main/java/backup/")){

            file.delete();
        }
        for (File file : files){
            Path sourcePath = Paths.get("src/main/java/org/example/"+file.getName());
            Path destPath = Paths.get("src/main/java/backup/"+file.getName()+".backup");
            Files.copy(sourcePath, destPath, StandardCopyOption.REPLACE_EXISTING);
        }

            System.out.println("File is copied successful!");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }


    public static File[] getFileInFolder(String path){
        File folder = new File(path);
        File[] files = folder.listFiles();
       return files;
    }
}