## RSForm - Style Radio Buttons and Checkboxes

Have you ever been annoyed that RSForms will not let you modify the order of input/label to allow you to easily style it with CSS alone? And worse, RSJoomla itself uses styled radio and checkboxes all over their website.

RSForm puts the input inside the label, which some say it's "the proper way to do it". I prefer my checkboxes styled, and if you do it right with the rest of your code, no accessibility is lost.

Anyway, when creating a new form, just put this code below in the form at "Properties" > "PHP Scripts" > "Scripts Called on Form Display" and you will be set for good.

```php
$formLayout = preg_replace('/(<label.*?>)(<input.*?>)(.*?)(<\/label>)/i', '$2$1$3$4', $formLayout);
```

This solution was kindly provided by the support staff at RSJoomla, and hopefully they will accept my suggestion to include it in their documentation.

I'm just glad that I don't have to modify the core component anymore.
