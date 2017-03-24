---
title: Mantener pares de nombre y valor (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 54db297ecd39e37492dcf8bb4de4f64476662670
ms.lasthandoff: 03/13/2017


---
# <a name="maintaining-namevalue-pairs-visual-basic"></a>Mantenimiento de pares nombre/valor (Visual Basic)
Son muchas las aplicaciones que necesitan mantener información que se almacena mejor en forma de pares de nombre/valor. Esta información podría contener datos sobre configuración o valores globales. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] incluye métodos que facilitan la operación de mantener un conjunto de pares nombre/valor. Puede almacenar la información como atributos o como un conjunto de elementos secundarios.  
  
 Una diferencia existente entre almacenar la información como atributos o como elementos secundarios es que los atributos tienen, como restricción, que solo puede existir un atributo con un nombre en particular para un elemento. Esto no se aplica a los elementos secundarios.  
  
## <a name="setattributevalue-and-setelementvalue"></a>SetAttributeValue y SetElementValue  
 Los dos métodos que facilitan el mantenimiento de nombre/valor son de pares <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>y <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</xref:System.Xml.Linq.XElement.SetElementValue%2A> </xref:System.Xml.Linq.XElement.SetAttributeValue%2A> La semántica de ambos métodos es muy similar.  
  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>Puede agregar, modificar o eliminar atributos de un elemento.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
-   Si se llama a <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>con un nombre de un atributo que no existe, el método crea un nuevo atributo y lo agrega al elemento especificado.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
-   Si se llama a <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>con el nombre de un atributo existente y con algunas especificado contenido, el contenido del atributo se reemplaza con el contenido especificado.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
-   Si se llama a <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>con el nombre de un miembro de atributo y especifique null para el contenido, se quita el atributo de su elemento primario.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A>Puede agregar, modificar o eliminar elementos secundarios de un elemento.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
-   Si se llama a <xref:System.Xml.Linq.XElement.SetElementValue%2A>con el nombre de un elemento secundario que no existe, el método crea un nuevo elemento y lo agrega al elemento especificado.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
-   Si se llama a <xref:System.Xml.Linq.XElement.SetElementValue%2A>con el nombre de un elemento existente y con algunas especificado contenido, el contenido del elemento se reemplaza con el contenido especificado.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
-   Si se llama a <xref:System.Xml.Linq.XElement.SetElementValue%2A>con el nombre de un elemento ya existente y pasando nulo en el contenido, el elemento se quita de su elemento primario.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo crea un elemento que no tiene atributos. A continuación, utiliza el <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>método para crear y mantener una lista de pares nombre/valor.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo crea un elemento que no tiene elementos secundarios. A continuación, utiliza el <xref:System.Xml.Linq.XElement.SetElementValue%2A>método para crear y mantener una lista de pares nombre/valor.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
  
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
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A></xref:System.Xml.Linq.XElement.SetAttributeValue%2A>   
 <xref:System.Xml.Linq.XElement.SetElementValue%2A></xref:System.Xml.Linq.XElement.SetElementValue%2A>   
 [Modificar árboles XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
