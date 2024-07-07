
# Installation

## pypi URL:
[https://pypi.org/project/pazok/](https://pypi.org/project/pazok/)

To install the library, use the following command:
```
pip install pazok
```

# Function Explanations

## The `tele_ms` Function

This function is designed to send messages to a specific Telegram user using the bot token and user's chat ID.

The function supports sending formatted text using **MarkdownV2**. Supported formats include:

- **Bold text:** `*text*`
- *Italic text:* `_text_`
- ~~Strikethrough text:~~ `~text~`
- `Monospaced text:` `text`
- [Text with a link:](https://example.com) `[text](url)`
- ||Spoiler text:|| `||text||`
- ```Code block:``` 
  ```
  code
  ```

It also supports sending files and images via URL or file path. The function automatically detects whether the input is a path or URL and handles it accordingly. If the file or image includes text, it will be automatically added to the file or image description. Additionally, the function supports sending buttons of type `types.InlineKeyboardButton`, allowing multiple buttons in the same message or just one button. Let's start with examples.

```
# Importing the library
import pazok

# Bot and user information
token = "token_bot"
id = "chat.id"

# Sending text only
text = "test" # Can be formatted with any supported telebot library format
pazok.tele_ms(token, id, txt=text)

# Sending text with a button
text = "test" # Can be formatted with any supported telebot library format
button = "name_button", "url_button"
# Sending multiple buttons in the same message
buttons = [
"name_button1", "url_button1",
"name_button2", "url_button2",
"name_button3", "url_button3"
]
# Sending the button with text
pazok.tele_ms(token, id, txt=text, buttons=buttons)

# Sending a file or image using their path or URL with text and button
text = "text"
button = "name_button", "url_button"
file = "Link or path to the file"
image = "Link or image path"
pazok.tele_ms(token, id, txt=text, file=file, buttons=buttons)

# Note: It's possible to send either a file or an image in each message. It's not possible to send both an image and a file in the same message.

# Sending an image
pazok.tele_ms(token, id, txt=text, img=image, buttons=buttons)
```

## Simple Functions

### Create a Random User Agent
**model:**
Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36

Here's an example:
```
import pazok
pazok.agnt()
```
