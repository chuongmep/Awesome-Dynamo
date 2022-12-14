# Zero Touch Templete

```{admonition} Zero Touch Document
:class: tip, dropdown
https://developer.dynamobim.org/03-Development-Options/3-4-zerotouch-nodes.html
```
## Function

### Return one output result

````{tab-set}
```{tab-item} CSharp
```cs
public static double MultiplyByTwo(double inputNumber = 2.0) 
{
    return inputNumber * 2.0;
}
```

```{tab-item} Python
```py
def MultiplyByTwo(inputNumber =2.0):
    return inputNumber *2.0
```
````

`Result:`
```{toggle}
4
```

### Return multiple outputs
``` cs
[NodeCategory("Query")]
[MultiReturn("Revit Document", "Dynamo Document")]
public static IDictionary? GetDocument(global::Revit.Elements.Element? element)
{
    return new Dictionary<string, object?>
    {
        {"Revit Document", element.InternalElement.Document},
        {"Dynamo Document", element.InternalElement.Document.ToDynamoType()}
    };
}

```
`Result:`
```{toggle}
![](../images/ZeroTouchDictionary.png)
```

```{raw} html
<script
   type="text/javascript"
   src="https://utteranc.es/client.js"
   async="async"
   repo="chuongmep/Awesome-Dynamo"
   issue-term="pathname"
   theme="github-light"
   label="💬 ZeroTouchTemplete"
   crossorigin="anonymous"
/>
```


