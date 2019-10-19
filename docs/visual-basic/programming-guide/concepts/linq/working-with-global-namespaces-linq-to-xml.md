---
title: Trabajar con espacios de nombres globales (Visual Basic) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
ms.openlocfilehash: 93c7c654e43b579456633dea90ba6a362ff095f7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582359"
---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a><span data-ttu-id="ddf9d-102">Trabajar con espacios de nombres globales (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="ddf9d-102">Working with Global Namespaces (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="ddf9d-103">Una de las características clave de los literales XML en Visual Basic es la capacidad de declarar espacios de nombres XML mediante la instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-103">One of the key features of XML literals in Visual Basic is the capability to declare XML namespaces by using the `Imports` statement.</span></span> <span data-ttu-id="ddf9d-104">Mediante esta característica puede declarar un espacio de nombres XML que usa un prefijo o bien puede declarar un espacio de nombres XML predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-104">Using this feature, you can declare an XML namespace that uses a prefix, or you can declare a default XML namespace.</span></span>  
  
 <span data-ttu-id="ddf9d-105">Esta capacidad es útil en dos situaciones.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-105">This capability is useful in two situations.</span></span> <span data-ttu-id="ddf9d-106">En primer lugar, los espacios de nombres declarados en los literales XML no se mantienen en expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-106">First, namespaces declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="ddf9d-107">La declaración de espacios de nombres globales reduce la cantidad de trabajo que tiene que realizar para usar expresiones incrustadas con espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-107">Declaring global namespaces reduces the amount of work that you have to do to use embedded expressions with namespaces.</span></span> <span data-ttu-id="ddf9d-108">En segundo lugar, debe declarar espacios de nombres globales para usar espacios de nombres con propiedades XML.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-108">Second, you must declare global namespaces in order to use namespaces with XML properties.</span></span>  
  
 <span data-ttu-id="ddf9d-109">Puede declarar espacios de nombres globales en el nivel del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-109">You can declare global namespaces at the project level.</span></span> <span data-ttu-id="ddf9d-110">También puede declarar espacios de nombres globales en el nivel del módulo, lo que invalida los espacios de nombres globales de nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-110">You can also declare global namespaces at the module level, which overrides the project-level global namespaces.</span></span> <span data-ttu-id="ddf9d-111">Finalmente, puede reemplazar los espacios de nombres globales en un literal XML.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-111">Finally, you can override global namespaces in an XML literal.</span></span>  
  
 <span data-ttu-id="ddf9d-112">Cuando se utilizan literales XML o propiedades XML que están en espacios de nombres declarados globalmente, se puede ver el nombre expandido de las propiedades o los literales XML manteniendo el mouse sobre ellos en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-112">When using XML literals or XML properties that are in globally-declared namespaces, you can see the expanded name of XML literals or properties by hovering over them in Visual Studio.</span></span> <span data-ttu-id="ddf9d-113">Verá el nombre expandido en una información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-113">You will see the expanded name in a tooltip.</span></span>  
  
 <span data-ttu-id="ddf9d-114">Puede obtener un objeto <xref:System.Xml.Linq.XNamespace> que se corresponde con un espacio de nombres global usando el método `GetXmlNamespace`.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-114">You can get an <xref:System.Xml.Linq.XNamespace> object that corresponds to a global namespace using the `GetXmlNamespace` method.</span></span>  
  
## <a name="examples-of-global-namespaces"></a><span data-ttu-id="ddf9d-115">Ejemplos de espacios de nombres globales</span><span class="sxs-lookup"><span data-stu-id="ddf9d-115">Examples of Global Namespaces</span></span>  
 <span data-ttu-id="ddf9d-116">El siguiente ejemplo declara un espacio de nombres global predeterminado usando la instrucción `Imports` y después usa un literal XML para inicializar un objeto <xref:System.Xml.Linq.XElement> en ese espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-116">The following example declares a default global namespace by using the `Imports` statement, and then uses an XML literal to initialize an <xref:System.Xml.Linq.XElement> object in that namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ddf9d-117">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-117">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 <span data-ttu-id="ddf9d-118">El siguiente ejemplo declara un espacio de nombres global con un prefijo y después usa un literal XML para inicializar un elemento:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-118">The following example declares a global namespace with a prefix, and then uses an XML literal to initialize an element:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ddf9d-119">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-119">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a><span data-ttu-id="ddf9d-120">Espacios de nombres globales y expresiones incrustadas</span><span class="sxs-lookup"><span data-stu-id="ddf9d-120">Global Namespaces and Embedded Expressions</span></span>  
 <span data-ttu-id="ddf9d-121">Los espacios de nombres que se declaran en los literales XML no se mantienen en expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-121">Namespaces that are declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="ddf9d-122">El siguiente ejemplo declara un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-122">The following example declares a default namespace.</span></span> <span data-ttu-id="ddf9d-123">A continuación usa una expresión incrustada para el elemento `Child`.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-123">It then uses an embedded expression for the `Child` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="ddf9d-124">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 <span data-ttu-id="ddf9d-125">Como puede ver, el XML resultante incluye una declaración de un espacio de nombres predeterminado de forma que el elemento `Child` no esté en ningún espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-125">As you can see, the resulting XML includes a declaration of a default namespace so that the `Child` element is in no namespace.</span></span>  
  
 <span data-ttu-id="ddf9d-126">Puede volver a declarar el espacio de nombres en la expresión incrustada de ka siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-126">You could re-declare the namespace in the embedded expression, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="ddf9d-127">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-127">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 <span data-ttu-id="ddf9d-128">Sin embargo, esto es más complicado que usar el espacio de nombres global predeterminado, que es un enfoque más adecuado.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-128">However, this is more cumbersome to use than the global default namespace, which is a better approach.</span></span> <span data-ttu-id="ddf9d-129">Con el espacio de nombres global predeterminado, puede utilizar literales XML sin declarar espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-129">With the global default namespace, you can use XML literals without declaring namespaces.</span></span> <span data-ttu-id="ddf9d-130">El XML resultante estará en el espacio de nombres predeterminado declarado globalmente.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-130">The resulting XML will be in the globally-declared default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root>  
                                   <%= <Child/> %>  
                               </Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ddf9d-131">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-131">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a><span data-ttu-id="ddf9d-132">Usar espacios de nombres con propiedades XML</span><span class="sxs-lookup"><span data-stu-id="ddf9d-132">Using Namespaces with XML Properties</span></span>  
 <span data-ttu-id="ddf9d-133">Si está trabajando con un árbol XML que está en un espacio de nombres y utiliza propiedades XML, debe usar un espacio de nombres global para que las propiedades XML también estén en el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-133">If you are working with an XML tree that is in a namespace, and you use XML properties, then you must use a global namespace so that the XML properties will also be in the correct namespace.</span></span> <span data-ttu-id="ddf9d-134">En el ejemplo siguiente se declara un árbol XML en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-134">The following example declares an XML tree in a namespace.</span></span> <span data-ttu-id="ddf9d-135">Después se muestra el número de elementos `Child`.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-135">It then prints the count of `Child` elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 <span data-ttu-id="ddf9d-136">Este ejemplo indica que no hay elementos `Child`.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-136">This example indicates that there are no `Child` elements.</span></span> <span data-ttu-id="ddf9d-137">Genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-137">It produces the following output:</span></span>  
  
```console  
0  
```  
  
 <span data-ttu-id="ddf9d-138">No obstante, si declara un espacio de nombres global predeterminado, el literal XML y la propiedad XML estarán en el espacio de nombres global predeterminado:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-138">If, however, you declare a default global namespace, then both the XML literal and the XML property are in the default global namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>content</Child>  
            </Root>  
        Console.WriteLine(root.<Child>.Count())  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ddf9d-139">Este ejemplo indica que hay un elemento `Child`.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-139">This example indicates that there is one `Child` element.</span></span> <span data-ttu-id="ddf9d-140">Genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-140">It produces the following output:</span></span>  
  
```console  
1  
```  
  
 <span data-ttu-id="ddf9d-141">Si declara un espacio de nombres global que no tenga un prefijo, puede usar el prefijo para literales XML y propiedades XML:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-141">If you declare a global namespace that has a prefix, you can use the prefix for both XML literals and XML properties:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>content</aw:Child>  
            </aw:Root>  
        Console.WriteLine(root.<aw:Child>.Count())  
    End Sub  
End Module  
```  
  
## <a name="xnamespace-and-global-namespaces"></a><span data-ttu-id="ddf9d-142">XNamespace y espacios de nombres globales</span><span class="sxs-lookup"><span data-stu-id="ddf9d-142">XNamespace and Global Namespaces</span></span>  
 <span data-ttu-id="ddf9d-143">Puede obtener un objeto <xref:System.Xml.Linq.XNamespace> usando el método `GetXmlNamespace`:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-143">You can get an <xref:System.Xml.Linq.XNamespace> object by using the `GetXmlNamespace` method:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Dim xn As XNamespace = GetXmlNamespace(aw)  
        Console.WriteLine(xn)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ddf9d-144">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-144">This example produces the following output:</span></span>  
  
```console  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a><span data-ttu-id="ddf9d-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddf9d-145">See also</span></span>

- [<span data-ttu-id="ddf9d-146">Información general sobre espacios de nombres (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddf9d-146">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
