# slotify-php-js-noframework-project
PHP and JS project with Udemy course that creates spotify clone with PHP and JS, no frameworks </br>
Really great project I completed some time ago and now I document my portfolio and re-visit the code since I had no time to do that in past </br>
Here is the link to the Udemy course: https://www.udemy.com/course/spotify-clone/ </br>

# Weaknesses: </br>
- Use of md5 hash. Ive seen some older project by this author and he never did that before, but since this project is more frontend oriented, I just assume he
was lazy with backend explaining everything on the fly and not paying attention to things that go beyond the scope of the course. Still, using md5 is bad. </br>
- No CSRF token. Same thing, maybe it goes beyond the scope of the course, but even not using any framework, you can write such feature and add it very
easily </br>
- Uses mysqli, in functional manner. Same thing, Ive done older courses with this author and he used to use PDO, he was just being lazy with the backend
here explaining everything on the fly in order not to overwhelm the student with too much stuff. Still, I remember - always use PDO or even better some
ORM, never use mysqli in functional manner, always keep dsn parts in .env file. </br>
- If you want to echo error message and exit you can do both using die("Error msg here") function at once </br>
- What I do not understand, and people still keep doing it, is treating urls like strings and adding/interpolating search params to them.
JS has built-in URL class and URLSearchParams class that allows you to create urls with search params easily on the clicent side.
Concatenate search param to a raw string in JS and then urlencode($_GET['term']) on the server? Im not so sure about that. </br>
-  Mixing PHP, <script> tags nested within and then some more PHP nested within them is not very best. But then again, I understand the intentions of the author </br>
- If/else could be changed to try/catch </br>
- Interpolating variables into mysqli query is always bad (even though input was sanitized). If $_POST['registerButton'] is set it runs all sanitization methods
and then creates an user, but still - no csrf token, no check what http verb is used, no cors </br>
- I noticed a thing about jQuery enthusiasts - they tend to use var keyword, even if they use some post ES5 syntax somewhere else in the code.
Idk where this is coming from, whether its some weird convention that when you use jQuery you use var, or if using let/const is gonna mess code up
if you use jQuery (I doubt, but if thats the case, dont use jQuery, problem solved). 
Var keyword is bad. Pollutes global namespace. Is hoisted, is behaving in a way you dont expect, try using var-based for loop with set timeout,
its interview classing with a for loop outputing 3,3,3 when you expect to see 1,2,3 :P JavaScript as a language is this behemoth, new things and features
are added with new standards, understanding that new features will not be supported unless people write polyfills and check for existence of a feature
but the thing is old things will rarely be removed since it leads to the situation in which user might prefer older browser than the new one. Backwards
compatibility. We add all sorts of solutions with every standards but we do not remove the old problems. Situations in which there is so many ways
to create xhr, do something asynchronous, plus existence of external libraries (like axios, lodash) that used to solve the problem that is no longer
an issue with the new ES standard: it can overwhelm you while learning JS. But you must be aware that just because something is not removed doesnt
mean it should be used in new projects, it just means removing it could lead to some problems, why people still use COBOL or fortran in 21st century?
The amount of different approaches to one problem in JS is overwhelming just like the amount of things you have to consider while creating any web app.
You add noscript tags for people who use TOR to access your website and probably have js disabled. You use nomodule file for people whose browsers for
some reason do not support modules. You add touch events to your simple clicking canvas game bc some people use devices with no mouse, no cursor.
You design your app mobile-first and watch for responsive experience. You add polyfills if you detect browser that doesnt support something.
You can even transpile your code into ES5 if you want. Well, i might be wrong but I think you shouldnt care about people whose browser doesnt support
let/const nowadays. They will run into all sorts of issues while browsing the web anyways. But here, the motivation is, I suspect, just a weird habbit
of jQuery library enthusiasts. </br>
- Use of jQuery to manage reactive component, here audio player. Dont get me wrong, managing components using jQuery is an art worth teaching programmers,
especially nowadays, when they are gonna do everything in React but jQuery code will confuse them. Here motivation is not to discourage students 
by using something like React they might not know as well as the idea of building everything from scratch and not using external codes that will do the
whole job for you leaving you kind of confused how it all actually works. I like this idea. Just as I believe new programmers, if they have time, resources
and in general this privilege to delay getting their job a little and learn all sorts of programming paradigms, languages and CS related stuff before reaching
their destination domain (thats the route ive taken in my life) I also believe they should learn how to manage stuff using jQuery, how to build their own
jQuery-like library, study jQuery source code if there confident enough as a learning material. Just like a good JS programmer should be able to do OOP
in JS in obscure way, write on the fly things like map, filter, reduce, even if they use TS, new ES syntactic sugar and in general do not need to use such
things, but they deeply know how the internals work which is a plus. So yeah, if I get a task, i will try to use React or something like that to manage 
reactive components, but as a learning material managing everything by jQuery is great. </br>
- Dont mind these rants and lengthy critique, if sb wants to be nitpicking and find some failure, they always will (for example insufficent loggind and monitoring).
They thing is, programmers work in teams, programmers dont usually create everything from scratch, the guy is a great instructor and far more experienced 
coder than I am, he creates great things (like Google translate clone in React Native), its more reference, reminder for me and some kind of preemptive defence
for nitpicking hiring people since Ive done some projects, they are great but some things can always be improved.
I admire the author for his creativity and the ideas of building things from scratch, replicating existing challenging ideas instead of doing todos and blogs
with this or that framework. It always opens me to new ideas when I see some idea of what you want to achieve I wouldnt come up with myself as well as
the bluprint of strategy how you want to achieve it. Revisiting the code and assesing it with critial eye is also a new learning experience to me
and the ability of reading the code someone else wrote is also something worth working at.
I also get the idea that the author is more confident with JS than PHP, Ive done his twitter clone in node (socket.io!) course.
It was kinda overwhelming, but there was great structure and in general very good code. So Im greatful the author created a lot of PHP courses
because lets be honest, PHP can be first web language but there is shortage of learning materials for it compared to other languages
and I suspect thats the problem with PHP and all the hate it receives. </br>


