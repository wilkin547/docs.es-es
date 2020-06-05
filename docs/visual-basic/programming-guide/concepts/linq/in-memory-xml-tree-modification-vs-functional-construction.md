---
title: Diferencias entre la modificación del árbol XML en memoria y Construcción funcional (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: d91c4ebf-6549-43cc-9961-26d4a82f722b
ms.openlocfilehash: efdbf51efa0f502ac9991d520defe45bb95678b7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397614"
---
# <a name="in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="baf15-102">Modificación del árbol XML en memoria frente a la construcción funcional (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baf15-102">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="baf15-103">Modificar un árbol XML directamente es un enfoque tradicional para cambiar la forma de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="baf15-103">Modifying an XML tree in place is a traditional approach to changing the shape of an XML document.</span></span> <span data-ttu-id="baf15-104">Una aplicación típica carga un documento en un almacén de datos como DOM o [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]; utiliza una interfaz de programación para insertar nodos, eliminar nodos o cambiar el contenido de los nodos y, a continuación, guarda el XML en un archivo o lo transmite a través de una red.</span><span class="sxs-lookup"><span data-stu-id="baf15-104">A typical application loads a document into a data store such as DOM or [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]; uses a programming interface to insert nodes, delete nodes, or change the content of nodes; and then saves the XML to a file or transmits it over a network.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="baf15-105">habilita otro enfoque que es útil en muchos escenarios *: construcción funcional*.</span><span class="sxs-lookup"><span data-stu-id="baf15-105">enables another approach that is useful in many scenarios *: functional construction*.</span></span> <span data-ttu-id="baf15-106">La construcción funcional trata la modificación de datos como un problema de transformación en lugar de una manipulación detallada de un almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="baf15-106">Functional construction treats modifying data as a problem of transformation, rather than as detailed manipulation of a data store.</span></span> <span data-ttu-id="baf15-107">Si puede tomar una representación de datos y transformarla eficientemente de una a otra, el resultado es el mismo que si ha tomado un almacén de datos y lo ha manipulado de alguna manera para que tome otra forma.</span><span class="sxs-lookup"><span data-stu-id="baf15-107">If you can take a representation of data and transform it efficiently from one form to another, the result is the same as if you took one data store and manipulated it in some way to take another shape.</span></span> <span data-ttu-id="baf15-108">Un aspecto fundamental del enfoque de construcción funcional es pasar los resultados de las consultas a los constructores <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="baf15-108">A key to the functional construction approach is to pass the results of queries to <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement> constructors.</span></span>  
  
 <span data-ttu-id="baf15-109">En muchos casos puede escribir el código de transformación en una fracción del tiempo que tardaría en manipular el almacén de datos y ese código es más eficaz y fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="baf15-109">In many cases you can write the transformational code in a fraction of the time that it would take to manipulate the data store, and that code is more robust and easier to maintain.</span></span> <span data-ttu-id="baf15-110">En esos casos, aunque el enfoque de transformación puede necesitar más potencia de procesamiento, es una forma más efectiva de modificar datos.</span><span class="sxs-lookup"><span data-stu-id="baf15-110">In these cases, even though the transformational approach can take more processing power, it is a more effective way to modify data.</span></span> <span data-ttu-id="baf15-111">Si un desarrollador está familiarizado con el enfoque funcional, el código resultante es en muchos casos más fácil de entender.</span><span class="sxs-lookup"><span data-stu-id="baf15-111">If a developer is familiar with the functional approach, the resulting code in many cases is easier to understand.</span></span> <span data-ttu-id="baf15-112">Resulta sencillo buscar el código que modifica cada parte del árbol.</span><span class="sxs-lookup"><span data-stu-id="baf15-112">It is easy to find the code that modifies each part of the tree.</span></span>  
  
 <span data-ttu-id="baf15-113">El enfoque en el que se modifica un árbol XML directamente es mucho más familiar para muchos programadores de DOM, mientras que el código escrito usando el enfoque funcional puede ser poco familiar para un desarrollador que aún no comprende este enfoque.</span><span class="sxs-lookup"><span data-stu-id="baf15-113">The approach where you modify an XML tree in-place is more familiar to many DOM programmers, whereas code written using the functional approach might look unfamiliar to a developer who doesn't yet understand that approach.</span></span> <span data-ttu-id="baf15-114">Si solo tiene que realizar una pequeña modificación en un árbol XML grande, el enfoque en el que se modifica un árbol directamente en muchos casos consumirá menos tiempo de CPU.</span><span class="sxs-lookup"><span data-stu-id="baf15-114">If you have to only make a small modification to a large XML tree, the approach where you modify a tree in place in many cases will take less CPU time.</span></span>  
  
 <span data-ttu-id="baf15-115">Este tema proporciona un ejemplo que se implementa con ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="baf15-115">This topic provides an example that is implemented with both approaches.</span></span>  
  
## <a name="transforming-attributes-into-elements"></a><span data-ttu-id="baf15-116">Transformar atributos en elementos</span><span class="sxs-lookup"><span data-stu-id="baf15-116">Transforming Attributes into Elements</span></span>  
 <span data-ttu-id="baf15-117">Para este ejemplo, supongamos que desea modificar el siguiente documento XML sencillo para que los atributos se conviertan en elementos.</span><span class="sxs-lookup"><span data-stu-id="baf15-117">For this example, suppose you want to modify the following simple XML document so that the attributes become elements.</span></span> <span data-ttu-id="baf15-118">Este tema primero presenta el enfoque tradicional de modificación directa.</span><span class="sxs-lookup"><span data-stu-id="baf15-118">This topic first presents the traditional in-place modification approach.</span></span> <span data-ttu-id="baf15-119">Después muestra el enfoque de construcción funcional.</span><span class="sxs-lookup"><span data-stu-id="baf15-119">It then shows the functional construction approach.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root Data1="123" Data2="456">  
  <Child1>Content</Child1>  
</Root>  
```  
  
### <a name="modifying-the-xml-tree"></a><span data-ttu-id="baf15-120">Modificar el árbol XML</span><span class="sxs-lookup"><span data-stu-id="baf15-120">Modifying the XML Tree</span></span>  
 <span data-ttu-id="baf15-121">Puede escribir código de procedimientos para crear elementos a partir de atributos y después eliminar los atributos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="baf15-121">You can write some procedural code to create elements from the attributes, and then delete the attributes, as follows:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
For Each att As XAttribute In root.Attributes()  
    root.Add(New XElement(att.Name, att.Value))  
Next  
root.Attributes().Remove()  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="baf15-122">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="baf15-122">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Content</Child1>  
  <Data1>123</Data1>  
  <Data2>456</Data2>  
</Root>  
```  
  
### <a name="functional-construction-approach"></a><span data-ttu-id="baf15-123">Enfoque de construcción funcional</span><span class="sxs-lookup"><span data-stu-id="baf15-123">Functional Construction Approach</span></span>  
 <span data-ttu-id="baf15-124">Por el contrario, un enfoque funcional consta de un código para formar un nuevo árbol, eligiendo y seleccionando elementos y atributos del árbol de origen y transformándolos, según convenga, a medida que se agregan al nuevo árbol.</span><span class="sxs-lookup"><span data-stu-id="baf15-124">By contrast, a functional approach consists of code to form a new tree, picking and choosing elements and attributes from the source tree, and transforming them as appropriate as they are added to the new tree.</span></span> <span data-ttu-id="baf15-125">El enfoque funcional tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="baf15-125">The functional approach looks like the following:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim newTree As XElement = _  
    <Root>  
        <%= root.<Child1> %>  
        <%= From att In root.Attributes() _  
            Select New XElement(att.Name, att.Value) %>  
    </Root>  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="baf15-126">Este ejemplo produce el mismo XML que el primer ejemplo.</span><span class="sxs-lookup"><span data-stu-id="baf15-126">This example outputs the same XML as the first example.</span></span> <span data-ttu-id="baf15-127">No obstante, tenga en cuenta que puede ver realmente la estructura resultante del nuevo XML en el enfoque funcional.</span><span class="sxs-lookup"><span data-stu-id="baf15-127">However, notice that you can actually see the resulting structure of the new XML in the functional approach.</span></span> <span data-ttu-id="baf15-128">Puede ver la creación del elemento `Root`, el código que extrae el elemento `Child1` del árbol de origen y el código que transforma los atributos del árbol de origen a los elementos del nuevo árbol.</span><span class="sxs-lookup"><span data-stu-id="baf15-128">You can see the creation of the `Root` element, the code that pulls the `Child1` element from the source tree, and the code that transforms the attributes from the source tree to elements in the new tree.</span></span>  
  
 <span data-ttu-id="baf15-129">El ejemplo funcional de este caso no es más corto que el primer ejemplo y en realidad no es más sencillo.</span><span class="sxs-lookup"><span data-stu-id="baf15-129">The functional example in this case is not any shorter than the first example, and it is not really any simpler.</span></span> <span data-ttu-id="baf15-130">No obstante, si tiene muchos cambios que realizar a un árbol XML, el enfoque no funcional se hará más complejo y difícil de entender.</span><span class="sxs-lookup"><span data-stu-id="baf15-130">However, if you have many changes to make to an XML tree, the non functional approach will become quite complex and somewhat obtuse.</span></span> <span data-ttu-id="baf15-131">Por el contrario, cuando se usa el enfoque funcional, se sigue formando el XML deseado, incrustando consultas y expresiones según convenga, para extraer el contenido deseado.</span><span class="sxs-lookup"><span data-stu-id="baf15-131">In contrast, when using the functional approach, you still just form the desired XML, embedding queries and expressions as appropriate, to pull in the desired content.</span></span> <span data-ttu-id="baf15-132">El enfoque funcional produce código que es más fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="baf15-132">The functional approach yields code that is easier to maintain.</span></span>  
  
 <span data-ttu-id="baf15-133">Tenga en cuenta que el enfoque funcional probablemente no tendrá un rendimiento tan bueno como la manipulación del árbol.</span><span class="sxs-lookup"><span data-stu-id="baf15-133">Notice that in this case the functional approach probably would not perform quite as well as the tree manipulation approach.</span></span> <span data-ttu-id="baf15-134">El principal problema es que el enfoque funcional crea objetos de corta duración.</span><span class="sxs-lookup"><span data-stu-id="baf15-134">The main issue is that the functional approach creates more short lived objects.</span></span> <span data-ttu-id="baf15-135">No obstante, la compensación es efectiva si el uso del enfoque funcional permite una mayor productividad del programador.</span><span class="sxs-lookup"><span data-stu-id="baf15-135">However, the tradeoff is an effective one if using the functional approach allows for greater programmer productivity.</span></span>  
  
 <span data-ttu-id="baf15-136">Éste es un ejemplo muy sencillo, pero sirve para mostrar la diferencia de filosofía entre los dos enfoques.</span><span class="sxs-lookup"><span data-stu-id="baf15-136">This is a very simple example, but it serves to show the difference in philosophy between the two approaches.</span></span> <span data-ttu-id="baf15-137">El enfoque funcional ofrece mayores ganancias de productividad para transformar documentos XML de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="baf15-137">The functional approach yields greater productivity gains for transforming larger XML documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf15-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="baf15-138">See also</span></span>

- [<span data-ttu-id="baf15-139">Modificar árboles XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baf15-139">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](modifying-xml-trees-linq-to-xml.md)
