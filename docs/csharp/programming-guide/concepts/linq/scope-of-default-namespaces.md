---
title: Ámbito del espacio de nombres predeterminado de C#
ms.date: 07/20/2015
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: d60f489f616a413e25bf5cd427bd467852a97c7b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379450"
---
# <a name="scope-of-default-namespaces-in-c"></a><span data-ttu-id="1ef6b-102">Ámbito del espacio de nombres predeterminado de C\#</span><span class="sxs-lookup"><span data-stu-id="1ef6b-102">Scope of Default Namespaces in C\#</span></span>
<span data-ttu-id="1ef6b-103">Los espacios de nombres predeterminados del árbol XML no se encuentran en el ámbito de las consultas.</span><span class="sxs-lookup"><span data-stu-id="1ef6b-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="1ef6b-104">Si tiene código XML en un espacio de nombres predeterminado, debe declarar una variable <xref:System.Xml.Linq.XNamespace> y combinarla con el nombre local para convertirla en un nombre completo que se usará en la consulta.</span><span class="sxs-lookup"><span data-stu-id="1ef6b-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="1ef6b-105">Uno de los problemas más habituales al consultar árboles XML es que si el árbol XML tiene un espacio de nombres predeterminado, el desarrollador a veces escribe la consulta como si el código XML no estuviera en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1ef6b-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="1ef6b-106">El primer conjunto de ejemplos de este tema muestra una forma habitual de cargar XML en un espacio de nombres predeterminado con una consulta incorrecta.</span><span class="sxs-lookup"><span data-stu-id="1ef6b-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="1ef6b-107">El segundo conjunto de ejemplos muestra las correcciones necesarias para que pueda consultar el código XML en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1ef6b-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ef6b-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ef6b-108">Example</span></span>  
 <span data-ttu-id="1ef6b-109">En este ejemplo se muestra la creación de XML en un espacio de nombres y una consulta que devuelve un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="1ef6b-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1ef6b-110">Código</span><span class="sxs-lookup"><span data-stu-id="1ef6b-110">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="1ef6b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ef6b-111">Comments</span></span>  
 <span data-ttu-id="1ef6b-112">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="1ef6b-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="1ef6b-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ef6b-113">Example</span></span>  
 <span data-ttu-id="1ef6b-114">En este ejemplo se muestra la creación de XML en un espacio de nombres y una consulta que se codifica correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ef6b-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="1ef6b-115">A diferencia del anterior ejemplo de código incorrecto, el enfoque adecuado al usar C# consiste en declarar e inicializar un objeto <xref:System.Xml.Linq.XNamespace> y usarlo cuando se especifiquen objetos <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="1ef6b-115">In contrast to the incorrectly coded example above, the correct approach when using C# is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="1ef6b-116">En este caso, el argumento para el método <xref:System.Xml.Linq.XContainer.Elements%2A> es un objeto <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="1ef6b-116">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1ef6b-117">Código</span><span class="sxs-lookup"><span data-stu-id="1ef6b-117">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="1ef6b-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ef6b-118">Comments</span></span>  
 <span data-ttu-id="1ef6b-119">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="1ef6b-119">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ef6b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ef6b-120">See also</span></span>

- [<span data-ttu-id="1ef6b-121">Trabajar con espacios de nombres XML (C#)</span><span class="sxs-lookup"><span data-stu-id="1ef6b-121">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
