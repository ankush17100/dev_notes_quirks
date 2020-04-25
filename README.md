# dev_notes_quirks
For quirky syntax and characteristics of languages and libraries that I can never remember and always run into.
<br> 
Their explanations and reasons can optionally be written.<br>
PRs are welcomed and ecncouraged.

# Pytorch
`model.cuda()` and `model.to(torch.device('cuda')`<br>
returns self(the model) which can be very infuriating when you are in a hurry and it returns the 20 line list of parameters of your model. These methods are also almost the same, just the difference being that `model.to(device)` provides flexibity as `device` can be cuda or cpu using an `if`; governed by whether the computer has a CUDA compatible GPU.<br>

`Tensor.retain_grad()`<br>
By default pytorch only updates gradients for leaf tensors but using this method the gradients are updated for that non leaf tensor also.

`Tensor is_leaf`<br>
This part is a little weird. Checkout doc before working with them. https://pytorch.org/docs/stable/autograd.html#torch.Tensor.is_leaf

`tensor.cuda()`<br>
This pushes the tensor to cuda but creates a copy so be sure to write - `tensor = tensor.cuda()`. This is not required when you do `model.cuda()`.

`nn.Module`<br> does not have a builtin `.device` method that is for tensors. The reason being that nn.Module can hold different types of data and on different devices.<br>
Workaround for this is to use `next(model.parameters()).device`.<br>
Pytorch Issue - https://github.com/pytorch/pytorch/issues/7460

# Github Markdown
Good gist on newline; read comments also. https://gist.github.com/shaunlebron/746476e6e7a4d698b373 
