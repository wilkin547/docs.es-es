---
title: Construcción funcional (LINQ to XML) (C#)
description: Obtenga información sobre la manera en que la interfaz de programación de LINQ to XML habilita la construcción funcional, es decir, la capacidad de crear un árbol XML en una sola instrucción en C#.
ms.date: 07/20/2015
ms.assetid: 57a82bcf-de03-4f1c-a0c8-9a76e989d542
ms.openlocfilehash: f209a7ef2a4597ec8eeccb3083b77223a27e7a65
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103767"
---
# <a name="functional-construction-linq-to-xml-c"></a><span data-ttu-id="2fd49-103">Construcción funcional (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2fd49-103">Functional Construction (LINQ to XML) (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="2fd49-104">proporciona una manera eficaz de crear elementos XML denominada *construcción funcional*.</span><span class="sxs-lookup"><span data-stu-id="2fd49-104">provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="2fd49-105">La construcción funcional es la capacidad de crear un árbol XML en una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="2fd49-105">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="2fd49-106">Hay varias características fundamentales de la interfaz de programación de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] que permiten la construcción funcional:</span><span class="sxs-lookup"><span data-stu-id="2fd49-106">There are several key features of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface that enable functional construction:</span></span>  
  
- <span data-ttu-id="2fd49-107">El constructor <xref:System.Xml.Linq.XElement> toma varios tipos de argumentos para el contenido.</span><span class="sxs-lookup"><span data-stu-id="2fd49-107">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="2fd49-108">Por ejemplo, puede pasar otro objeto <xref:System.Xml.Linq.XElement>, que se convierte en un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="2fd49-108">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="2fd49-109">Puede pasar un objeto <xref:System.Xml.Linq.XAttribute>, que se convierte en un atributo del elemento.</span><span class="sxs-lookup"><span data-stu-id="2fd49-109">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="2fd49-110">O bien, puede pasar cualquier otro tipo de objeto, que se convierte en una cadena y en el contenido de texto del elemento.</span><span class="sxs-lookup"><span data-stu-id="2fd49-110">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
- <span data-ttu-id="2fd49-111">El constructor <xref:System.Xml.Linq.XElement> toma una matriz de `params` del tipo <xref:System.Object>, de forma que puede pasar cualquier número de objetos al constructor.</span><span class="sxs-lookup"><span data-stu-id="2fd49-111">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="2fd49-112">Esto permite crear un elemento que tiene un contenido complejo.</span><span class="sxs-lookup"><span data-stu-id="2fd49-112">This enables you to create an element that has complex content.</span></span>  
  
- <span data-ttu-id="2fd49-113">Si un objeto implementa <xref:System.Collections.Generic.IEnumerable%601>, se enumera la colección del objeto y se agregan todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="2fd49-113">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="2fd49-114">Si la colección contiene objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, cada elemento de la colección se agrega por separado.</span><span class="sxs-lookup"><span data-stu-id="2fd49-114">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="2fd49-115">Esto es importante porque le permite pasar los resultados de una consulta LINQ al constructor.</span><span class="sxs-lookup"><span data-stu-id="2fd49-115">This is important because it lets you pass the results of a LINQ query to the constructor.</span></span>  
  
 <span data-ttu-id="2fd49-116">Estas características permiten escribir código para crear un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="2fd49-116">These features enable you to write code to create an XML tree.</span></span> <span data-ttu-id="2fd49-117">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2fd49-117">The following is an example:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="2fd49-118">Estas características también permiten escribir código que usa los resultados de las consultas LINQ cuando crea un árbol XML, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2fd49-118">These features also enable you to write code that uses the results of LINQ queries when you create an XML tree, as follows:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="2fd49-119">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2fd49-119">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  