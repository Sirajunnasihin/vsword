# VS PHP Word HTML class

Vs PHP Word HTML is a package created by Raskin Veniamin which allows you to dynamically create files DOCX simply by converting HTML to .DOCX. It won the [PHP Innovation Award edition of January 2015](http://www.phpclasses.org/winners/year/2015/).

It is open source and easy to use. This article will focus on this library as it is the easiest to use.
 
With Vs PHP Word class it is very simple and straight forward to generate DOCX documents. You just include VsWord library and create a HTML parser object. Then pass to the parser whatever HTML code you want to added to the document and save it a DOCX file.

You can also use another way by using nodes where you get more control in styling and manipulating your text. You also can create add page breaks or add templates and styles. You can even use WYSIWYG HTML editotr like TinyMCE and save the result as DOCX file.

Based on the code, the author changes some code and publishes it into a library that can be easily integrated into the laravel framework through composer.

# Example
```
<?php

require_once '../vsword/VsWord.php'; 

VsWord::autoLoad();

$doc = new VsWord(); 
$parser = new HtmlParser($doc);
$parser->parse( '<h1>Hello world!</h1>' );
$parser->parse( '<h3>Hello world!</h3>' );
$parser->parse( '<p>Hello world!</p>' );
$parser->parse( '<h2>Header table</h2> <table> <tr><td>Coll 1</td><td>Coll 2</td></tr> </table>' );
$parser->parse( $html );

echo '<pre>'.($doc->getDocument() -> getBody() -> look()).'</pre>';

$doc->saveAs( 'htmlparser.docx' );

?>
```
