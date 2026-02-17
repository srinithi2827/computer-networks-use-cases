import java.io.*;
import java.net.*;

public class SimpleHttpClient {

    public static void main(String[] args) {
        String host = "example.com";   // Server name
        int port = 80;                 // HTTP default port
        String path = "/";             // Web page path

        try (Socket socket = new Socket(host, port)) {

            // Send HTTP request
            PrintWriter out = new PrintWriter(socket.getOutputStream(), true);
            out.println("GET " + path + " HTTP/1.1");
            out.println("Host: " + host);
            out.println("Connection: close");
            out.println();  // blank line ends request

            // Read HTTP response
            BufferedReader in = new BufferedReader(
                    new InputStreamReader(socket.getInputStream())
            );

            String line;
            while ((line = in.readLine()) != null) {
                System.out.println(line);
            }

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
