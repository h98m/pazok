<div class="container">
            <div class="section">
                <div class="section-title">Installation</div>
                <p>
                    pypi URL:
                    <a href="https://pypi.org/project/pazok/"
                        >https://pypi.org/project/pazok/</a
                    >
                </p>
                <p>To install the library, use the following command:</p>
                <pre><code>pip install pazok</code></pre>
            </div>
            <div class="section">
                <div class="section-title">Function Explanations</div>
                <div class="sub-section">
                    <h3>The <code>tele_ms</code> Function</h3>
                    <p>
                        This function is designed to send messages to a specific
                        Telegram user using the bot token and user's chat ID.
                    </p>
                    <p>
                        The function supports sending formatted text using
                        MarkdownV2. Supported formats include:
                    </p>
                    <ul>
                        <li>Bold text: <code>*text*</code></li>
                        <li>Italic text: <code>_text_</code></li>
                        <li>Strikethrough text: <code>~text~</code></li>
                        <li>Monospaced text: <code>`text`</code></li>
                        <li>Text with a link: <code>[text](url)</code></li>
                        <li>Spoiler text: <code>||text||</code></li>
                        <li>Code block: <code>```code```</code></li>
                    </ul>
                    <p>
                        It also supports sending files and images via URL or
                        file path. The function automatically detects whether
                        the input is a path or URL and handles it accordingly.
                        If the file or image includes text, it will be
                        automatically added to the file or image description.
                        Additionally, the function supports sending buttons of
                        type types.InlineKeyboardButton, allowing multiple
                        buttons in the same message or just one button. Let's
                        start with examples.
                    </p>
                    <pre><code># Importing the library
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
pazok.tele_ms(token, id, txt=text, img=image, buttons=buttons)</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Simple Functions</h3>
                    <h4>Create a Random User Agent</h4>
                    <p>model:</p>
                    <p>
                        Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36
                        (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
                    </p>
                    <p>Here's an example:</p>
                    <pre><code>import pazok
pazok.agnt()</code></pre>
                    <h4>Create an Instagram-Specific User Agent</h4>
                    <p>model:</p>
                    <p>
                        Instagram 136.0.0.34.124 Android (23/6.0.1; 640dpi;
                        1440x2560; samsung; SM-G935; hero2lte;
                        samsungexynos8890; en_US; 208061712)
                    </p>
                    <p>Here's an example:</p>
                    <pre><code>import pazok
pazok.agnt_in()</code></pre>
                    <h4>Get Cookies from the Instagram API</h4>
                    <p>
                        The next function is to obtain some cookies from the
                        Instagram API. The cookie names that can be obtained are
                        csrftoken and mid.
                    </p>
                    <p>Here's an example:</p>
                    <pre><code>
import pazok
                        
cok = pazok.cook()
print(cok.csrftoken)
print(cok.mid)

# Or like this:
print(pazok.cook().csrftoken)
print(pazok.cook().mid)</code></pre>
                </div>

                <div class="sub-section">
                    <h3>Text Decoration Functions</h3>
                    <p>Now we have some functions to decorate the text.</p>
                    <p>
                        Function to display text with fading effect. This
                        function changes the color of text from black to white
                        across all shades of these colors to create a smooth
                        fading effect. You can also adjust the duration of the
                        effect and the text alignment format if you want it in
                        the center of the screen type True or in its normal form
                        type False. Here is an example:
                    </p>
                    <p>First function</p>

                    <h4>Display Text with a Fading Effect</h4>
                    <pre><code>
import pazok
                    
text = "test" # The text
time = 0.05 # Duration of the effect
align = True # If you want it continuously centered, write False

pazok.tl(text, time, align)</code></pre>
                    <h4>Decorate English Letters with 8 Types</h4>
                    <pre><code>
import pazok
                        
pazok.info_motifs()

# Pattern 1: 𝗛𝗲𝗹𝗹𝗼 𝗪𝗼𝗿𝗹𝗱 𝟭𝟮𝟯
# Pattern 2: 𝙷𝚎𝚕𝚕𝚘 𝚆𝚘𝚛𝚕𝚍 𝟷𝟸𝟹
# Pattern 3: 𝐇𝐞𝐥𝐥𝐨 𝐖𝐨𝐫𝐥𝐝 𝟏𝟐𝟑
# Pattern 4: ʜᥱᥣᥣ᥆ ᴡ᥆ᖇᥣძ 𝟙𝟚𝟛
# Pattern 5: ᕼᗴᒪᒪO ᗯOᖇᒪᗪ 123
# Pattern 6: 𝕳𝖊𝖑𝖑𝖔 𝖂𝖔𝖗𝖑𝖉 123
# Pattern 7: 𝓗𝓮𝓵𝓵𝓸 𝓦𝓸𝓻𝓵𝓭 123
# Pattern 8: ℍ𝕖𝕝𝕝𝕠 𝕎𝕠𝕣𝕝𝕕 𝟙𝟚𝟛

# Using the decoration function
print(pazok.motifs("text", 1))</code></pre>
                    <h4>Using Pre-Made Colors in the Library</h4>
                    <p> This function consists of ready-made colors in the library. Using this function is different from other functions in that we must call the library in this way</p>
                    
                    <pre><code>
import pazok
                        
from pazok import *

# Display color names
print(pazok.name_clo())

# o = orange
# b = blue
# m = white
# F = dark green
# Z = light red
# e = dark gray
# C = strong white
# p = wide line
# X = yellow
# j = pink
# E = light gray

# Using the color
print(f"{e} TEST")</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Display Text with a Waiting Pattern</h3>
                    <p>We have two functions that do the same job almost</p>
                    <p>The function is to display text with a waiting form and a certain period</p>
                    <h4>The First Pattern</h4>
                    <pre><code>
import pazok

text = "text" # The text
staliy = "name_staliy" # The pattern
time = 1 # Time

pazok.pazok_rich(text, staliy, time)

# Display pattern names
import pazok
pazok.name_rich()

# Will display:
# 1. arrow
# 2. christmas
# 3. circle
# 4. clock
# 5. hearts
# 6. moon
# 7. pong
# 8. runner
# 9. star
# 10. weather</code></pre>
                    <h4>The Second Pattern</h4>
                    <pre><code>text = "text" # The text
staliy = "bounce" # The pattern
time = 1 # Time

pazok.pazok_halo(text, staliy, time)

# Display special styles
import pazok
pazok.name_halo()

# Will display:
# 1. dots
# 2. dots2
# 3. dots3
# 4. dots4
# 5. dots5
# 6. dots6
# 7. dots7
# 8. dots8
# 9. dots9
# 10. dots10
# 11. dots11
# 12. dots12
# 13. line
# 14. line2
# 15. pipe
# 16. simpleDots
# 17. simpleDotsScrolling
# 18. star
# 19. star2
# 20. flip
# 21. hamburger
# 22. growVertical
# 23. growHorizontal
# 24. balloon
# 25. balloon2
# 26. noise
# 27. bounce
# 28. boxBounce
# 29. boxBounce2
# 30. triangle
# 31. arc
# 32. circle
# 33. square
# 34. circleQuarters
# 35. circleHalves
# 36. squish
# 37. toggle
# 38. toggle2
# 39. toggle3
# 40. toggle4
# 41. toggle5
# 42. toggle6
# 43. toggle7
# 44. toggle8
# 45. toggle9
# 46. toggle10
# 47. toggle11
# 48. toggle12
# 49. toggle13
# 50. arrow
# 51. arrow2
# 52. arrow3
# 53. bouncyBall
# 54. bouncyBall2
# 55. smiley
# 56. monkey
# 57. hearts
# 58. clock
# 59. earth
# 60. moon
# 61. runner
# 62. pong
# 63. shark
# 64. dqpb
# 65. weather
# 66. emoji
# 67. fire
# 68. lioud
# 69. magic
# 70. curses
# 71. chrome
# 72. windows
# 73. eyes
# 74. action
# 75. mr.robot
# 76. dvd
# 77. pacman
# 78. audi
# 79. bing
# 80. mobile
# 81. data
# 82. bit
# 83. mark
# 84. bit10
# 85. mew
# 86. fbi
# 87. all
# 88. food
# 89. ztang</code></pre>
                </div>
            </div>
            <div class="section">
                <div class="section-title">
                    Organizing Data and Using Threads
                </div>
                <div class="sub-section">
                    <h3>
                        Convert <code>curl</code> Commands to Requests Using the
                        <code>requests</code> Library
                    </h3>
                    
                    <p>The function is designed to convert curl commands into requests using the requests library. Here's an example:
</p>

                    <pre><code># Example of a curl command:
# curl http://en.wikipedia.org/

# Usage:
import pazok

curl_command = "curl http://en.wikipedia.org/"
print(pazok.cURL(curl_command))

# It will display a response similar to:
# https://t.me/b_azok
import requests

response = requests.get("http://en.wikipedia.org/").text

print(response)</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Organize JSON Responses Vertically</h3>
                    <p>The function organizes JSON responses into a vertical format.</p>
                    <pre><code>
import pazok
                        
# Example response:
{'message': 'The password you entered is incorrect. Please try again.', 'status': 'fail', 'error_type': 'bad_password'}

# Using the command:

print(pazok.json_req(response_variable))

# Will display:
# message: The password you entered is incorrect. Please try again.
# status: fail
# error_type: bad_password</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Execute Functions with Multiple Threads</h3>
              <p>The function's task is to execute functions with multiple threads, specifying the number of threads. Here's an example:
</p>
                    <pre><code>
import pazok

 def test():
    print("xxxx")

number_of_threads = 5  # You can put any number of threads
pazok.sb(test, number_of_threads)</code></pre>
                </div>
                <div class="sub-section">
                    <h3>
                        Fetch Session Information for a Specific Instagram
                        Account
                    </h3>
                    <p>The function is designed to fetch session information for a specific Instagram account by logging in with a username and password. Here's an example:
</p>
                    <pre><code>
import pazok

username = "username"
password = "password"

test = pazok.log_in(username, password)
print(test.csrftoken)
print(test.sessionid)
print(test.ds_user_id)
print(test.rur)</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Generate Random Data</h3>
                    <p>The function for generating random data, but in a simple way. Essentially, the function replaces numbers with types of data. I'll clarify each number and its value. Number 1 and its random value between a-z and 0-9, for example, if I write 111, the result will be ks6. Number 2, its random value is the same as number 1, but with a slight difference when placing number 2 in different places within the function, the value will be the same in all places, for example, if I write 222, the random value will be hhh. Number 3, its random value is _ or . If I write 1313, this is an example of no more. The result will be h_i. Number 4, its random value is numbers only from 0 to 9. I think the command has become clear, now an example of using the function.
</p>
                    <pre><code>
import pazok
                        
username = pazok.user_ran("2113244")
print(username)</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Get Data from a File</h3>
                    <p> The following function is dedicated to obtaining data from a text file. The function fetches the first line and passes it. There is an option in the function to delete the line after passing it or move it to the last line in the file. If you want to delete the line after passing it, put True, and if you want to move it to the end of the file, write False. </p><p> is an example.</p>
                    <pre><code>
import pazok
                        
data_file = pazok.user_file("name_file.txt", True)
print(data_file)

# Put True to activate delete mode after getting the data, or False to turn off delete mode</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Store Bot Data and Chat ID</h3>
                    <p>Now we have a function that stores the bot's code and the user's private chat ID and returns the data at the time of need, and if the data is not found in the hidden file, the function requests the data, and this helps us facilitate the use of our tools.</p><p> Here's an example.</p>

                    <pre><code>
import pazok
                        
token, id = pazok.info_bot()

# Delete user data from the hidden file
import pazok
pazok.info_bot_dlet()</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Sleep Function</h3>
                    <p> A simple and useful function designed to make the script sleep and there is a default time in the function or you can manually set the sleep time the default time is between 0.5 and 1 second, for example</p>
                    <pre><code>
import pazok
                        
pazok.sleep()  # Default mode
pazok.sleep(5)  # Manually specified value</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Convert Images to Text</h3>
                    <p> A wonderful function for converting images to text in two styles. The first is dots like this⣿⣿⣿ and the second is random symbols. There is a small note you must have the background of the image white and the shape you want to convert to text in black to get the best result. Here's an example of using the function.</p>
                    <pre><code>
import pazok
                        
z = "image path"
x = image size in numbers
a = required pattern (1 for dots, 2 for symbols)
print(pazok.picture(z, x, a))</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Set a Specific Date and Time</h3>
                    <p>A function designed to set a specific date and time and the function compares the current time with the specified time if it is less than the current time it returns false and if the current time is greater than or equal to the specified time it returns true. There is a default time in the function if the user wants to set a date only the default time is 23:59:59.</p><p> Here's an example of using the function.</p>

                    <pre><code>
import pazok
                        
test = pazok.timeeg(2024, 7, 5)
if test == True:
    print("The validity period has ended")</code></pre>
                </div>
                <div class="sub-section">
                    <h3>Check and Install Specific Libraries</h3>
                    <p> It checks the existence of a specific library or a group of libraries, and if it is not installed, it automatically installs the libraries.</p><p> Here's an example.</p>

                    <pre><code>
import pazok
                        
pazok.install("requests", "random", "threading")

# You can specify any number of libraries</code></pre>
            
