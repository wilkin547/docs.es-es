---
title: Mantener pares nombre/valor (C#)| Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fda5e083584a57245a83bdf8c09d31e7ffdb2d5a
ms.lasthandoff: 03/13/2017


---
# <a name="maintaining-namevalue-pairs-c"></a>Mantener pares nombre/valor (C#)
Son muchas las aplicaciones que necesitan mantener información que se almacena mejor en forma de pares de nombre/valor. Esta información podría contener datos sobre configuración o valores globales. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] incluye métodos que facilitan la operación de mantener un conjunto de pares nombre/valor. Puede almacenar la información como atributos o como un conjunto de elementos secundarios.  
  
 Una diferencia existente entre almacenar la información como atributos o como elementos secundarios es que los atributos tienen, como restricción, que solo puede existir un atributo con un nombre en particular para un elemento. Esto no se aplica a los elementos secundarios.  
  
## <a name="setattributevalue-and-setelementvalue"></a>SetAttributeValue y SetElementValue  
 Los dos métodos que facilitan el mantenimiento de pares nombre/valor son <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> y <xref:System.Xml.Linq.XElement.SetElementValue%2A>. La semántica de ambos métodos es muy similar.  
  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> puede agregar, modificar o eliminar atributos de un elemento.  
  
-   Si llama a <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con el nombre de un atributo que no existe, el método crea un nuevo atributo y lo agrega al elemento especificado.  
  
-   Si llama a <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con el nombre de un atributo existente y con algún contenido especificado, el contenido del atributo se sustituye por el contenido especificado.  
  
-   Si llama a <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con el nombre de un atributo existente y especifica null para el contenido, el atributo se quita de su elemento primario.  
  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A> puede agregar, modificar o eliminar elementos secundarios de un elemento.  
  
-   Si llama a <xref:System.Xml.Linq.XElement.SetElementValue%2A> con el nombre de un elemento secundario que no existe, el método crea un nuevo elemento y lo agrega al elemento especificado.  
  
-   Si llama a <xref:System.Xml.Linq.XElement.SetElementValue%2A> con el nombre de un elemento existente y con algún contenido especificado, el contenido del elemento se sustituye por el contenido especificado.  
  
-   Si llama a <xref:System.Xml.Linq.XElement.SetElementValue%2A> con el nombre de un elemento existente y especifica null para el contenido, el elemento se quita de su elemento primario.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo crea un elemento que no tiene atributos. Luego usa el método <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> para crear y mantener una lista de pares nombre/valor.  
  
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
  
```  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo crea un elemento que no tiene elementos secundarios. Luego usa el método <xref:System.Xml.Linq.XElement.SetElementValue%2A> para crear y mantener una lista de pares nombre/valor.  
  
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
  
```  
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
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>   
 <xref:System.Xml.Linq.XElement.SetElementValue%2A>   
 [Modificar árboles XML (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
