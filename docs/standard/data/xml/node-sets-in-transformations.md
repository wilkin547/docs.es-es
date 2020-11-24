---
title: Conjuntos de nodos en transformaciones
ms.date: 03/30/2017
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
ms.openlocfilehash: 72b3af5b471d73cc159dd700ddd29c4ffb5ea639
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830121"
---
# <a name="node-sets-in-transformations"></a>Conjuntos de nodos en transformaciones
Los conjuntos de nodos son uno de los cuatro tipos de datos básicos devueltos por las expresiones XPath. Un conjunto de nodos, que es una colección no ordenada de nodos sin duplicados, creada por orden de documento, puede asignarse a una variable en una hoja de estilos.  
  
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 Los conjuntos de nodos son uno de los cuatro tipos de datos básicos devueltos por las expresiones XPath. Un conjunto de nodos, que es una colección no ordenada de nodos sin duplicados, creada por orden de documento, puede asignarse a una variable en una hoja de estilos. Este conjunto de nodos, que es el resultado de una expresión XPath utilizada en un atributo `select` de una transformación, se comporta del mismo modo que un conjunto de nodos de DOM. Puede navegar por un conjunto de nodos mediante el conjunto de métodos que se muestra en [Navegación por un conjunto de nodos con XPathNavigator](node-set-navigation-using-xpathnavigator.md), a diferencia del fragmento del árbol de resultados, que utiliza <xref:System.Xml.XPath.XPathNodeIterator> para navegar.  
  
 En el siguiente ejemplo de código se muestra la forma de iterar por un conjunto de nodos cuando un elemento `variable` o `parameter` de una hoja de estilos se evalúa como un conjunto de nodos.  
  
## <a name="style-sheet"></a>Hoja de estilos  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
    <xsl:variable name="x" select="bookstore/book/title"></xsl:variable>  
  
    <xsl:template match="/">  
        <xsl:for-each select="$x">  
            ******  
            <xsl:value-of select="."></xsl:value-of>  
            ******  
        </xsl:for-each>  
    </xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="input"></a>Entrada  
  
```xml  
<bookstore>  
   <book style="autobiography">  
      <title>Seven Years in Trenton</title>  
   </book>  
  
   <book style="autobiography">  
      <title>Seven Years in Trenton2</title>  
   </book>  
  
   <book style="textbook">  
      <title>History of Trenton Vol 3</title>  
   </book>  
</bookstore>  
```  
  
## <a name="output"></a>Salida  
  
```output  
******  
Seven Years in Trenton  
******  
  
******  
Seven Years in Trenton2  
******  
  
******  
History of Trenton Vol 3  
******  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XPath.XPathNodeIterator>
- [Transformaciones XSLT con la clase XslTransform](xslt-transformations-with-the-xsltransform-class.md)
- [La clase XslTransform implementa el procesador XSLT](xsltransform-class-implements-the-xslt-processor.md)
