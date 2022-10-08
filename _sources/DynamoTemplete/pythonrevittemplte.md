# Revit Python Script Templete

```{admonition} Python Templete
:class: tip, dropdown
https://primer.dynamobim.org/10_Custom-Nodes/10-6_Python-Templates.html
```
## Import Library
````{tab-set}
```{tab-item} Python
```py
import clr
clr.AddReference('RevitAPI')
from Autodesk.Revit.DB import *
from Autodesk.Revit.DB.Structure import *
clr.AddReference('RevitAPIUI')
from Autodesk.Revit.UI import *
clr.AddReference('System')
from System.Collections.Generic import List
clr.AddReference('RevitNodes')
import Revit
clr.ImportExtensions(Revit.GeometryConversion)
clr.ImportExtensions(Revit.Elements)
clr.AddReference('RevitServices')
import RevitServices
from RevitServices.Persistence import DocumentManager
from RevitServices.Transactions import TransactionManager
import System 
from System.Collections.Generic import *
import sys
sys.path.append(r'C:\Program Files (x86)\IronPython 2.7\Lib')

```
```{tab-item} CSharp
```cs
using Autodesk.Revit.DB;
using Dynamo.Graph.Nodes;
using Autodesk.DesignScript.Geometry;
using Autodesk.DesignScript.Runtime;
using Revit.GeometryConversion;
using RevitServices.Persistence;
```
## App,UIApp,Document,UIDocument

````{tab-set}
```{tab-item} Python
```py
doc = DocumentManager.Instance.CurrentDBDocument
uidoc=DocumentManager.Instance.CurrentUIApplication.ActiveUIDocument
uiapp = DocumentManager.Instance.CurrentUIApplication
app = DocumentManager.Instance.CurrentUIApplication.Application
```

```{tab-item} CSharp
```cs
doc = DocumentManager.Instance.CurrentDBDocument;
uidoc=DocumentManager.Instance.CurrentUIApplication.ActiveUIDocument;
uiapp = DocumentManager.Instance.CurrentUIApplication;
app = DocumentManager.Instance.CurrentUIApplication.Application;
```
````

## Function

### Convert To List
```py
def tolist(obj1):
	if hasattr(obj1,'__iter__') : return obj1
	else : return [obj1]
element = UnwrapElement(tolist(IN[0]))
```

### Flatten
```py
def flatten(x):
    result = []
    for el in x:
        if hasattr(el, "__iter__") and not isinstance(el, basestring):
            result.extend(flatten(el))
        else:
            result.append(el)
    return result
```

### Transaction

````{tab-set}
```{tab-item} Python
```py
#Do some action in a Transaction
TransactionManager.Instance.EnsureInTransaction(doc)
#Do Action
TransactionManager.Instance.TransactionTaskDone()
```

```{tab-item} Zero Touch Node
```cs
doc = DocumentManager.Instance.CurrentDBDocument
Autodesk.Revit.DB.Document doc = DocumentManager.Instance.CurrentDBDocument;
TransactionManager.Instance.EnsureInTransaction(doc);
// Do some thing
TransactionManager.Instance.TransactionTaskDone();
```
```{tab-item} Revit API
```cs
using Autodesk.Revit.ApplicationServices;
using Autodesk.Revit.Attributes;
using Autodesk.Revit.DB;
using Autodesk.Revit.UI;
using Application = Autodesk.Revit.ApplicationServices.Application;
public Result Execute(ExternalCommandData commandData, ref string message, ElementSet elements)
{
    try
    {
        _commandData = commandData;
        _uiapp = commandData.Application;
        _uidoc = commandData.Application.ActiveUIDocument;
        _doc = commandData.Application.ActiveUIDocument.Document;
        _app = commandData.Application.Application;
        using (Autodesk.Revit.DB.Transaction tran = new Autodesk.Revit.DB.Transaction(_doc,"Acton"))
        {
            // Do some thing
            tran.Commit();
        }
        Action();
    }
    catch (Exception e)
    {
        message = e.ToString();
        return Result.Failed;
    }
    return Result.Succeeded;
}
```
````


## Reference
```{note} More
https://primer.dynamobim.org/10_Custom-Nodes/10-6_Python-Templates.html
```