# Lab_6
import java.io.*;
//Переписать в результирующий файл слова с четным числом букв.
public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = null;
        BufferedWriter bw = null;
        try {
            br = new BufferedReader(
                    new InputStreamReader(
                            new FileInputStream("C:\\Users\\Student\\Desktop\\НВВ\\АиП\\файлы\\MyFile1.txt"), "cp1251"));
            bw = new BufferedWriter(
                    new OutputStreamWriter(
                            new FileOutputStream("C:\\Users\\Student\\Desktop\\НВВ\\АиП\\файлы\\MyFile2.txt"), "cp1251"));

            int lineCount = 0;
            String s;
            String [] words;
            while ((s = br.readLine()) != null) {
                lineCount++;
                System.out.print(lineCount + ": " );
                words = s.split(" ");
                for (int i = 0; i < words.length; i++) {
                    if(words[i].length()%2==0){
                        bw.write(words[i]);
                        System.out.print(words[i] + " ");
                    }
                }
                System.out.println();
               // bw.write(lineCount + ": " + s);
                bw.newLine();
            }
        }
        catch (IOException e) {
            System.out.println("Ошибка !!!!!!!!");
        }
        finally {
            br.close();
            bw.flush();
            bw.close();
        }
    }
}
