# Write2Learn
# A Hacktech Hardware Hack

## Inspiration


## What it does
Many people whose communication abilities are impaired must use Braille to comprehend the world around them, 
and talk to the world around them. But with Writing2Learn, the options to communicate with the classical languages 
of our world open up to these people. Through hand motions on a Synaptic TouchPad, Writing2Learn voices out the letter 
being drawn and also records the letter virtually.

## How we built it
Python was used for server-side processing, javascript and HTML5 for front-end local host development. We started off trying to
receive and output image data through matrices given the Synaptic TouchPad. Understanding the complexities and use of various 
numbers that the TouchPad gave us, we worked on then being able to recognize number of touches and gestures on the TouchPad. Once
we did this, we had the insane idea of trying to recognize gestures as English letters. We created a training data set of several
hundred iterations for each capitalized English letter and then by comparison to a real-time handwritten gesture, our program
suggests what was written. We also incorporated audio playing of the letter that was recognized.

## Challenges we ran into
Perhaps the crux of this product was being able to recognize which 
letter is being written at a given time. We are taking the image and flattening it into a vector and then pushing it
into an automated averaging algorithm which takes many, many image samples of say the letter "O" and determines the 
characteristics of a handwritten "O".

Our symbol recognition has been our toughest challenge yet. By taking the touch points that we recognize in the 
gesture, we created a map of the letters that we have pressed based on is recognized. We transform this data into long 
vectors of size length squared.
We are taking the vectors that we created and then computing the inner product of 
the x and y coordinates of every pixel that is affected by the touch on the Synaptics TouchPad. We take the highest inner 
product and correlate it to the best represented letter or symbol in our dataset JSON file.

Playing Audio on a HTML page is simple, but playing audio on a local host's index page is a different story. 
We had to learn server-side http requests and just being able to play the .wav sound of a particular letter after 
it is written was difficult.

## Accomplishments that We're proud of
We are proud of our algorithm to categorize image data, applying concepts we learn at school in real life, and creating a functional
product in less than 36 hours. Each team member had unique perspectives, experiences, and expertise, yet we were able to use those
differences to enhance and optimize the ultimate product. We overcame many technical challenges as well, which are discussed above.

## What We learned
We learned how to use Python backend, Synpatic technologies, debug large datasets with Python, image processing
(turns data into touch spikes that are grouped to form motions), data mining (collecting data for training set),
data analysis (comparing new data vs. training set) and data visualization (allowing JavaScript to show handwriting).

## What's next for Write2Learn
Write2Learn currently has letter recognition and audio files for English characters. We expect to create a training set for 
Chinese and Arabic characters as well as audio files for the most common words of these languages to provide people the 
chance to learn how to write foreign characters. There are several feature to be implemented like being able to record the sound
of phonetics/letters for other languages. Also, given more time we could create some algorithms that gave tips on how to
improve calligraphy and style of writing which would increae the educational value of Writing2Learn.
