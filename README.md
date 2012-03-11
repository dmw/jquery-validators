
jquery-validators
===

jQUery Validators is a jQuery validation plugin that allows
you to setup individual validators inside form controls,
without binding the complete form configuring the validar
for each control, individually. It has several options,
like action taken on submit, error display styling and
custom validation, including custom validation regular
expressions and custom validation callbacks.

It is extensible to allow you to create field validations on
change and focusout events. The plug-in runs individually for
each field, without referring a specific form in the HTML.
Also you can define custom validation function and custom
messages, currently it supports English and Spanish messages,
but you can setup your own messages on it. If the field isn’t
valid for the validator, it will block the form identified by
the form selector (written as jQuery selector string). The
current version is 1.3.

An example on installing validators:

```javascript

/* example (invalid) validator */
$('#jquery_selector').addValidator({options});
 
/* example validators */
$('#phone_input').addValidator({type: 'phone', allow_empty: true});

$('#user_rut').addValidator({
    type: 'integer',
    minl: 5000000,
    maxl: 50000000
});

$('#select_input').addValidator({type: 'notempty'});

$('#user_dv').addValidator({type: 'rutdv'});

function rut_validator(idv) {
    /* validate rut */
}
 
$('#user_rut, #user_dv').addValidator({
    type: 'custom',
    custom: rut_validator,
    custom_message: 'Rut Invalido'
});

```

Option Description
---

|----------------------------------------------------------------------------------------------------------------------|
|Option             | Description                                                                                      |
|-------------------|-------------------------------------------------------------------------------------------------:|
|border_color       | border color for the validation message.                                                         |
|background_color   | background color for the validation message.                                                     |
|foreground_color   | font color for the validation message.                                                           |
|border_width       | border width for the validation message.                                                         |
|padding            | padding on the validation message.                                                               |
|margin             | margin on the validation message.                                                                |
|display            | display type, inline, block, cell-row, etc.                                                      |
|messages           | message list, see the source code for more details.                                              |
|form_selector      | form selector, as jQuery selector string.                                                        |
|form_event         | form event to handle using jQuery bind() operation.                                              |
|type               | validator type, those listed above.                                                              |
|len                | minimum length of control value.                                                                 |
|minl               | minimum limit for integer and double values.                                                     |
|maxl               | maximum limit for integer and double values.                                                     |
|exactlen           | requires an exact length for the control value.                                                  |
|regex              | regular expression to use with the &#8216;regex&#8217; validator.                                |
|custom             | custom validation function to use with &#8216;custom&#8217; validator.                           |
|language           | message language, currently it supports English and Spanish.                                     |
|allow_empty        | allow empty values with true, false requires a value.                                            |
|custom_message     | custom validation message, to use with &#8216;regex&#8217; and &#8216;custom&#8217; validators.  |                                                              |
|event              | overrides the default <i>focusout</i> and <i>change</i> events to validate the control.          |                                                      |
|----------------------------------------------------------------------------------------------------------------------|


Available Validators Types
---

------------------------------------------------------------------------------------------------|
| Type             | Description                                                                |
-----------------------------------------------------------------------------------------------:|
| integer          | /[0-9]+/gi expression.                                                     |
| float            | /[0-9]+\.[0-9]+/gi expression.                                             |
| letters          | /[a-z]+/gi expression.                                                     |
| alphanum         | /[a-z0-9]+/gi expression.                                                  |
| email            | email validation                                                           |
| alphacode        | /[0-9a-z\._-]+/gi expression.                                              |
| code             | /[0-9\._-]+/gi expression.                                                 |
| notempty         | /^.+$/gi expression.                                                       |
| empty            | /^$/gi expression.                                                         |
| rutdv            | /^[0-9K]$/g expression.                                                    |
| selected         | not empty value and selectedIndex different from zero con select controls. |
| zip              | /^[0-9]{5,15}$/g expression.                                               |
| zip4             | /^[0-9]{4,4}$/g expression.                                                |
| deliverylocation | /^[0-9]{2,2}$/g expression.                                                |
| phone            | +country_code (area_code) phone_number expression.                         |
| regex            | custom regular expression validator.                                       |
| http_url         | validates HTTP urls.                                                       |
| ftp_url          | validates FTP urls.                                                        |
| any_url          | validates URL (URI) urls.                                                  |
| twitter_id       | validates Twitter IDs.                                                     |
| iso_timestamp    | validates ISO Timestamps.                                                  |
| iso_date         | validates ISO Date formats.                                                |
| date             | validates dates in yyyy-mm-dd format.                                      |
| custom           | custom validation callback.                                                |
|-----------------------------------------------------------------------------------------------|


Available Option Defaults
---

|---------------------------------------------|
| Option                | Value               |
|--------------------------------------------:|
| border_color          | #e00                |
| background_color      | #900                |
| foreground_color      | #fff                |
| border_width          | 2px                 |
| messages              | _available_messages |
| form_selector         | form                | 
| form_event            | submit              |
| type                  | notempty            |
| padding               | 2px                 |
| margin                | 2px                 |
| display               | inline              |
| len                   | false               |
| minl                  | false               |
| maxl                  | false               |
| exactlen              | false               |
| regex                 | false               |
| custom                | false               |
| language              | es                  |
| allow_empty           | false               |
| custom_message        | false               |
| event                 | false               |
|---------------------------------------------|


Related Webpages
---

The jquery-validators main web page is located here [coder.cl](http://coder.cl/products/jquery-validators/)


Authors
---

* Copyright (c) 2010 [Daniel Molina Wegener](https://github.com/dmw) [coder.cl](http://coder.cl/)
* Copyright (c) 2011 [Daniel Molina Wegener](https://github.com/dmw) [coder.cl](http://coder.cl/)
* Copyright (c) 2011 Anton Norko [anton dot norko at gmail dot com](mailto:)
* Copyright (c) 2012 [Daniel Molina Wegener](https://github.com/dmw) [coder.cl](http://coder.cl/)

