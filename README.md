# dev_notes_quirks
For quirky syntax and characteristics of languages and libraries that I can never remember and always run into.
<br> 
Their explanations and reasons can optionally be written.<br>
PRs are welcomed and ecncouraged.

# Pytorch
model.cuda()<br>
is a succinct command to get the model to GPU but it returns self(the model) which can be very infuriating when you are in a hurry and it returns the 20 line list of parameters of your model.

# Github Markdown
Good gist on newline, read comments also- https://gist.github.com/shaunlebron/746476e6e7a4d698b373 
