# dev_notes_quirks
For quirky syntax and characteristics of languages and libraries that I can never remember and always run into.
<br> 
Their explanations and reasons can optionally be written.<br>
PRs are welcomed and ecncouraged.

# Pytorch
`model.cuda()`<br>
is a succinct command to get the model to GPU but it returns self(the model) which can be very infuriating when you are in a hurry and it returns the 20 line list of parameters of your model.


`nn.Module`<br> does not have a builtin `.device` method that is for tensors. The reason being that nn.Module can hold different types of data and on different devices.<br>
Workaround for this is to use `next(model.parameters()).device`.<br>
Pytorch Issue - https://github.com/pytorch/pytorch/issues/7460

# Github Markdown
Good gist on newline; read comments also. https://gist.github.com/shaunlebron/746476e6e7a4d698b373 
