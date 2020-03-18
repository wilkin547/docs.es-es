---
title: Errores en código declarativo-imperativo mixto (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: fada62d0-0680-4e73-945a-2b00d7a507af
ms.openlocfilehash: 76a9bb5abf6ce2700a2a0698ebc109f65e2b7eb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168354"
---
# <a name="mixed-declarative-codeimperative-code-bugs-linq-to-xml-c"></a><span data-ttu-id="dee27-102">Errores en códigos declarativos/imperativos mixtos (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="dee27-102">Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dee27-103">incluye numerosos métodos que le permiten modificar directamente un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="dee27-103">contains various methods that allow you to modify an XML tree directly.</span></span> <span data-ttu-id="dee27-104">Puede agregar elementos, eliminarlos, cambiar sus contenidos, agregar atributos, etc.</span><span class="sxs-lookup"><span data-stu-id="dee27-104">You can add elements, delete elements, change the contents of an element, add attributes, and so on.</span></span> <span data-ttu-id="dee27-105">Esta interfaz de programación se describe en [Modificar árboles XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="dee27-105">This programming interface is described in [Modifying XML Trees (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span> <span data-ttu-id="dee27-106">Si está llevando a cabo una iteración por uno de los ejes, como puede ser <xref:System.Xml.Linq.XContainer.Elements%2A>, y está modificando el árbol XML a medida que recorre el eje, es posible que acabe encontrando errores extraños.</span><span class="sxs-lookup"><span data-stu-id="dee27-106">If you are iterating through one of the axes, such as <xref:System.Xml.Linq.XContainer.Elements%2A>, and you are modifying the XML tree as you iterate through the axis, you can end up with some strange bugs.</span></span>  
  
 <span data-ttu-id="dee27-107">En ocasiones, a este problema se le conoce como "El problema de Halloween".</span><span class="sxs-lookup"><span data-stu-id="dee27-107">This problem is sometimes known as "The Halloween Problem".</span></span>  
  
## <a name="definition-of-the-problem"></a><span data-ttu-id="dee27-108">Definición del problema</span><span class="sxs-lookup"><span data-stu-id="dee27-108">Definition of the Problem</span></span>  
 <span data-ttu-id="dee27-109">Cuando se escribe cierto código utilizando LINQ para iterar por una colección, se utiliza un código de estilo declarativo.</span><span class="sxs-lookup"><span data-stu-id="dee27-109">When you write some code using LINQ that iterates through a collection, you are writing code in a declarative style.</span></span> <span data-ttu-id="dee27-110">Es un método que se aproxima más a definir *qué* es lo que quiere, en vez de especificar *cómo* quiere hacerlo.</span><span class="sxs-lookup"><span data-stu-id="dee27-110">It is more akin to describing *what* you want, rather that *how* you want to get it done.</span></span> <span data-ttu-id="dee27-111">Si escribe un código que 1) obtenga el primer elemento, 2) lo compruebe con una cierta condición, 3) lo modifique y 4) lo coloque nuevamente en la lista, entonces se trata de un código imperativo.</span><span class="sxs-lookup"><span data-stu-id="dee27-111">If you write code that 1) gets the first element, 2) tests it for some condition, 3) modifies it, and 4) puts it back into the list, then this would be imperative code.</span></span> <span data-ttu-id="dee27-112">Le está indicando al ordenador *cómo* hacer lo que quiere.</span><span class="sxs-lookup"><span data-stu-id="dee27-112">You are telling the computer *how* to do what you want done.</span></span>  
  
 <span data-ttu-id="dee27-113">Si se combinan ambos estilos de código en una misma operación, es cuando aparecen los problemas.</span><span class="sxs-lookup"><span data-stu-id="dee27-113">Mixing these styles of code in the same operation is what leads to problems.</span></span> <span data-ttu-id="dee27-114">Considere el siguiente caso:</span><span class="sxs-lookup"><span data-stu-id="dee27-114">Consider the following:</span></span>  
  
 <span data-ttu-id="dee27-115">Suponga que tiene una lista vinculada que contiene tres elementos (a, b y c):</span><span class="sxs-lookup"><span data-stu-id="dee27-115">Suppose you have a linked list with three items in it (a, b, and c):</span></span>  
  
 `a -> b -> c`  
  
 <span data-ttu-id="dee27-116">Ahora, suponga que desea recorrer la lista vinculada y añadir tres nuevos elementos (a', b' y c').</span><span class="sxs-lookup"><span data-stu-id="dee27-116">Now, suppose that you want to move through the linked list, adding three new items (a', b', and c').</span></span> <span data-ttu-id="dee27-117">Desea que la lista vinculada resultante tenga el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="dee27-117">You want the resulting linked list to look like this:</span></span>  
  
 `a -> a' -> b -> b' -> c -> c'`  
  
 <span data-ttu-id="dee27-118">De forma que escribe un código que recorre la lista y, que para cada elemento, añade uno nuevo justo después.</span><span class="sxs-lookup"><span data-stu-id="dee27-118">So you write code that iterates through the list, and for every item, adds a new item right after it.</span></span> <span data-ttu-id="dee27-119">Lo que ocurrirá es que el código encontrará primero el elemento `a` e insertará `a'` justo después.</span><span class="sxs-lookup"><span data-stu-id="dee27-119">What happens is that your code will first see the `a` element, and insert `a'` after it.</span></span> <span data-ttu-id="dee27-120">Ahora, el código pasará al siguiente nodo de la lista, que en este momento será `a'`</span><span class="sxs-lookup"><span data-stu-id="dee27-120">Now, your code will move to the next node in the list, which is now `a'`!</span></span> <span data-ttu-id="dee27-121">Entonces agregará un nuevo elemento a la lista, `a''`.</span><span class="sxs-lookup"><span data-stu-id="dee27-121">It happily adds a new item to the list, `a''`.</span></span>  
  
 <span data-ttu-id="dee27-122">¿Cómo se puede resolver esto en un caso real?</span><span class="sxs-lookup"><span data-stu-id="dee27-122">How would you solve this in the real world?</span></span> <span data-ttu-id="dee27-123">Una opción es realizar una copia de la lista vinculada original y crear una lista completamente nueva.</span><span class="sxs-lookup"><span data-stu-id="dee27-123">Well, you might make a copy of the original linked list, and create a completely new list.</span></span> <span data-ttu-id="dee27-124">O bien, si únicamente está escribiendo un código imperativo, puede encontrar el primer elemento, añadir el nuevo y, a continuación, avanzar dos elementos en la lista, pasando así por encima del elemento recién agregado.</span><span class="sxs-lookup"><span data-stu-id="dee27-124">Or if you are writing purely imperative code, you might find the first item, add the new item, and then advance twice in the linked list, advancing over the element that you just added.</span></span>  
  