# Strengths: </br>
- OOP, not to lengthy </br>
- Good project structure </br>
- Uses API, ajax, reactive components </br>
- I could copy/paste a lot of things I already said about other projects from this author. </br>
- I really like use of function constructor for Audio object and the neat way this object is written. </br>
- Its the first time I see creating element, that is not appended anywhere but rather kept as a reference and then some actions (like play, stop)
are performed on it. </br>
- Dealing with audio, playlists and all this stuff is a new experience to me </br>
- Project is really good and gets a lot of job done. </br>
- Frontend-component oriented project. The audio player is great, good looking, reactive, doing a lot of job (shuffling, managing volume).
Author was really pedantic about even the smallest details such as next/prev button that if used on a song thats been played longer than 3 seconds takes progress
to the beginning instead of going back. </br>
- uses filter var, strip tags, sanitization </br>
- uses $_SERVER['HTTP_X_REQUESTED_WITH'], thats nice </br>
- In general, very good user experience </br>

# Possible todos: </br>
- Could refactor the project and remove some things I mentioned </br>
- Could leave fronend as it is but migrate backend to some framework like Laravel.
- Could leave backend as it is but migrate frontend to React/Angular/Vue and maybe migrate JS to TS
- Could try something fancy with the frontend: custom web components (possible stencil.js), svelte, custom events </br>
- Could migrate backend to node.js and express (TS or not) to create fully javascript project (possible migration of db to mongo) <br>
- Small thing: I would add <base> tag or some templating engine and autoloading feature </br>
- EDIT: Just as I secure image files uploaded by the user by copying the contents rather than saving them with gd library I thought, maybe stupidly,
that maybe there is a way to copy the contents of the audio file like that. I mean I dont know what audio file can cause in terms of security,
people say its safe, no executable code, can do buffer overflow like any file but thats it. And of course I know, in linux shell you can copy any file,
some people might not know, but its not only for text files, you can copy images, music as well i think, but using shell exec is a very bad thing.
Plus, when I copy image I do not copy/paste file, I record the contents and output them in another image. Any malicious stuff or exif data
(the way I see it, but something so record those data and store them somwhere is also worth introducing) is not copied.
So equivalent of this in audio files would be playing and recording them. So what im looking for is stupid, also invloves running the file anyways,
probably takes a lot of memory (thats why we destroy image after the job is done in gd... if we close db conncetions in those more advanced projects is
another thing bothering me) but it led me to another interesting problem: not allowing users to download audio files, just letting them to listen, which
makes a lot of sense from the perspective of system design and system intended use. Worth considering </br>

All in all, great project Im proud I have in my portfolio :)
