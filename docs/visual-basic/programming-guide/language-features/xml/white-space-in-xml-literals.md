---
description: 'Más información sobre: espacio en blanco en literales XML (Visual Basic)'
title: Espacio en blanco en literales XML
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 9b4134626c0ad1f7f4be2923573eb6058fa7687f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428121"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="5d4ee-103">Espacio en blanco en literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d4ee-103">White Space in XML Literals (Visual Basic)</span></span>

<span data-ttu-id="5d4ee-104">El compilador de Visual Basic incorpora solo los caracteres de espacio en blanco significativos de un literal XML cuando crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-104">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="5d4ee-105">No se incorporan los caracteres de espacio en blanco insignificantes.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-105">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="5d4ee-106">Espacio en blanco significativo e insignificante</span><span class="sxs-lookup"><span data-stu-id="5d4ee-106">Significant and Insignificant White Space</span></span>  

 <span data-ttu-id="5d4ee-107">Los caracteres de espacio en blanco de los literales XML solo son significativos en tres áreas:</span><span class="sxs-lookup"><span data-stu-id="5d4ee-107">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="5d4ee-108">Cuando se encuentran en un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-108">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="5d4ee-109">Cuando forman parte del contenido de texto de un elemento y el texto también contiene otros caracteres.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-109">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="5d4ee-110">Cuando están en una expresión incrustada para el contenido de texto de un elemento.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-110">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="5d4ee-111">De lo contrario, el compilador trata los caracteres de espacio en blanco como insignificantes y no incluye en el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto para el literal.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-111">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="5d4ee-112">Para incluir un espacio en blanco insignificante en un literal XML, use una expresión incrustada que contenga un literal de cadena con el espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-112">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d4ee-113">Si el `xml:space` atributo aparece en un literal de elemento XML, el compilador Visual Basic incluye el atributo en el <xref:System.Xml.Linq.XElement> objeto, pero al agregar este atributo no se cambia el modo en que el compilador trata los espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-113">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5d4ee-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5d4ee-114">Examples</span></span>  

 <span data-ttu-id="5d4ee-115">El ejemplo siguiente contiene dos elementos XML, Outer e Inner.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-115">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="5d4ee-116">Ambos elementos contienen espacios en blanco en el contenido de texto.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-116">Both elements contain white space in their text content.</span></span> <span data-ttu-id="5d4ee-117">El espacio en blanco del elemento exterior es insignificante porque solo contiene espacios en blanco y un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-117">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="5d4ee-118">El espacio en blanco del elemento interno es significativo porque contiene un espacio en blanco y texto.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-118">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="5d4ee-119">Cuando se ejecuta, este código muestra el texto siguiente.</span><span class="sxs-lookup"><span data-stu-id="5d4ee-119">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d4ee-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d4ee-120">See also</span></span>

- [<span data-ttu-id="5d4ee-121">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d4ee-121">Creating XML in Visual Basic</span></span>](creating-xml.md)
