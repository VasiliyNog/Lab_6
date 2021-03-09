# Lab_6
public class InConvertInText {
 public static void readAllByByte( Reader in) throws IOException {
  while (true) {
  int oneByte = in.read(); // читает 1 байт
  if (oneByte != -1) { // признак конца файла
  System.out.print((char) oneByte);
  } else {
   System.out.print("\n" + " конец ");
   break;
  }
 }
} 
public static void main(String[] args) {
 try {
  br = new BufferedReader( new FileReader("E:\\MyFile1.txt" ), 1024);
  out = new BufferedWriter( new FileWriter( "E:\\MyFile2.txt" ));
  int lineCount = 0; 
  String s;
  while ((s = br.readLine()) != null) {
  lineCount++;
  System.out.println(lineCount + ": " + s);
  out.write(s);
  out.newLine(); 
  InputStream inArray = new ByteArrayInputStream( new byte[] {5, 8, 3, 9, 11});
  Reader rArray=new InputStreamReader(inArray,"cp1251" );
  readAllByByte(rArray);
  System.out.print("\n\n\n");
  inArray.close();
  rArray.close();
 } catch (IOException e) {
 System.out.println("Ошибка: "+ e);
 }
}
