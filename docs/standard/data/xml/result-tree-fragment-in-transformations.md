---
title: Fragmento del árbol de resultados en transformaciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df363480-ba02-4233-9ddf-8434e421c4f1
ms.openlocfilehash: e454c1194e8c280042857f106e22d0d0509417e3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156366"
---
# <a name="result-tree-fragment-in-transformations"></a><span data-ttu-id="2e41e-102">Fragmento del árbol de resultados en transformaciones</span><span class="sxs-lookup"><span data-stu-id="2e41e-102">Result Tree Fragment in Transformations</span></span>

> [!NOTE]
> <span data-ttu-id="2e41e-103">La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="2e41e-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="2e41e-104">Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="2e41e-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="2e41e-105">Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2e41e-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

 <span data-ttu-id="2e41e-106">Los fragmentos del árbol de resultados, también conocidos como fragmentos de árboles de resultados, no son más que un tipo especial de conjuntos de nodos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-106">Result tree fragments, also known as result tree fragments, are nothing more than a special type of node set.</span></span> <span data-ttu-id="2e41e-107">Cualquier función que pueda realizar sobre un conjunto de nodos puede realizarla también sobre estos fragmentos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-107">You can perform any function on them that can be performed on a node set.</span></span> <span data-ttu-id="2e41e-108">También puede convertir un fragmento del árbol de resultados en un conjunto de nodos utilizando la función `node-set()`, y podrá utilizar dicho fragmento posteriormente en cualquier lugar en el que puede utilizarse un conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-108">Or, you can also convert a result tree fragment to a node set using the `node-set()` function and subsequently use it any place that a node set can be used.</span></span>

 <span data-ttu-id="2e41e-109">Un fragmento del árbol de resultados se crea como resultado de utilizar un elemento `<xsl:variable>` o `<xsl:param>` de una forma específica en una hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-109">A result tree fragment is created as a result of using an `<xsl:variable>` or `<xsl:param>` element in a specific manner in a style sheet.</span></span> <span data-ttu-id="2e41e-110">La sintaxis de los elementos `variable` y `parameter` es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e41e-110">The syntax for the `variable` and `parameter` elements is as follows:</span></span>

```xml
<xsl:param name=Qname select= XPath Expression >
    template body
</xsl:param>

<xsl:variable name=Qname select=XPath Expression >
    template body
</xsl:variable>
```

<span data-ttu-id="2e41e-111">En el caso del elemento `parameter`, el valor se asigna a (`Qname`) de varias formas.</span><span class="sxs-lookup"><span data-stu-id="2e41e-111">For the `parameter` element, the value is assigned to the qualified name (`Qname`) in several ways.</span></span> <span data-ttu-id="2e41e-112">Puede asignar un valor predeterminado al parámetro mediante la devolución del contenido de la expresión XPath en el atributo `select` o asignándole el contenido del cuerpo de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="2e41e-112">You can assign a default value to the parameter by returning content from the XML Path Language (XPath) expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="2e41e-113">En el caso del elemento `variable`, el valor se asigna también de varias formas.</span><span class="sxs-lookup"><span data-stu-id="2e41e-113">For the `variable` element, the value is also assigned in several ways.</span></span> <span data-ttu-id="2e41e-114">Puede asignar un valor mediante la devolución del contenido de la expresión XPath en el atributo `select` o asignándole el contenido del cuerpo de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="2e41e-114">You can assign it by returning content from the XPath expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="2e41e-115">Tanto para el elemento `parameter` como para el `variable`, si se asigna un valor mediante la expresión XPath, se devolverá uno de los cuatro tipos básicos de XPath: booleano, de cadena, numérico o de conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-115">For both the `parameter` and `variable` elements, if a value is assigned by the XPath expression, then one of the four basic XPath types will be returned: Boolean, string, number, or node set.</span></span> <span data-ttu-id="2e41e-116">Cuando se asigna un valor mediante un cuerpo de plantilla que no está vacío, se devuelve un tipo de dato que no es de XPath, que será un fragmento del árbol de resultados.</span><span class="sxs-lookup"><span data-stu-id="2e41e-116">When the value is given by using a non-empty template body, then a non-XPath data type is returned, and that will be a result tree fragment.</span></span>

