# Part 1:

## Code for ChatServer:

```java
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The String value that will be added upon through
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
                        return "No '&' symbol to separate s and user";
                    }
                    return "No user defined";

                }
                return "No string defined";
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

## Screenshots of adding messages:

![Image](Screenshot2024-01-28155734.png)

The `handleRequest` method from the `Handler` class is called when the URL is input. There are many layers of arguments for the request, but first `str` is initialized to an empty `string`. The first layer checks if `\add-message` is a valid argument. After that we check if an `s` is contained right after that. Then we check if `user` and `&` are located in the appropriate places. Any failure of these checks results in an error message being printed out. Only after all the arguments have been verified, the field `str` adds on to itself the `<user>: <s>`. And it prints. No other fields or values like `url` is altered, only `str` changes by adding onto itself the new proper message: `<user>: <s>`. 


![Image](Screenshot2024-01-28161853.png)

The same applies here. `handleRequest` is called and and field `str` still contains the previous value of `BobJefferson: Howareyou`. So it will remain there until the server gets taken down or restarts. Arguments for `\add-message` gets checked, then `s` and `user` and `&`. `user` is assigned to the value of `Avril Gold` and `s` is assigned to the value `I am good`. After all relevant checks are verified, field `str` adds a line break `\n` before adding the `<user>: <s>` part. No other fields or values like `url` is altered. However in this case, field `str` now contains `BobJefferson: Howareyou\n Avril Gold: I am good`.

# Part 2:

## Aboslute path to the private key for my ssh key on my PC:

![Image](Screenshot2024-02-12143603.png)

## Aboslute path to the public key for my ssh key on my account on ieng6:

![Image](Screenshot2024-02-12145321.png)

## Logging into my account passwordless:

![Image](Screenshot2024-01-28164548.png)

# Part 3:

## What I've learnt:

Almost everything this week was new to me. Everything from creating a new web server to logging into one. The `ssh` keyword is entirely new to me. The basics of URL's was the only thing I did know from before. Creating a private and public key to avoid password input was also new to me. Overall I'm very glad I learnt all of this. 
