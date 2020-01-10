---
title: Fragmento del árbol de resultados en transformaciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df363480-ba02-4233-9ddf-8434e421c4f1
ms.openlocfilehash: 33d66b0a835be8bacab76ef9295ce8158385d8d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710263"
---
# <a name="result-tree-fragment-in-transformations"></a>Fragmento del árbol de resultados en transformaciones

> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.

 Los fragmentos del árbol de resultados, también conocidos como fragmentos de árboles de resultados, no son más que un tipo especial de conjuntos de nodos. Cualquier función que pueda realizar sobre un conjunto de nodos puede realizarla también sobre estos fragmentos. También puede convertir un fragmento del árbol de resultados en un conjunto de nodos utilizando la función `node-set()`, y podrá utilizar dicho fragmento posteriormente en cualquier lugar en el que puede utilizarse un conjunto de nodos.

 Un fragmento del árbol de resultados se crea como resultado de utilizar un elemento `<xsl:variable>` o `<xsl:param>` de una forma específica en una hoja de estilos. La sintaxis de los elementos `variable` y `parameter` es la siguiente:

```xml
<xsl:param name=Qname select= XPath Expression >
    template body
</xsl:param>

<xsl:variable name=Qname select=XPath Expression >
    template body
</xsl:variable>
```

En el caso del elemento `parameter`, el valor se asigna a (`Qname`) de varias formas. Puede asignar un valor predeterminado al parámetro mediante la devolución del contenido de la expresión XPath en el atributo `select` o asignándole el contenido del cuerpo de la plantilla.

En el caso del elemento `variable`, el valor se asigna también de varias formas. Puede asignar un valor mediante la devolución del contenido de la expresión XPath en el atributo `select` o asignándole el contenido del cuerpo de la plantilla.

Tanto para el elemento `parameter` como para el elemento `variable`, si se asigna un valor mediante la expresión XPath, se devolverá uno de los cuatro tipos básicos de XPath:tipo booleano, tipo de cadena, tipo numérico o tipo de conjunto de nodos. Cuando se asigna un valor mediante un cuerpo de plantilla que no está vacío, se devuelve un tipo de dato que no es de XPath, que será un fragmento del árbol de resultados.

Cuando se enlaza una variable a un fragmento del árbol de resultados en lugar de uno de los cuatro tipos de datos básicos de XPath, esta es la única vez que una consulta XPath devuelve un tipo que no pertenece a uno de los cuatro tipos de objetos de XPath. Los fragmentos del árbol de resultados y el comportamiento de estos se analizan en la [especificación del consorcio W3C](https://www.w3.org/TR/xslt-10/), [de la sección 11.1, Fragmentos de árboles de resultados](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments), a la [sección 11.6, Cómo pasar parámetros a plantillas](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates). Además, en la [sección 1, Introducción](https://www.w3.org/TR/xslt-10/#section-Introduction), se analiza la forma en que las plantillas pueden contener elementos del espacio de nombres XSLT que devuelven o crean fragmentos de árboles de resultados.

En teoría, un fragmento del árbol de resultados se comporta como un conjunto de nodos con solo un nodo raíz. Sin embargo, el resto de los nodos devueltos son nodos secundarios. Para ver los nodos secundarios mediante programación, copie el resultado del fragmento del árbol de resultados utilizando el elemento `<xsl:copy-of>`. Cuando se realiza la copia, todos los nodos secundarios se copian también en el árbol de resultados, en secuencia. Hasta que no se utilice `copy` o `copy-of`, un fragmento del árbol de resultados no forma parte del árbol de resultados o del resultado de la transformación.

Para iterar por los nodos devueltos de un fragmento del árbol de resultados, se utiliza <xref:System.Xml.XPath.XPathNavigator>. En el siguiente ejemplo de código se muestra cómo crear un fragmento del árbol de resultados en una hoja de estilos mediante una llamada a la función con un parámetro `fragment`, que contiene XML.

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

Este es otro ejemplo que muestra una variable, que es un RTF, y, por tanto, un tipo de fragmento del árbol de resultados, que no se convierte en un conjunto de nodos. En lugar de ello, se pasa a una función de scripts y <xref:System.Xml.XPath.XPathNavigator> se utiliza para navegar por los nodos.

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

El resultado de transformar cualquier XML con esta hoja de estilos se muestra en la siguiente salida.

## <a name="output"></a>Resultados

```xml
<first_book xmlns:user="urn:books">Book1</first_book>
```

Tal y como se ha indicado anteriormente, la función `node-set` permite convertir un fragmento del árbol de resultados en un conjunto de nodos. El conjunto de nodos resultante siempre contiene un único nodo, que es el nodo raíz del árbol. Si convierte un fragmento del árbol de resultados en un conjunto de nodos, puede utilizarlo en cualquier lugar en el que se puede utilizar un conjunto de nodos normal, como en una instrucción for-each o en el valor de un atributo `select`. En las siguientes líneas de código se muestra el fragmento que se ha convertido en un conjunto de nodos y que se ha utilizado como un conjunto de nodos:

`<xsl:for-each select="msxsl:node-set($node-fragment)">`

`<xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>`

Cuando un fragmento se convierte en un conjunto de nodos, ya no puede utilizar <xref:System.Xml.XPath.XPathNavigator> para navegar por el mismo. En el caso de un conjunto de nodos, se utiliza <xref:System.Xml.XPath.XPathNodeIterator> en su lugar.

En el ejemplo siguiente, `$var` es una variable que es un árbol de nodos en la hoja de estilos. La instrucción for-each, combinada con la función `node-set` permite que el usuario itere por este árbol como un conjunto de nodos.

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

Este es otro ejemplo que muestra una variable, que es un RTF, y, por lo tanto, un tipo de fragmento de nodo, que se convierte en un conjunto de nodos antes de que se pase a una función de scripts como XPathNodeIterator.

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

Lo siguiente es el resultado de transformar XML con esta hoja de estilos:

```xml
<books xmlns:user="urn:books">Book1Book2Book3Book4</books>
```

## <a name="see-also"></a>Vea también

- <xref:System.Xml.XPath.XPathNodeIterator>
- [Transformaciones XSLT con la clase XslTransform](xslt-transformations-with-the-xsltransform-class.md)
- [La clase XslTransform implementa el procesador XSLT](xsltransform-class-implements-the-xslt-processor.md)
