# Part 1:

## Code for ChatServer:

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String str = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format(str);
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    if (parameters[1].contains("user")) {
                        if (parameters[1].contains("&")) {
                            String[] middleString = parameters[1].split("&");
                            str += "\n" + parameters[2] + ": " + middleString[0];
                            return String.format(str);
                        }
                        return "No & symbol to separate s and user";
                    }
                    return "No user defined";

                }
                return "No String defined";
            }
            return "404 Not Found!";
        }
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```

#
