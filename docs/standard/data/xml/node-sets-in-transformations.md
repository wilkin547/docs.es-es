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
# <a name="node-sets-in-transformations"></a><span data-ttu-id="8aa4e-102">Conjuntos de nodos en transformaciones</span><span class="sxs-lookup"><span data-stu-id="8aa4e-102">Node Sets in Transformations</span></span>
<span data-ttu-id="8aa4e-103">Los conjuntos de nodos son uno de los cuatro tipos de datos básicos devueltos por las expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-103">Node sets are one of four basic data types that are returned from XML Path Language (XPath) expressions.</span></span> <span data-ttu-id="8aa4e-104">Un conjunto de nodos, que es una colección no ordenada de nodos sin duplicados, creada por orden de documento, puede asignarse a una variable en una hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-104">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8aa4e-105">La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="8aa4e-106">Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="8aa4e-107">Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="8aa4e-108">Los conjuntos de nodos son uno de los cuatro tipos de datos básicos devueltos por las expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-108">Node sets are one of four basic data types that are returned from XPath expressions.</span></span> <span data-ttu-id="8aa4e-109">Un conjunto de nodos, que es una colección no ordenada de nodos sin duplicados, creada por orden de documento, puede asignarse a una variable en una hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-109">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span> <span data-ttu-id="8aa4e-110">Este conjunto de nodos, que es el resultado de una expresión XPath utilizada en un atributo `select` de una transformación, se comporta del mismo modo que un conjunto de nodos de DOM.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-110">This node set, which is a result of an XPath expression used in a `select` attribute in a transformation, has the same behavior as a node set from the XML Document Object Model (DOM).</span></span> <span data-ttu-id="8aa4e-111">Puede navegar por un conjunto de nodos mediante el conjunto de métodos que se muestra en [Navegación por un conjunto de nodos con XPathNavigator](node-set-navigation-using-xpathnavigator.md), a diferencia del fragmento del árbol de resultados, que utiliza <xref:System.Xml.XPath.XPathNodeIterator> para navegar.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-111">You can navigate a node set using a set of methods shown in [Node Set Navigation Using XPathNavigator](node-set-navigation-using-xpathnavigator.md), unlike a result tree fragment or result tree fragment, which uses the <xref:System.Xml.XPath.XPathNodeIterator> for navigation.</span></span>  
  
 <span data-ttu-id="8aa4e-112">En el siguiente ejemplo de código se muestra la forma de iterar por un conjunto de nodos cuando un elemento `variable` o `parameter` de una hoja de estilos se evalúa como un conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="8aa4e-112">The following code sample shows how to iterate over a node set when a `variable` or `parameter` element in a style sheet evaluates to a node set.</span></span>  
  
## <a name="style-sheet"></a><span data-ttu-id="8aa4e-113">Hoja de estilos</span><span class="sxs-lookup"><span data-stu-id="8aa4e-113">Style Sheet</span></span>  
  
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
  
## <a name="input"></a><span data-ttu-id="8aa4e-114">Entrada</span><span class="sxs-lookup"><span data-stu-id="8aa4e-114">Input</span></span>  
  
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
  
## <a name="output"></a><span data-ttu-id="8aa4e-115">Salida</span><span class="sxs-lookup"><span data-stu-id="8aa4e-115">Output</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8aa4e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8aa4e-116">See also</span></span>

- <xref:System.Xml.XPath.XPathNodeIterator>
- [<span data-ttu-id="8aa4e-117">Transformaciones XSLT con la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="8aa4e-117">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="8aa4e-118">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="8aa4e-118">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
