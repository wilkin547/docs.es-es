---
title: Procedimiento para recuperar el valor de un elemento (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: c4bb78e937fe0de08242923cdd7cd638abf571c7
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805831"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a>Procedimiento para recuperar el valor de un elemento (LINQ to XML) (C#)

En este artículo se muestra cómo obtener el valor de los elementos. Existen dos formas principales de hacerlo:

- Convertir un objeto <xref:System.Xml.Linq.XElement> o un objeto <xref:System.Xml.Linq.XAttribute> al tipo deseado. El operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado y lo asigna a la variable.

- Use las propiedades <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>. También puede establecer el valor con estas propiedades.

Con C#, la conversión suele ser el mejor método. Si convierte el elemento o el atributo a un tipo que admite valores NULL, resulta más fácil escribir el código al recuperar el valor de un elemento (o atributo) que podría existir o no. En el [último ejemplo](#element-might-not-exist-example) de este artículo se muestra que la conversión es más sencilla en caso de que el elemento no exista. No obstante, no puede establecer el contenido de un elemento mediante la conversión del mismo modo que con la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.  
  
## <a name="string-cast-example"></a>Ejemplo de conversión de cadena  
 Para recuperar el valor de un elemento, convierta el objeto <xref:System.Xml.Linq.XElement> al tipo deseado. Siempre puede convertir un elemento en cadena, tal y como se indica a continuación:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="integer-cast-example"></a>Ejemplo de conversión de enteros  
 También puede convertir elementos a tipos diferentes a una cadena. Por ejemplo, si tiene un elemento que contiene un entero, puede convertirlo a `int`, tal como se muestra en el código siguiente:  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona operadores de conversión explícita para los tipos de datos siguientes: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` y `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona los mismos operadores de conversión para los objetos <xref:System.Xml.Linq.XAttribute>.  
  
## <a name="value-property-example"></a>Ejemplo de la propiedad Value  
 Puede usar la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para recuperar el contenido de un elemento:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="element-might-not-exist-example"></a>Ejemplo de elemento que podría no existir
 A veces, intenta recuperar el valor de un elemento aunque no esté seguro de que exista. En este caso, al asignar el elemento convertido a un tipo de referencia que acepta valores NULL o a un tipo de valor que acepta valores NULL, si el elemento no existe, la variable asignada se establece en `null`. El código siguiente demuestra que cuando el elemento podría existir o no, resulta más fácil usar la conversión que la propiedad <xref:System.Xml.Linq.XElement.Value%2A>.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 Este código genera el siguiente resultado:  
  
```output  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 Por lo general, puede escribir un código más simple al usar la conversión para recuperar el contenido de los elementos y los atributos.  
  
## <a name="see-also"></a>Vea también

- [Ejes de LINQ to XML (C#)](./linq-to-xml-axes-overview.md)
