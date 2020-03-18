---
title: Mantener pares nombre/valor (C#)
ms.date: 07/20/2015
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
ms.openlocfilehash: 9c42a154a4c3ed1463e428faab4c7d33197ef4a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591705"
---
# <a name="maintaining-namevalue-pairs-c"></a>Mantener pares nombre/valor (C#)
Son muchas las aplicaciones que necesitan mantener información que se almacena mejor en forma de pares de nombre/valor. Esta información podría contener datos sobre configuración o valores globales. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] incluye métodos que facilitan la operación de mantener un conjunto de pares nombre/valor. Puede almacenar la información como atributos o como un conjunto de elementos secundarios.  
  
 Una diferencia existente entre almacenar la información como atributos o como elementos secundarios es que los atributos tienen, como restricción, que solo puede existir un atributo con un nombre en particular para un elemento. Esto no se aplica a los elementos secundarios.  
  
## <a name="setattributevalue-and-setelementvalue"></a>SetAttributeValue y SetElementValue  
 Los dos métodos que facilitan el mantenimiento de pares nombre/valor son <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> y <xref:System.Xml.Linq.XElement.SetElementValue%2A>. La semántica de ambos métodos es muy similar.  
  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> permite agregar, modificar o eliminar atributos de un elemento.  
  
- Si llama al método <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con el nombre de un atributo que no existe, éste creará un nuevo atributo y lo agregará al elemento especificado.  
  
- Si llama al método <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con el nombre de un atributo ya existente y con un contenido en particular, se sobrescribirán los contenidos del atributo con el contenido especificado.  
  
- Si llama al método <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con el nombre de un atributo ya existente y pasando nulo en el contenido, se eliminará el atributo de su elemento primario.  
  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A> permite agregar, modificar o eliminar elementos secundarios de un elemento.  
  
- Si llama al método <xref:System.Xml.Linq.XElement.SetElementValue%2A> con el nombre de un elemento secundario que no existe, éste creará un nuevo elemento y lo agregará al elemento especificado.  
  
- Si llama al método <xref:System.Xml.Linq.XElement.SetElementValue%2A> con el nombre de un elemento ya existente y con un contenido en particular, se sobrescribirán los contenidos del elemento con el contenido especificado.  
  
- Si llama al método <xref:System.Xml.Linq.XElement.SetElementValue%2A> con el nombre de un elemento ya existente y pasando nulo en el contenido, se eliminará el elemento de su elemento primario.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo crea un elemento que no tiene atributos. A continuación, utiliza el método <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> para crear y mantener una lista de pares nombre/valor.  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22);  
root.SetAttributeValue("Left", 20);  
root.SetAttributeValue("Bottom", 122);  
root.SetAttributeValue("Right", 300);  
root.SetAttributeValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
  
// Replace the value of Top.  
root.SetAttributeValue("Top", 10);  
Console.WriteLine(root);  
  
// Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo crea un elemento que no tiene elementos secundarios. A continuación, utiliza el método <xref:System.Xml.Linq.XElement.SetElementValue%2A> para crear y mantener una lista de pares nombre/valor.  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22);  
root.SetElementValue("Left", 20);  
root.SetElementValue("Bottom", 122);  
root.SetElementValue("Right", 300);  
root.SetElementValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Replace the value of Top.  
root.SetElementValue("Top", 10);  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Remove DefaultColor.  
root.SetElementValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [Modificar árboles XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)
