---
title: Construcción funcional (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
ms.openlocfilehash: a51360d6c8d44770c462afb728a1fb78d3e2cd42
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636853"
---
# <a name="functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="8f846-102">Construcción funcional (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f846-102">Functional Construction (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="8f846-103">proporciona una manera eficaz de crear elementos XML denominada *construcción funcional*.</span><span class="sxs-lookup"><span data-stu-id="8f846-103">provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="8f846-104">La construcción funcional es la capacidad de crear un árbol XML en una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="8f846-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="8f846-105">Hay varias características fundamentales de la interfaz de programación de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] que permiten la construcción funcional:</span><span class="sxs-lookup"><span data-stu-id="8f846-105">There are several key features of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface that enable functional construction:</span></span>  
  
- <span data-ttu-id="8f846-106">El constructor <xref:System.Xml.Linq.XElement> toma varios tipos de argumentos para el contenido.</span><span class="sxs-lookup"><span data-stu-id="8f846-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="8f846-107">Por ejemplo, puede pasar otro objeto <xref:System.Xml.Linq.XElement>, que se convierte en un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="8f846-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="8f846-108">Puede pasar un objeto <xref:System.Xml.Linq.XAttribute>, que se convierte en un atributo del elemento.</span><span class="sxs-lookup"><span data-stu-id="8f846-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="8f846-109">O bien, puede pasar cualquier otro tipo de objeto, que se convierte en una cadena y en el contenido de texto del elemento.</span><span class="sxs-lookup"><span data-stu-id="8f846-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
- <span data-ttu-id="8f846-110">El constructor <xref:System.Xml.Linq.XElement> toma una matriz de `params` del tipo <xref:System.Object>, de forma que puede pasar cualquier número de objetos al constructor.</span><span class="sxs-lookup"><span data-stu-id="8f846-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="8f846-111">Esto permite crear un elemento que tiene un contenido complejo.</span><span class="sxs-lookup"><span data-stu-id="8f846-111">This enables you to create an element that has complex content.</span></span>  
  
- <span data-ttu-id="8f846-112">Si un objeto implementa <xref:System.Collections.Generic.IEnumerable%601>, se enumera la colección del objeto y se agregan todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="8f846-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="8f846-113">Si la colección contiene objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, cada elemento de la colección se agrega por separado.</span><span class="sxs-lookup"><span data-stu-id="8f846-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="8f846-114">Esto es importante porque le permite pasar los resultados de una consulta LINQ al constructor.</span><span class="sxs-lookup"><span data-stu-id="8f846-114">This is important because it lets you pass the results of a LINQ query to the constructor.</span></span>  
  
 <span data-ttu-id="8f846-115">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8f846-115">The following is an example:</span></span>  
  
 <span data-ttu-id="8f846-116">Estas características permiten escribir código mediante literales XML para crear un árbol XML y también para escribir código que use los resultados de las consultas LINQ al crear un árbol XML:</span><span class="sxs-lookup"><span data-stu-id="8f846-116">These features enable you to write code using XML literals to create an XML tree, and also to write code that uses the results of LINQ queries when you create an XML tree:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="8f846-117">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8f846-117">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f846-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f846-118">See also</span></span>

- [<span data-ttu-id="8f846-119">Crear árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f846-119">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
