# The-2020-US-elections-Wordcloud
<h1>Gathering more than 5000 lines of Biden's and Trump's speeches in many states and on various topics and generated a word_cloud for them each using Python data science modules</h2>
<ul>
 <li>you don't need to be a python expert to do this project this was my first real-world python project and it took me a day to get how things work
 <li> You should have basic  understanding to (amuller's world-cloud module ) make sure to give a look (https://github.com/amueller/word_cloud.git)

 <h3> You can create classical wordclouds using the default parameters of the word cloud object and the results will be something like this </h3>
 
 
![github1](https://user-images.githubusercontent.com/62334815/92413270-943da600-f14f-11ea-9bb3-e8536e4111ec.JPG)



<h3> Or mask your PNG image files to produce a more dynamic word_clouds</h3>

![h221](https://user-images.githubusercontent.com/62334815/92413267-9142b580-f14f-11ea-8407-e9bfab197242.JPG)





![masking](https://user-images.githubusercontent.com/62334815/92413216-5b053600-f14f-11ea-98f8-24732e3c44e9.JPG)



<h3> Below is the description of the main parameters of a word cloud instanse note that all of them have their default values and you should only give the the text itslef</h3>
 <h4> copyrights from amuller wordcloud library</h4>

  Init signature:
WordCloud(
    font_path=None,
    width=400,
    height=200,
    margin=2,
    ranks_only=None,
    prefer_horizontal=0.9,
    mask=None,
    scale=1,
    color_func=None,
    max_words=200,
    min_font_size=4,
    stopwords=None,
    random_state=None,
    background_color='black',
    max_font_size=None,
    font_step=1,
    mode='RGB',
    relative_scaling='auto',
    regexp=None,
    collocations=True,
    colormap=None,
    normalize_plurals=True,
    contour_width=0,
    contour_color='black',
    repeat=False,
    include_numbers=False,
    min_word_length=0,
    collocation_threshold=30,
)
Docstring:     
Word cloud object for generating and drawing.

Parameters
----------
font_path : string
    Font path to the font that will be used (OTF or TTF).
    Defaults to DroidSansMono path on a Linux machine. If you are on
    another OS or don't have this font, you need to adjust this path.

width : int (default=400)
    Width of the canvas.

height : int (default=200)
    Height of the canvas.

prefer_horizontal : float (default=0.90)
    The ratio of times to try horizontal fitting as opposed to vertical.
    If prefer_horizontal < 1, the algorithm will try rotating the word
    if it doesn't fit. (There is currently no built-in way to get only
    vertical words.)

mask : nd-array or None (default=None)
    If not None, gives a binary mask on where to draw words. If mask is not
    None, width and height will be ignored and the shape of mask will be
    used instead. All white (#FF or #FFFFFF) entries will be considerd
    "masked out" while other entries will be free to draw on. [This
    changed in the most recent version!]

contour_width: float (default=0)
    If mask is not None and contour_width > 0, draw the mask contour.

contour_color: color value (default="black")
    Mask contour color.

scale : float (default=1)
    Scaling between computation and drawing. For large word-cloud images,
    using scale instead of larger canvas size is significantly faster, but
    might lead to a coarser fit for the words.

min_font_size : int (default=4)
    Smallest font size to use. Will stop when there is no more room in this
    size.

font_step : int (default=1)
    Step size for the font. font_step > 1 might speed up computation but
    give a worse fit.

max_words : number (default=200)
    The maximum number of words.

stopwords : set of strings or None
    The words that will be eliminated. If None, the build-in STOPWORDS
    list will be used. Ignored if using generate_from_frequencies.

background_color : color value (default="black")
    Background color for the word cloud image.

max_font_size : int or None (default=None)
    Maximum font size for the largest word. If None, height of the image is
    used.

mode : string (default="RGB")
    Transparent background will be generated when mode is "RGBA" and
    background_color is None.

relative_scaling : float (default='auto')
    Importance of relative word frequencies for font-size.  With
    relative_scaling=0, only word-ranks are considered.  With
    relative_scaling=1, a word that is twice as frequent will have twice
    the size.  If you want to consider the word frequencies and not only
    their rank, relative_scaling around .5 often looks good.
    If 'auto' it will be set to 0.5 unless repeat is true, in which
    case it will be set to 0.

    .. versionchanged: 2.0
        Default is now 'auto'.

color_func : callable, default=None
    Callable with parameters word, font_size, position, orientation,
    font_path, random_state that returns a PIL color for each word.
    Overwrites "colormap".
    See colormap for specifying a matplotlib colormap instead.
    To create a word cloud with a single color, use
    ``color_func=lambda *args, **kwargs: "white"``.
    The single color can also be specified using RGB code. For example
    ``color_func=lambda *args, **kwargs: (255,0,0)`` sets color to red.

regexp : string or None (optional)
    Regular expression to split the input text into tokens in process_text.
    If None is specified, ``r"\w[\w']+"`` is used. Ignored if using
    generate_from_frequencies.

collocations : bool, default=True
    Whether to include collocations (bigrams) of two words. Ignored if using
    generate_from_frequencies.


    .. versionadded: 2.0

colormap : string or matplotlib colormap, default="viridis"
    Matplotlib colormap to randomly draw colors from for each word.
    Ignored if "color_func" is specified.

    .. versionadded: 2.0

normalize_plurals : bool, default=True
    Whether to remove trailing 's' from words. If True and a word
    appears with and without a trailing 's', the one with trailing 's'
    is removed and its counts are added to the version without
    trailing 's' -- unless the word ends with 'ss'. Ignored if using
    generate_from_frequencies.

repeat : bool, default=False
    Whether to repeat words and phrases until max_words or min_font_size
    is reached.

include_numbers : bool, default=False
    Whether to include numbers as phrases or not.

min_word_length : int, default=0
    Minimum number of letters a word must have to be included.

collocation_threshold: int, default=30
    Bigrams must have a Dunning likelihood collocation score greater than this
    parameter to be counted as bigrams. Default of 30 is arbitrary.

    See Manning, C.D., Manning, C.D. and Schütze, H., 1999. Foundations of
    Statistical Natural Language Processing. MIT press, p. 162
    https://nlp.stanford.edu/fsnlp/promo/colloc.pdf#page=22

Attributes
----------
``words_`` : dict of string to float
    Word tokens with associated frequency.

    .. versionchanged: 2.0
        ``words_`` is now a dictionary

``layout_`` : list of tuples (string, int, (int, int), int, color))
    Encodes the fitted word cloud. Encodes for each word the string, font
    size, position, orientation and color.

Notes
-----
Larger canvases with make the code significantly slower. If you need a
large word cloud, try a lower canvas size, and set the scale parameter.

The algorithm might give more weight to the ranking of the words
than their actual frequencies, depending on the ``max_font_size`` and the
scaling heuristic.
File:           c:\users\mar_k\anaconda3\lib\site-packages\wordcloud\wordcloud.py
Type:           type
Subclasses: 
