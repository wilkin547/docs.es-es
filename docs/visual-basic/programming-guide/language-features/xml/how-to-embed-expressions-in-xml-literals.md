---
title: Procedimiento Incrustar expresiones en literales XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 6ecb6a5d684badba68f4c224d5359ea428cfbbf2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968717"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="66200-102">Procedimiento Incrustar expresiones en literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66200-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="66200-103">Literales XML se pueden combinar con expresiones incrustadas para crear un documento XML, fragmento o elemento que contiene el contenido creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="66200-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="66200-104">Los ejemplos siguientes muestran cómo utilizar expresiones incrustadas para rellenar los nombres de elementos, atributos y contenido del elemento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="66200-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="66200-105">La sintaxis de una expresión incrustada es `<%=` `exp` `%>`, que es la misma sintaxis que [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] usa.</span><span class="sxs-lookup"><span data-stu-id="66200-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="66200-106">Para obtener más información, consulte [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="66200-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="66200-107">También puede usar el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="66200-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="66200-108">Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="66200-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="66200-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="66200-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="66200-110">Para insertar texto como contenido del elemento</span><span class="sxs-lookup"><span data-stu-id="66200-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="66200-111">El ejemplo siguiente muestra cómo insertar el texto que se encuentra en la `contactName` variable entre los elementos de nombre de apertura y cierre.</span><span class="sxs-lookup"><span data-stu-id="66200-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="66200-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="66200-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="66200-113">Para insertar texto como un valor de atributo</span><span class="sxs-lookup"><span data-stu-id="66200-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="66200-114">El ejemplo siguiente muestra cómo insertar el texto que se encuentra en la `phoneType` variable como el valor de la `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="66200-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="66200-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="66200-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="66200-116">Para insertar texto para un nombre de elemento</span><span class="sxs-lookup"><span data-stu-id="66200-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="66200-117">El ejemplo siguiente muestra cómo insertar el texto que se encuentra en la `elementName` variable como el nombre de un elemento.</span><span class="sxs-lookup"><span data-stu-id="66200-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="66200-118">Al crear elementos mediante esta técnica, debe cerrarlos con la \</ > etiqueta.</span><span class="sxs-lookup"><span data-stu-id="66200-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="66200-119">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="66200-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="66200-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="66200-120">See also</span></span>
- [<span data-ttu-id="66200-121">Cómo: Crear literales XML</span><span class="sxs-lookup"><span data-stu-id="66200-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [<span data-ttu-id="66200-122">Expresiones incrustadas en XML</span><span class="sxs-lookup"><span data-stu-id="66200-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="66200-123">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66200-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="66200-124">XML</span><span class="sxs-lookup"><span data-stu-id="66200-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
