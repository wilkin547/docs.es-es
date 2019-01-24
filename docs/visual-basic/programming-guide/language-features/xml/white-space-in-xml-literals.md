---
title: Espacio en blanco en literales XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 56466856bc70f4bde428f7087efdf4e71a50021f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689157"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="891ec-102">Espacio en blanco en literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="891ec-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="891ec-103">El compilador de Visual Basic incorpore solo los caracteres de espacio en blanco significativo de un literal XML cuando crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto.</span><span class="sxs-lookup"><span data-stu-id="891ec-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="891ec-104">No se incorporan los caracteres de espacios en blanco insignificantes.</span><span class="sxs-lookup"><span data-stu-id="891ec-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="891ec-105">Espacio en blanco significativo y no significativo</span><span class="sxs-lookup"><span data-stu-id="891ec-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="891ec-106">Caracteres de espacio en blanco en literales XML son significativos en sólo tres áreas:</span><span class="sxs-lookup"><span data-stu-id="891ec-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="891ec-107">Cuando se encuentran en un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="891ec-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="891ec-108">Cuando forman parte de un elemento contenido de texto y el texto también contiene otros caracteres.</span><span class="sxs-lookup"><span data-stu-id="891ec-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="891ec-109">Cuando se encuentran en una expresión incrustada para el contenido de texto de un elemento.</span><span class="sxs-lookup"><span data-stu-id="891ec-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="891ec-110">En caso contrario, el compilador trata los caracteres de espacio en blanco como insignificantes y no se incluye a continuación, en el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto para el literal.</span><span class="sxs-lookup"><span data-stu-id="891ec-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="891ec-111">Para incluir espacios en blanco insignificantes en un literal XML, use una expresión incrustada que contiene una cadena literal con el espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="891ec-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="891ec-112">Si el `xml:space` atributo aparece en un literal de elemento XML, el compilador de Visual Basic incluye el atributo en el <xref:System.Xml.Linq.XElement> objeto, pero agregar este atributo no cambia el modo en que el compilador trata los espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="891ec-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="891ec-113">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="891ec-113">Examples</span></span>  
 <span data-ttu-id="891ec-114">En el siguiente ejemplo contiene dos elementos XML, externos e internos.</span><span class="sxs-lookup"><span data-stu-id="891ec-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="891ec-115">Ambos elementos contienen espacios en blanco en su contenido de texto.</span><span class="sxs-lookup"><span data-stu-id="891ec-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="891ec-116">El espacio en blanco en el elemento exterior es insignificante, ya que contiene solo espacios en blanco y un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="891ec-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="891ec-117">El espacio en blanco en el elemento interno es significativo porque contiene espacios en blanco y texto.</span><span class="sxs-lookup"><span data-stu-id="891ec-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 <span data-ttu-id="891ec-118">Cuando se ejecuta, este código muestra el texto siguiente.</span><span class="sxs-lookup"><span data-stu-id="891ec-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="891ec-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="891ec-119">See also</span></span>
- [<span data-ttu-id="891ec-120">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="891ec-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