## <a name="adding-while-iterating"></a><span data-ttu-id="dee27-125">Agregar a medida que se va iterando</span><span class="sxs-lookup"><span data-stu-id="dee27-125">Adding While Iterating</span></span>  
 <span data-ttu-id="dee27-126">Suponga, por ejemplo, que desea escribir un cierto código que, para cada elemento de un árbol, cree un elemento duplicado:</span><span class="sxs-lookup"><span data-stu-id="dee27-126">For example, suppose you want to write some code that for every element in a tree, you want to create a duplicate element:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements())  
    root.Add(new XElement(e.Name, (string)e));  
```  
  
 <span data-ttu-id="dee27-127">Este código entrará en un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="dee27-127">This code goes into an infinite loop.</span></span> <span data-ttu-id="dee27-128">La instrucción `foreach` lleva a cabo una iteración a lo largo del eje `Elements()`, agregando nuevos elementos al elemento `doc`.</span><span class="sxs-lookup"><span data-stu-id="dee27-128">The `foreach` statement iterates through the `Elements()` axis, adding new elements to the `doc` element.</span></span> <span data-ttu-id="dee27-129">Al final, acaba realizando dicha iteración por los elementos que se acaban de agregar.</span><span class="sxs-lookup"><span data-stu-id="dee27-129">It ends up iterating also through the elements it just added.</span></span> <span data-ttu-id="dee27-130">Y, dado que coloca los nuevos objetos en cada una de las iteraciones del bucle, llegará un momento en el que consuma toda la memoria disponible.</span><span class="sxs-lookup"><span data-stu-id="dee27-130">And because it allocates new objects with every iteration of the loop, it will eventually consume all available memory.</span></span>  
  
 <span data-ttu-id="dee27-131">Puede resolver este problema almacenando en memoria la colección mediante el operador de consulta estándar <xref:System.Linq.Enumerable.ToList%2A>, de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="dee27-131">You can fix this problem by pulling the collection into memory using the <xref:System.Linq.Enumerable.ToList%2A> standard query operator, as follows:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements().ToList())  
    root.Add(new XElement(e.Name, (string)e));  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="dee27-132">Ahora el código funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="dee27-132">Now the code works.</span></span> <span data-ttu-id="dee27-133">El árbol XML resultante es como sigue:</span><span class="sxs-lookup"><span data-stu-id="dee27-133">The resulting XML tree is the following:</span></span>  
  
```xml  
<Root>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
## <a name="deleting-while-iterating"></a><span data-ttu-id="dee27-134">Eliminar a medida que se va iterando</span><span class="sxs-lookup"><span data-stu-id="dee27-134">Deleting While Iterating</span></span>  
 <span data-ttu-id="dee27-135">Si desea eliminar todos los nodos que se encuentren en un cierto nivel, podría tener la tentación de escribir un código como el que sigue:</span><span class="sxs-lookup"><span data-stu-id="dee27-135">If you want to delete all nodes at a certain level, you might be tempted to write code like the following:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements())  
    e.Remove();  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="dee27-136">Sin embargo, no realiza la tarea que deseaba.</span><span class="sxs-lookup"><span data-stu-id="dee27-136">However, this does not do what you want.</span></span> <span data-ttu-id="dee27-137">En esta situación, tras eliminar el primer elemento (A), éste se elimina del árbol XML contenido en la raíz, con lo que el código del método Elements encargado de la iteración no podrá encontrar el siguiente elemento.</span><span class="sxs-lookup"><span data-stu-id="dee27-137">In this situation, after you have removed the first element, A, it is removed from the XML tree contained in root, and the code in the Elements method that is doing the iterating cannot find the next element.</span></span>  
  
 <span data-ttu-id="dee27-138">Este código anterior genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="dee27-138">The preceding code produces the following output:</span></span>  
  
