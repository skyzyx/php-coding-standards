# Controversial Bits
These are the topics where I've seen the most "weeping and gnashing of teeth" [1]. This is the side of the line where I find myself falling most often.

## Braces
My braces follow the [Uncompressed Style](DEFINE-BRACES.md) because, quite simply, it's easier to read than the [Compressed Style](DEFINE-BRACES.md) recommended by PSR-2. [2]

## Indenting
### Preference
Having started my career on the front-end, where saving bytes over the wire is very important (long before newfangled minifiers/compressors came along), using a single `TAB` character instead of 2/4/8 spaces was a no-brainer.

Even though it's no longer as important (since code crushing is a fully-automated task), I can move my cursor around from line-to-line much faster when there are fewer characters to traverse.

Also, I like being able to view indentations as wide or as narrow as I prefer. Someone else's preference should not be forced upon me. This isn't the dark ages of programming on tiny 80-character screens.

Therefore, I very much favor tabs.

### Joining the Dark Side
If I join a project that has already standardized on spaces, I have plugins for my IDE/editor which can convert to tabs, let me code in peace, then convert back to spaces. I've gotten really good at this, and code reviews can catch when I forget to change back.

Having said that, I'm a bit jealous of the 4-space folks because their code looks better when published to GitHub. Unfortunately, GitHub still displays tabs as taking 8 spaces. (Who actually displays tabbed code at 8 characters?!)

### Alignment
Alignment (as opposed to indentation) should of-course use spaces because tabs are variable width and spaces are static width. If you want to align pieces of a specific line (e.g., `=>` in associative arrays), you use a static width unit.

[TABs vs Spaces: The end of the debate.](http://www.iovene.com/posts/2007/05/tabs-vs-spaces-the-end-of-the-debate/) made the most argument that convinced me, and I've been following the pattern ever since.

----

1. https://www.bible.com/search/bible?q=Luke+13%3A28
2. Brace style was chosen by simple majority vote, as opposed to any kind of genuine usability research. See the "A.3. Survey Results" section of [PSR-2](http://www.php-fig.org/psr/psr-2/).
