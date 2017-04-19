---
title: "Agregar elementos, atributos y nodos a un árbol XML (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b8a1644757fb4ce9f1498e79b16d1077e412346b
ms.lasthandoff: 03/13/2017


---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a>Agregar elementos, atributos y nodos a un árbol XML (Visual Basic)
Puede agregar contenidos (elementos, atributos, comentarios, instrucciones de procesamiento, texto y bloques CDATA) a un árbol XML existente.  
  
## <a name="methods-for-adding-content"></a>Métodos para agregar contenidos  
 Los métodos siguientes agregan contenidos secundarios a un <xref:System.Xml.Linq.XElement>o un <xref:System.Xml.Linq.XDocument>:</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A>|Agrega un contenido al final de los contenidos secundarios del <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A>|Agrega un contenido al comienzo de los contenidos secundarios del <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer>|  
  
 Los métodos siguientes agregan contenidos como nodos relacionados de un <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> El nodo más común al que se agregan habitualmente contenidos relacionados es <xref:System.Xml.Linq.XElement>, aunque es posible agregar contenidos relacionados válidos a otros tipos de nodos como <xref:System.Xml.Linq.XText>o <xref:System.Xml.Linq.XComment>.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XText> </xref:System.Xml.Linq.XElement>  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Agrega el contenido después de la <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Agrega contenido antes de la <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode>|  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El siguiente ejemplo crear dos árboles XML y, a continuación, modifica uno de ellos.  
  
### <a name="code"></a>Código  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
  
```  
  
### <a name="comments"></a>Comentarios  
 Este código genera el siguiente resultado:  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a>Vea también  
 [Modificar árboles XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
