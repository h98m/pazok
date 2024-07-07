
# Project Title

## Installation

You can install the package via pip:

```sh
pip install pazok
```

## Usage

### Function Explanations

#### The `tele_ms` Function

This function is designed to send messages to a specific Telegram user using the bot token and user's chat ID. The function supports sending formatted text using MarkdownV2. Supported formats include:

- **Bold text:** `*text*`
- **Italic text:** `_text_`
- **Strikethrough text:** `~text~`
- **Monospaced text:** `` `text` ``
- **Text with a link:** `[text](url)`
- **Spoiler text:** `||text||`
- **Code block:** `` ```code``` ``

It also supports sending files and images via URL or file path. The function automatically detects whether the input is a path or URL and handles it accordingly. If the file or image includes text, it will be automatically added to the file or image description. Additionally, the function supports sending buttons of type `types.InlineKeyboardButton`, allowing multiple buttons in the same message or just one button. Let's start with examples.

```python
# Importing the library
import pazok

# Bot and user information
token = "your_token"
chat_id = "your_chat_id"

# Sending a message with a button
button = pazok.types.InlineKeyboardButton("Click me!", url="https://example.com")
keyboard = pazok.types.InlineKeyboardMarkup().add(button)

pazok.tele_ms(token, chat_id, txt="Hello with button", reply_markup=keyboard)

# Sending an image
image_path = "/path/to/your/image.jpg"
pazok.tele_ms(token, chat_id, img=image_path, txt="Here is an image")
```

#### The `agnt` Function

This function generates a random user agent.

```python
import pazok

user_agent = pazok.agnt()
```

#### The `cook` Function

This function retrieves cookies from the Instagram API.

```python
import pazok

cookies = pazok.cook()
print(cookies.csrftoken)
```

### Text Decoration

#### The `tl` Function

This function displays text with a fading effect.

```python
import pazok

pazok.tl("Hello", 0.05, True)
```

### Custom Styling

#### Color Text

You can add color to your text using the following syntax:

```python
from termcolor import colored

text = colored('Hello, World!', 'red', attrs=['reverse', 'blink'])
print(text)
```

- **Bold text:** `*text*`
- **Italic text:** `_text_`
- **Strikethrough text:** `~text~`
- **Monospaced text:** `` `text` ``
- **Text with a link:** `[text](url)`
- **Spoiler text:** `||text||`
- **Code block:** `` ```code``` ``

### Example with Buttons and Images

You can send messages with buttons and images like this:

```python
import pazok

token = "your_token"
chat_id = "your_chat_id"

# Sending a message with a button
button = pazok.types.InlineKeyboardButton("Click me!", url="https://example.com")
keyboard = pazok.types.InlineKeyboardMarkup().add(button)

pazok.tele_ms(token, chat_id, txt="Hello with button", reply_markup=keyboard)

# Sending an image
image_path = "/path/to/your/image.jpg"
pazok.tele_ms(token, chat_id, img=image_path, txt="Here is an image")
```