```xml  
<Root>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
 <span data-ttu-id="dee27-139">De nuevo, la solución pasa por llamar a <xref:System.Linq.Enumerable.ToList%2A> para materializar la colección, de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="dee27-139">The solution again is to call <xref:System.Linq.Enumerable.ToList%2A> to materialize the collection, as follows:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements().ToList())  
    e.Remove();  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="dee27-140">Esto genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="dee27-140">This produces the following output:</span></span>  
  
```xml  
<Root />  
```  
  
 <span data-ttu-id="dee27-141">Como alternativa, puede eliminar la iteración entera llamando a <xref:System.Xml.Linq.XElement.RemoveAll%2A> en el elemento primario:</span><span class="sxs-lookup"><span data-stu-id="dee27-141">Alternatively, you can eliminate the iteration altogether by calling <xref:System.Xml.Linq.XElement.RemoveAll%2A> on the parent element:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
root.RemoveAll();  
Console.WriteLine(root);  
```  
  
## <a name="why-cant-linq-automatically-handle-this"></a><span data-ttu-id="dee27-142">¿Por qué LINQ no puede controlar este comportamiento?</span><span class="sxs-lookup"><span data-stu-id="dee27-142">Why Can't LINQ Automatically Handle This?</span></span>  
 <span data-ttu-id="dee27-143">Una posible aproximación sería trasladar todo a memoria en vez de realizar evaluaciones diferidas.</span><span class="sxs-lookup"><span data-stu-id="dee27-143">One approach would be to always bring everything into memory instead of doing lazy evaluation.</span></span> <span data-ttu-id="dee27-144">No obstante, esto resultaría muy costoso en términos de rendimiento y de utilización de la memoria.</span><span class="sxs-lookup"><span data-stu-id="dee27-144">However, it would be very expensive in terms of performance and memory use.</span></span> <span data-ttu-id="dee27-145">De hecho, si LINQ y (LINQ to XML) utilizaran este método, no sería viable en situaciones reales.</span><span class="sxs-lookup"><span data-stu-id="dee27-145">In fact, if LINQ and (LINQ to XML) were to take this approach, it would fail in real-world situations.</span></span>  
  
 <span data-ttu-id="dee27-146">Otra posible aproximación consiste en utilizar una cierta sintaxis transaccional en LINQ y hacer que el compilador intente analizar el código para determinar si es necesario materializar alguna colección en particular.</span><span class="sxs-lookup"><span data-stu-id="dee27-146">Another possible approach would be to put in some sort of transaction syntax into LINQ, and have the compiler attempt to analyze the code and determine if any particular collection needed to be materialized.</span></span> <span data-ttu-id="dee27-147">Sin embargo, puede resultar extremadamente complejo analizar todo el código que pueda tener efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="dee27-147">However, attempting to determine all code that has side-effects is incredibly complex.</span></span> <span data-ttu-id="dee27-148">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="dee27-148">Consider the following code:</span></span>  
  
