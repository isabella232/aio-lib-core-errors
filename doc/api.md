## Modules

<dl>
<dt><a href="#module_AioCoreSDKError">AioCoreSDKError</a></dt>
<dd></dd>
<dt><a href="#module_AioCoreSDKErrorWrapper">AioCoreSDKErrorWrapper</a></dt>
<dd></dd>
</dl>

## Classes

<dl>
<dt><a href="#AioCoreSDKError">AioCoreSDKError</a></dt>
<dd><p>The base class for all Adobe I/O Core SDK Errors.</p>
</dd>
</dl>

## Functions

<dl>
<dt><a href="#ErrorWrapper">ErrorWrapper(errorClassName, sdkName, Updater, BaseClass)</a></dt>
<dd><p>Returns a function that will dynamically create a class with the
error code specified, and updates the objects specified via the Updater parameter.</p>
<p>The returned function takes two parameters:</p>
<ul>
<li>code (string), which is the error code.</li>
<li>message (string), which is the error message (can contain format specifiers)</li>
</ul>
</dd>
<dt><a href="#createUpdater">createUpdater(codes, messages)</a></dt>
<dd><p>Returns a function that updates the parameters specified.
This is used in ErrorWrapper.</p>
</dd>
</dl>

<a name="module_AioCoreSDKError"></a>

## AioCoreSDKError
<a name="module_AioCoreSDKErrorWrapper"></a>

## AioCoreSDKErrorWrapper
<a name="AioCoreSDKError"></a>

## AioCoreSDKError
The base class for all Adobe I/O Core SDK Errors.

**Kind**: global class  

* [AioCoreSDKError](#AioCoreSDKError)
    * [new AioCoreSDKError([message], [code], [sdk], [sdkDetails], [captureStackTrace])](#new_AioCoreSDKError_new)
    * [.toJSON()](#AioCoreSDKError+toJSON)

<a name="new_AioCoreSDKError_new"></a>

### new AioCoreSDKError([message], [code], [sdk], [sdkDetails], [captureStackTrace])
Constructor.
Do not instantiate directly, subclass this class instead.


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| [message] | <code>string</code> | <code>&quot;&lt;no_message&gt;&quot;</code> | The message for the Error |
| [code] | <code>string</code> | <code>&quot;&lt;unknown_code&gt;&quot;</code> | The code for the Error |
| [sdk] | <code>string</code> | <code>&quot;&lt;unknown_sdk&gt;&quot;</code> | The SDK associated with the Error |
| [sdkDetails] | <code>object</code> | <code>{}</code> | The SDK details associated with the Error |
| [captureStackTrace] | <code>boolean</code> | <code>Error.captureStackTrace</code> | if available, capture the V8 stack trace |

<a name="AioCoreSDKError+toJSON"></a>

### aioCoreSDKError.toJSON()
Returns a JSON respresentation of this Error object.

**Kind**: instance method of [<code>AioCoreSDKError</code>](#AioCoreSDKError)  
<a name="ErrorWrapper"></a>

## ErrorWrapper(errorClassName, sdkName, Updater, BaseClass)
Returns a function that will dynamically create a class with the
error code specified, and updates the objects specified via the Updater parameter.

The returned function takes two parameters:
   - code (string), which is the error code.
   - message (string), which is the error message (can contain format specifiers)

**Kind**: global function  

| Param | Type | Description |
| --- | --- | --- |
| errorClassName | <code>string</code> | The class name for your SDK Error. Your Error objects will be these objects |
| sdkName | <code>string</code> | The name of your SDK. This will be a property in your Error objects |
| Updater | <code>function</code> | the object returned from a CreateUpdater call |
| BaseClass | <code>Class</code> | the base class that your Error class is extending. AioCoreSDKError is the default |

<a name="createUpdater"></a>

## createUpdater(codes, messages)
Returns a function that updates the parameters specified.
This is used in ErrorWrapper.

**Kind**: global function  

| Param | Type |
| --- | --- |
| codes | <code>object</code> | 
| messages | <code>Map</code> | 
