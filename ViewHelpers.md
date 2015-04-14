# Introduction #

EJS provides view helpers for common tasks.  These helpers are very similar to those found in the Ruby On Rails framework.

| date\_tag | form\_tag | form\_tag\_end | hidden\_field\_tag | input\_field\_tag |
|:----------|:----------|:---------------|:-------------------|:------------------|
| is\_current\_page | link\_to | submit\_link\_to | link\_to\_if | link\_to\_unless |
| link\_to\_unless\_current | password\_field\_tag | select\_tag | single\_tag\_for | start\_tag\_for |
| submit\_tag | tag | tag\_end | text\_area\_tag | text\_tag |
| text\_field\_tag | url\_for | img\_tag |

# Details #

### date\_tag(name, value, html\_options) ###
Creates a date tag
```
date_tag('Installation[date]', new Date(1982, 10,20) )
```


### form\_tag(action, html\_options) ###
Creates a start form tag.
```
form_tag('/myaction',{multipart: true}) 
```


### end\_form\_tag() ###
Creates a start form tag.
```
form_tag_end()
```


### hidden\_field\_tag( name,  value,  html\_options) ###
Creates a hidden field.
```
hidden_field_tag('something[interesting]', 5) => 

              "<input id=\'something[interesting]\' 
                      value=\'5\' 
                      type=\'hidden\' 
                      name=\'something[interesting]\'/>"
```


### img\_tag ###
Creates an image tag.
```
img_tag('/some.png', 'something') => "<img src='/some.png' alt='something' />"
```


### input\_field\_tag ###
Creates an input field tag.
```
input_field_tag('something[interesting]', 5) => 

              "<input id='something[interesting]' 
                      value='5' 
                      type='text' 
                      name='something[interesting]'/>"
```


### is\_current\_page ###
Returns true if the url equals location.href or location.pathname, false if otherwise.
```
is_current_page('yahoo.com') => false
```


### link\_to ###
Creates a link to another page.
```
link_to('hello world', '/something/here') => "<a href='/something/here' >hello world</a>"
```


### submit\_link\_to ###
Creates a submit button that links to another page.
```
submit_link_to('holla', '/new/location') => 

              "<input onclick='window.location=\"/new/location\";return false;' 
                      value='holla' 
                      type='submit' />"
```


### link\_to\_if(condition, name, url, html\_options, post, block) ###
Just like link\_to if the condition is true. If condition is false it returns name.

### link\_to\_unless(condition, name, url, html\_options, block) ###
Just like link\_to if the condition is false. If condition is true it returns name.

### link\_to\_unless\_current(name, url, html\_options, block) ###
Just like link\_to if the url passed in matches the current pages url.  Returns name if otherwise.

### password\_field\_tag ###
Returns a password field.
```
password_field_tag('something[interesting]', 5) => 

              "<input id='something[interesting]' 
                      value='5' 
                      type='password' 
                      name='something[interesting]'/>"
```


### select\_tag ###
Returns a select tag.
```
var choices = [ {value: 1,    text: 'First Choice' }, 
                {value: 2,    text: 'Second Choice'},
                {value: 3,    text: 'Third Choice'}  ]
select_tag('mySelectElement', 2,  choices) => 

               "<select id='mySelectElement' value='2' name='mySelectElement'>
                   <option value='1' >First Choice</option>
                   <option value='2' selected='selected'>Second Choice</option>
                   <option value='3'>Third Choice</option>
                </select>"
```


### single\_tag\_for ###

Helper for creating a single tag like <br />

### start\_tag\_for ###

Helper for creating a beginning tag like <div>

<h3>submit_tag</h3>
Creates a submit tag.<br>
<pre><code>submit_tag('Submit') =&gt; "&lt;input type=\'submit\' value=\'Submit\' /&gt;"<br>
</code></pre>
<h3>tag</h3>

Creates a general tag.<br>
<br>
<h3>tag_end</h3>

Creates an end tag like </div>

### text\_area\_tag ###
```
text_area_tag('task[description]', 'Here is some text.\nA new line.') =>
               "<textarea id='task[description]' 
                          name='task[description]' 
                          cols='50' 
                          rows='4' >Here is some text.\nA new line.</textarea>"
```


### text\_field\_tag ###
```
text_field_tag('something[interesting]', 5) => 
               "<input id='something[interesting]' 
                       value='5' 
                       type='text' 
                       name='something[interesting]'/>"
```


### url\_for ###

returns a string that changes the url.