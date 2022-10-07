# Zero Touch Templete

## Function

Return List Dictionary

``` cs
[NodeCategory("Query")]
[MultiReturn("Revit Document", "Dynamo Document")]
public static IDictionary GetDocument(global::Revit.Elements.Element element)
{
    return new Dictionary<string, object?>
    {
        {"Revit Document", element.InternalElement.Document},
        {"Dynamo Document", element.InternalElement.Document.ToDynamoType()}
    };
}
```