<span data-ttu-id="2e41e-117">Cuando se enlaza una variable a un fragmento del árbol de resultados en lugar de uno de los cuatro tipos de datos básicos de XPath, esta es la única vez que una consulta XPath devuelve un tipo que no pertenece a uno de los cuatro tipos de objetos de XPath.</span><span class="sxs-lookup"><span data-stu-id="2e41e-117">When a variable is bound to a result tree fragment instead of one of the four basic XPath data types, this is the only time that an XPath query returns a type that is not one of the four XPath object types.</span></span> <span data-ttu-id="2e41e-118">Los fragmentos del árbol de resultados y el comportamiento de estos se analizan en la [especificación del consorcio W3C](https://www.w3.org/TR/xslt-10/), [de la sección 11.1, Fragmentos de árboles de resultados](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments), a la [sección 11.6, Cómo pasar parámetros a plantillas](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates).</span><span class="sxs-lookup"><span data-stu-id="2e41e-118">Result tree fragments and their behavior are discussed in the [World Wide Web Consortium (W3C) specification](https://www.w3.org/TR/xslt-10/), [section 11.1 Result Tree Fragments](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments) through [section 11.6 Passing Parameters to Templates](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates).</span></span> <span data-ttu-id="2e41e-119">Además, en la [sección 1, Introducción](https://www.w3.org/TR/xslt-10/#section-Introduction), se analiza la forma en que las plantillas pueden contener elementos del espacio de nombres XSLT que devuelven o crean fragmentos de árboles de resultados.</span><span class="sxs-lookup"><span data-stu-id="2e41e-119">Also, [section 1 Introduction](https://www.w3.org/TR/xslt-10/#section-Introduction) discusses how templates can contain elements from the XSLT namespace that return or create result tree fragments.</span></span>

<span data-ttu-id="2e41e-120">En teoría, un fragmento del árbol de resultados se comporta como un conjunto de nodos con solo un nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="2e41e-120">A result tree fragment, in concept, behaves like a node set with nothing more than a single root node.</span></span> <span data-ttu-id="2e41e-121">Sin embargo, el resto de los nodos devueltos son nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="2e41e-121">However, the rest of the nodes returned are child nodes.</span></span> <span data-ttu-id="2e41e-122">Para ver los nodos secundarios mediante programación, copie el resultado del fragmento del árbol de resultados utilizando el elemento `<xsl:copy-of>`.</span><span class="sxs-lookup"><span data-stu-id="2e41e-122">To programmatically see the child nodes, copy the result tree fragment to the result tree using the `<xsl:copy-of>` element.</span></span> <span data-ttu-id="2e41e-123">Cuando se realiza la copia, todos los nodos secundarios se copian también en el árbol de resultados, en secuencia.</span><span class="sxs-lookup"><span data-stu-id="2e41e-123">When the copy-of is performed, all the child nodes are also copied to the result tree in sequence.</span></span> <span data-ttu-id="2e41e-124">Hasta que no se utilice `copy` o `copy-of`, un fragmento del árbol de resultados no forma parte del árbol de resultados o del resultado de la transformación.</span><span class="sxs-lookup"><span data-stu-id="2e41e-124">Until a `copy` or `copy-of` is used, a result tree fragment is not part of the result tree or the output from the transformation.</span></span>

<span data-ttu-id="2e41e-125">Para iterar por los nodos devueltos de un fragmento del árbol de resultados, se utiliza <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="2e41e-125">To iterate over the returned nodes of a result tree fragment, an <xref:System.Xml.XPath.XPathNavigator> is used.</span></span> <span data-ttu-id="2e41e-126">En el siguiente ejemplo de código se muestra cómo crear un fragmento del árbol de resultados en una hoja de estilos mediante una llamada a la función con un parámetro `fragment`, que contiene XML.</span><span class="sxs-lookup"><span data-stu-id="2e41e-126">The following code sample shows how to create a result tree fragment within a style sheet by calling the function with a parameter `fragment`, which contains XML.</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:var name="fragment">
        <node1>
            <node2/>
        </node1>
    <xsl:var>

  <msxsl:script language="C#" implements-prefix="user">
    function NodeFragment(XPathNavigator nav)
    {
      if (nav.HasSelection == false)
        XPathNavigator.MoveToNext();
      return;
    }
  </msxsl:script>

    <xsl:template match="/">
            <xsl:value-of select="user:NodeFragment(msxml:node-set($fragment))"/>
    </xsl:template>
</xsl:stylesheet>
```

<span data-ttu-id="2e41e-127">Este es otro ejemplo que muestra una variable, que es un RTF, y, por tanto, un tipo de fragmento del árbol de resultados, que no se convierte en un conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-127">Here is another sample showing a variable, which is in Rich Text Format (RTF), and hence, a type of result tree fragment, that is not converted to a node set.</span></span> <span data-ttu-id="2e41e-128">En lugar de ello, se pasa a una función de scripts y <xref:System.Xml.XPath.XPathNavigator> se utiliza para navegar por los nodos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-128">Instead, it is passed to a script function, and the <xref:System.Xml.XPath.XPathNavigator> is used to navigate over the nodes.</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNavigator nav)
    {
        bool b = nav.MoveToFirstChild();
        if (b)
            return nav.Value;
        else
            return "Does not exist";
    }

]]>

</msxsl:script>

<xsl:template match="/">
    <first_book>
        <xsl:value-of select="user:func($node-fragment)"/>
    </first_book>
</xsl:template>

</xsl:stylesheet>
```

<span data-ttu-id="2e41e-129">El resultado de transformar cualquier XML con esta hoja de estilos se muestra en la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="2e41e-129">The result of transforming any XML with this style sheet is shown in the following output.</span></span>

## <a name="output"></a><span data-ttu-id="2e41e-130">Salida</span><span class="sxs-lookup"><span data-stu-id="2e41e-130">Output</span></span>

```xml
<first_book xmlns:user="urn:books">Book1</first_book>
```

<span data-ttu-id="2e41e-131">Tal y como se ha indicado anteriormente, la función `node-set` permite convertir un fragmento del árbol de resultados en un conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-131">As stated above, the `node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="2e41e-132">El conjunto de nodos resultante siempre contiene un único nodo, que es el nodo raíz del árbol.</span><span class="sxs-lookup"><span data-stu-id="2e41e-132">The resulting node always contains a single node that is the root node of the tree.</span></span> <span data-ttu-id="2e41e-133">Si convierte un fragmento del árbol de resultados en un conjunto de nodos, puede utilizarlo en cualquier lugar en el que se puede utilizar un conjunto de nodos normal, como en una instrucción for-each o en el valor de un atributo `select`.</span><span class="sxs-lookup"><span data-stu-id="2e41e-133">If you convert a result tree fragment to a node set, then you can use it anywhere a regular node set is used, such as in a for-each statement or in the value of a `select` attribute.</span></span> <span data-ttu-id="2e41e-134">En las siguientes líneas de código se muestra el fragmento que se ha convertido en un conjunto de nodos y que se ha utilizado como un conjunto de nodos:</span><span class="sxs-lookup"><span data-stu-id="2e41e-134">The following lines of code show the fragment being converted to a node set and used as a node set:</span></span>

`<xsl:for-each select="msxsl:node-set($node-fragment)">`

`<xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>`

<span data-ttu-id="2e41e-135">Cuando un fragmento se convierte en un conjunto de nodos, ya no puede utilizar <xref:System.Xml.XPath.XPathNavigator> para navegar por el mismo.</span><span class="sxs-lookup"><span data-stu-id="2e41e-135">When a fragment is converted to a node set, you no longer use the <xref:System.Xml.XPath.XPathNavigator> to navigate over it.</span></span> <span data-ttu-id="2e41e-136">En el caso de un conjunto de nodos, se utiliza <xref:System.Xml.XPath.XPathNodeIterator> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2e41e-136">For a node set, you use the <xref:System.Xml.XPath.XPathNodeIterator> instead.</span></span>

<span data-ttu-id="2e41e-137">En el ejemplo siguiente, `$var` es una variable que es un árbol de nodos en la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-137">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="2e41e-138">La instrucción for-each, combinada con la función `node-set` permite que el usuario itere por este árbol como un conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="2e41e-138">The for-each statement, combined with the `node-set` function, allows the user to iterate over this tree as a node set.</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:variable name="states">
        <node1>AL</node1>
        <node1>CA</node1>
        <node1>CO</node1>
        <node1>WA</node1>
    </xsl:variable>

    <xsl:template match="/">
            <xsl:for-each select="msxsl:node-set($states)"/>
    </xsl:template>
</xsl:stylesheet>
```

<span data-ttu-id="2e41e-139">Este es otro ejemplo que muestra una variable, que es un RTF, y, por lo tanto, un tipo de fragmento de nodo, que se convierte en un conjunto de nodos antes de que se pase a una función de scripts como XPathNodeIterator.</span><span class="sxs-lookup"><span data-stu-id="2e41e-139">Here is another example of a variable that is in RTF, and hence of type result tree fragment, that is converted to a node set before being passed to a script function as XPathNodeIterator.</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNodeIterator it)
    {
        it.MoveNext();
        return it.Current.Value;
        //it.Current returns XPathNavigator positioned on the current node
    }

]]>

</msxsl:script>
<xsl:template match="/">
    <books>
        <xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>
    </books>
</xsl:template>

</xsl:stylesheet>
```

<span data-ttu-id="2e41e-140">Lo siguiente es el resultado de transformar XML con esta hoja de estilos:</span><span class="sxs-lookup"><span data-stu-id="2e41e-140">The following is the result of transforming XML with this style sheet:</span></span>

```xml
<books xmlns:user="urn:books">Book1Book2Book3Book4</books>
```

## <a name="see-also"></a><span data-ttu-id="2e41e-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e41e-141">See also</span></span>

- <xref:System.Xml.XPath.XPathNodeIterator>
- [<span data-ttu-id="2e41e-142">Transformaciones XSLT con la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="2e41e-142">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="2e41e-143">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="2e41e-143">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
