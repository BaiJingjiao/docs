

<pre>
https://developer.mozilla.org/en-US/docs/Web/XPath
http://www.w3.org/TR/xpath/#axes
http://www.w3schools.com/xpath/xpath_axes.asp
http://www.xmlplease.com/axis

to interact with SVG objects, the following XPath works:
"/*[name()='svg']/*[name()='SVG OBJECT']";
The XPath check using name() is necessary because SVG DOM nodes are in a different namespace. 
WebElement mapObject = driver.findElement(By.xpath("//*[name()='svg']/*[name()='rect']"));
((JavascriptExecutor) driver).executeScript("arguments[0].click();", mapObject);

// persition
"//*[@id='blalbalba']//span[persition()>3]"
// starts-with
"//input[starts-with(@id,'cb_variableGrid')";

// 约等于“ends with”, substring(从某个index开始，至最后), string-length
"//td[substring(@aria-describedby, string-length(@aria-describedby) - string-length('_variableName') +1) = '_variableName']";

// or
"//input[@id='btn_save'] | //input[@id='btn_update']"
"//div[contains(@class,'dynamicContactContainer') or contains(@class,'dynamicSettingContainer')]"

// following-sibling
"//*[@id='selIncidentCategory']/following-sibling::span//input"

// precding-sibling
"//*[@id='account_id']/preceding-sibling::span//input"
//找到前面最靠近'Last Active Login Report'的input
"//td[text()='Last Active Login Report']/preceding-sibling::td//input[last()]"
//找到后面最靠近的'Last Active Login Report'的input
(//td[text()='Last Active Login Report']/following-sibling::td/input)[1]

// element is visible
"[not(ancestor-or-self::*[contains(translate(@style,' ',''),'display:none')])]"

// parent
"//*[@variableid='10002']/../..//select[@name='fieldValue']";

// ancestor::*
"[not(ancestor::*[contains(@style,'display: none')])]";

// descendant::*
"//tr[descendant::td[text()='" + informationName + "']]";

// normalize-space()
// http://stackoverflow.com/questions/5992177/what-is-the-difference-between-normalize-space-and-normalize-spacetext
"//li[descendant::label[contains(normalize-space(),'dateVar')]]//input"

// node(), text(), string()
$x("//div[@class='margin_10b']/node()")
$x("//div[@class='margin_10b']/text()")
$x("string(//div[@class='margin_10b'])")
$x("//div[@class='margin_10b']/label/following-sibling::node()")
$x("string(//div[@class='margin_10b']/label/following-sibling::node())")

// count
"//*[@class="interesting" and count(ancestor::div[@class="frame"])=1]"
</pre>
