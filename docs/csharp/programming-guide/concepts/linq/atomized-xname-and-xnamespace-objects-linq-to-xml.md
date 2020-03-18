---
title: Objetos XName y XNamespace atomizados (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a5b21433-b49d-415c-b00e-bcbfb0d267d7
ms.openlocfilehash: bc5066440d87f5485ae9099d7a7f4f5e9e66b4ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204274"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-c"></a>Objetos XName y XNamespace atomizados (LINQ to XML) (C#)
Los objetos <xref:System.Xml.Linq.XName> y <xref:System.Xml.Linq.XNamespace> se *atomizan*; es decir, si contienen el mismo nombre completo, hacen referencia al mismo objeto. De esta forma, se incrementan los beneficios de rendimiento de las consultas: cuando compare la igualdad de dos nombres atomizados, el lenguaje intermedio subyacente solo debe determinar si los dos puntos de referencia apuntan al mismo objeto. El código subyacente no debe hacer comparaciones de cadenas, ya que sería un proceso muy lento.  
  
## <a name="atomization-semantics"></a>Semántica de atomización  
 Atomización significa que si dos objetos <xref:System.Xml.Linq.XName> tienen el mismo nombre local y se encuentran en el mismo espacio de nombres, comparten la misma instancia. De igual forma, si dos objetos <xref:System.Xml.Linq.XNamespace> tienen el mismo URI de espacio de nombres, comparten la misma instancia.  
  
 Para que una clase habilite objetos atomizados, el constructor de la clase debe ser privado y no público. La razón es que si el constructor fuera público, podría crea un objeto no atomizado. Las clases <xref:System.Xml.Linq.XName> y <xref:System.Xml.Linq.XNamespace> implementan un operador de conversión implícita para convertir una cadena en <xref:System.Xml.Linq.XName> o <xref:System.Xml.Linq.XNamespace>. De esta forma, obtiene una instancia de estos objetos. No puede obtener ninguna instancia mediante un constructor, ya que no se puede tener acceso a él.  
  
 <xref:System.Xml.Linq.XName> y <xref:System.Xml.Linq.XNamespace> también implementan los operadores de igualdad y desigualdad, para determinar si los dos objetos que se comparan son referencias a la misma instancia.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código crea algunos objetos <xref:System.Xml.Linq.XElement> y muestra que nombres idénticos comparten la misma instancia.  
  
```csharp  
XElement r1 = new XElement("Root", "data1");  
XElement r2 = XElement.Parse("<Root>data2</Root>");  
  
if ((object)r1.Name == (object)r2.Name)  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.");  
else  
    Console.WriteLine("Different");  
  
XName n = "Root";  
  
if ((object)n == (object)r1.Name)  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.");  
else  
    Console.WriteLine("Different");  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 Como se ha mencionado anteriormente, la ventaja de los objetos atomizados es que el usuario utiliza uno de los métodos de eje que toman <xref:System.Xml.Linq.XName> como parámetro, el método de eje solo debe determinar que los dos nombres hagan referencia a la misma instancia para seleccionar los elementos deseados.  
  
 El siguiente ejemplo pasa <xref:System.Xml.Linq.XName> a la llamada del método <xref:System.Xml.Linq.XContainer.Descendants%2A>, cuyo rendimiento mejora gracias al patrón de atomización.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("C1", 1),  
    new XElement("Z1",  
        new XElement("C1", 2),  
        new XElement("C1", 1)  
    )  
);  
  
var query = from e in root.Descendants("C1")  
            where (int)e == 1  
            select e;  
  
foreach (var z in query)  
    Console.WriteLine(z);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
