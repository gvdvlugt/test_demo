Hello,

https://www.youtube.com/watch?v=4_r_1W6aVIE&list=PLpVC00PAQQxFNDfiXn6LH1gOLllGS3hhl&index=14 at 18:11
Course Acquia Drupal Training - Module Development Unit 2-14.
Using Visual Studio Code version: 1.84.2
Local Site: Drupal 10.1.6
PHP 8.3 and 7.4


I get syntax errors although I'm pretty sure I typed the code correct:

In FirstController.php line 15-21:

  public function simpleContent() {
    return [
      '#type' => 'markup',
      '#markup' => t(string 'Hello Drupal World. Time flies like an arrow, fruit flies like a banana.'),
    ];
  }


 
 
The text of the string is underlined with a straight and zig-zag line.

I get a syntax error:
"Syntax error: unexpected token ''Hello Drupal World.Time flies like an arrow, fruit flies like a banana.''", PHP(PHP2014) [Ln18, Col 28]
Unexpected 'StringLiteral'. Expected ')'. intelephense(P1001) [Ln 18, Col28]



Same in line 23-30:
  public function variableContent($name_1,$name_2){

    return [
      '#type' => 'markup',
      '#markup' => t😥( string "@name_1 and @name_2 say hello to you!",
        ['@name1' => $name_1, '@name2' => $name_2]),😥
    ];
  }
}

The text of the string is underlined and with a straight and zig-zag line.

I get syntax errors:

	"resource": "/d:/xampp/htdocs/testsite/modules/custom/mymodule/src/FirstController.php",
	"owner": "_generated_diagnostic_collection_name_#5",
 
	"code": "PHP2014",
 
	"severity": 8,
 
	"message": "Syntax error: unexpected token ''Hello Drupal World. Time flies like an arrow, fruit flies like a banana.''",
 
	"source": "PHP",
 
	"startLineNumber": 18,
 
	"startColumn": 29,
 
	"endLineNumber": 18,
 
	"endColumn": 103



	"resource": "/d:/xampp/htdocs/testsite/modules/custom/mymodule/src/FirstController.php",
 
	"owner": "_generated_diagnostic_collection_name_#0",
 
	"code": "P1001",
 
	"severity": 8,
 
	"message": "Unexpected 'StringLiteral'. Expected ','.",
 
	"source": "intelephense",
 
	"startLineNumber": 18,
 
	"startColumn": 29,
 
	"endLineNumber": 18,
 
	"endColumn": 103
 

	"resource": "/d:/xampp/htdocs/testsite/modules/custom/mymodule/src/FirstController.php";
 
	"owner": "_generated_diagnostic_collection_name_#0",
 
	"code": "P1001",
 
	"severity": 8,
 
	"message": "Unexpected 'StringLiteral'. Expected ','.",
 
	"source": "intelephense",
 
	"startLineNumber": 25,
 
	"startColumn": 29,
 
	"endLineNumber": 25,
 
	"endColumn": 68



Suprisingly PHP doesn't give an error in line 25.
The local site did start after flushing the cache but gave "Page not found" (/mycustompath)
Mymodule.routing.yml seems to be OK.

I checked and retyped the code during a few days with double and single quotes, changed the text, changed the PhP version from 8.3 to 7.4, searched the net etc. but could not find any solution

Any idea what I do wrong?
Kind regards,

Guus van der Vlugt
