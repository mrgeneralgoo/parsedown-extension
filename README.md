## Parsedown Extension

A markdown extension for [parsedown](https://github.com/erusev/parsedown) , supports `[TOC]` syntax to generate table of contents.

## Installation

Include both `Parsedown.php` and `ParsedownExtension.php` .

## Example

``` php
        $text = <<<EOL
[TOC]
# This is head 1
## This is head 1-1
### This is head 1-3
# Sample text of head 2
## Sample text of head 2-1
EOL;

        $content = ParsedownExtension::instance()
            ->setTocEnabled(true)
            ->text($text);
```

```html
<ul>
	<li><a href="#This+is+head+1">This is head 1</a>
	<ul>
		<li><a href="#This+is+head+1-1">This is head 1-1</a>
		<ul>
			<li><a href="#This+is+head+1-3">This is head 1-3</a></li>
		</ul>
		</li>
	</ul>
	</li>
	<li><a href="#This+is+head+2">This is head 2</a>
	<ul>
		<li><a href="#This+is+head+2-1">This is head 2-1</a></li>
	</ul>
	</li>
</ul>
<h1 id="This+is+head+1">This is head 1</h1>
<h2 id="This+is+head+1-1">This is head 1-1</h2>
<h3 id="This+is+head+1-3">This is head 1-3</h3>
<h1 id="This+is+head+2">This is head 2</h1>
<h2 id="This+is+head+2-1">This is head 2-1</h2>
```

## Reporting issues

 You can [create an issue](https://github.com/mrgeneralgoo/parsedown-extension/issues/new)