```csharp  
var z =  
    from e in root.Elements()  
    where TestSomeCondition(e)  
    select DoMyProjection(e);  
```  
  
 <span data-ttu-id="dee27-149">Un código de análisis así necesitaría analizar los métodos TestSomeCondition y DoMyProjection, así como todos los métodos a los que llaman, con el fin de determinar si existe código con efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="dee27-149">Such analysis code would need to analyze the methods TestSomeCondition and DoMyProjection, and all methods that those methods called, to determine if any code had side-effects.</span></span> <span data-ttu-id="dee27-150">Pero no bastaría con que el código de análisis buscara código que tuviera efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="dee27-150">But the analysis code could not just look for any code that had side-effects.</span></span> <span data-ttu-id="dee27-151">Solo debería seleccionar aquel código que tuviera efectos secundarios sobre los elementos secundarios de `root` en este caso en particular.</span><span class="sxs-lookup"><span data-stu-id="dee27-151">It would need to select for just the code that had side-effects on the child elements of `root` in this situation.</span></span>  
  
 <span data-ttu-id="dee27-152">LINQ to XML no realiza ese tipo de análisis.</span><span class="sxs-lookup"><span data-stu-id="dee27-152">LINQ to XML does not attempt to do any such analysis.</span></span>  
  
 <span data-ttu-id="dee27-153">Es responsabilidad del programador evitar este tipo de problemas.</span><span class="sxs-lookup"><span data-stu-id="dee27-153">It is up to you to avoid these problems.</span></span>  
  
## <a name="guidance"></a><span data-ttu-id="dee27-154">Orientación</span><span class="sxs-lookup"><span data-stu-id="dee27-154">Guidance</span></span>  
 <span data-ttu-id="dee27-155">Primeramente, no mezcle código imperativo con código declarativo.</span><span class="sxs-lookup"><span data-stu-id="dee27-155">First, do not mix declarative and imperative code.</span></span>  
  
 <span data-ttu-id="dee27-156">Incluso en el caso de que conozca con precisión la semántica de las colecciones y de los métodos que modifican el árbol XML y escriba un código que evite este tipo de problemas, éste deberá ser mantenido por otros desarrolladores en un futuro, y es posible que éstos no estén al tanto de esos problemas.</span><span class="sxs-lookup"><span data-stu-id="dee27-156">Even if you know exactly the semantics of your collections and the semantics of the methods that modify the XML tree, if you write some clever code that avoids these categories of problems, your code will need to be maintained by other developers in the future, and they may not be as clear on the issues.</span></span> <span data-ttu-id="dee27-157">Si mezcla estilos de programación declarativa e imperativa, el código resultará más complicado.</span><span class="sxs-lookup"><span data-stu-id="dee27-157">If you mix declarative and imperative coding styles, your code will be more brittle.</span></span>  
  
 <span data-ttu-id="dee27-158">Si escribe código que materialice una colección de forma que se eviten todos estos problemas, incluya en él comentarios de forma que los programadores encargados de su mantenimiento puedan comprender la problemática.</span><span class="sxs-lookup"><span data-stu-id="dee27-158">If you write code that materializes a collection so that these problems are avoided, note it with comments as appropriate in your code, so that maintenance programmers will understand the issue.</span></span>  
  
 <span data-ttu-id="dee27-159">En segundo lugar, si el rendimiento y otras consideraciones lo permiten, utilice únicamente código declarativo.</span><span class="sxs-lookup"><span data-stu-id="dee27-159">Second, if performance and other considerations allow, use only declarative code.</span></span> <span data-ttu-id="dee27-160">No modifique el árbol XML existente.</span><span class="sxs-lookup"><span data-stu-id="dee27-160">Don't modify your existing XML tree.</span></span> <span data-ttu-id="dee27-161">Genere uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="dee27-161">Generate a new one.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
XElement newRoot = new XElement("Root",  
    root.Elements(),  
    root.Elements()  
);  
Console.WriteLine(newRoot);  
```  
