---
title: Compatibilidad con la función msxsl:node-set()
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
ms.openlocfilehash: 30652d8cbaac333cc1cb35954742b16dc7c4764b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071994"
---
# <a name="support-for-the-msxslnode-set-function"></a><span data-ttu-id="6f629-102">Compatibilidad con la función msxsl:node-set()</span><span class="sxs-lookup"><span data-stu-id="6f629-102">Support for the msxsl:node-set() Function</span></span>
<span data-ttu-id="6f629-103">La función `msxsl:node-set` permite convertir un fragmento del árbol de resultados en un conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="6f629-103">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="6f629-104">El conjunto de nodos resultante siempre contiene un único nodo, que es el nodo raíz del árbol.</span><span class="sxs-lookup"><span data-stu-id="6f629-104">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f629-105">La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="6f629-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="6f629-106">Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="6f629-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="6f629-107">Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6f629-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="6f629-108">La función `msxsl:node-set` permite convertir un fragmento del árbol de resultados en un conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="6f629-108">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="6f629-109">El conjunto de nodos resultante siempre contiene un único nodo, que es el nodo raíz del árbol.</span><span class="sxs-lookup"><span data-stu-id="6f629-109">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f629-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f629-110">Example</span></span>  
 <span data-ttu-id="6f629-111">En el ejemplo siguiente, `$books` es una variable que es un árbol de nodos en la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="6f629-111">In the following example, `$books` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="6f629-112">La instrucción for-each, combinada con la función `node-set`, permite que el usuario itere por este árbol como un conjunto de nodos.</span><span class="sxs-lookup"><span data-stu-id="6f629-112">The for-each statement combined with the `node-set` function allows the user to iterate over this node tree as a node set.</span></span>  
  
## <a name="nodesetxsl"></a><span data-ttu-id="6f629-113">nodeset.xsl</span><span class="sxs-lookup"><span data-stu-id="6f629-113">nodeset.xsl</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">
                <author><xsl:value-of select="@author"/></author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a><span data-ttu-id="6f629-114">Salida</span><span class="sxs-lookup"><span data-stu-id="6f629-114">Output</span></span>  
 <span data-ttu-id="6f629-115">El resultado de la transformación es</span><span class="sxs-lookup"><span data-stu-id="6f629-115">The output of the transformation is</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f629-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f629-116">See also</span></span>

- [<span data-ttu-id="6f629-117">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="6f629-117">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
