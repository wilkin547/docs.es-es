---
title: 'Cómo: Incrustar expresiones en literales XML'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 2e8dd10b334b0271e3c9de11ed155c9d5d7aae48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332942"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="b76d6-102">Cómo: Incrustar expresiones en literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b76d6-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="b76d6-103">Puede combinar literales XML con expresiones incrustadas para crear un documento, fragmento o elemento XML que contenga contenido creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b76d6-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="b76d6-104">En los siguientes ejemplos se muestra cómo utilizar expresiones incrustadas para rellenar el contenido de los elementos, los atributos y los nombres de elemento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b76d6-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="b76d6-105">La sintaxis de una expresión incrustada es `<%=` `exp` `%>`, que es la misma sintaxis que utiliza ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b76d6-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that ASP.NET uses.</span></span> <span data-ttu-id="b76d6-106">Para obtener más información, vea [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b76d6-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="b76d6-107">También puede usar el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear objetos de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b76d6-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="b76d6-108">Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="b76d6-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b76d6-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="b76d6-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="b76d6-110">Para insertar texto como contenido de elemento</span><span class="sxs-lookup"><span data-stu-id="b76d6-110">To insert text as element content</span></span>  
  
- <span data-ttu-id="b76d6-111">En el ejemplo siguiente se muestra cómo insertar el texto contenido en la variable `contactName` entre los elementos de nombre de apertura y de cierre.</span><span class="sxs-lookup"><span data-stu-id="b76d6-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="b76d6-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b76d6-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="b76d6-113">Para insertar texto como un valor de atributo</span><span class="sxs-lookup"><span data-stu-id="b76d6-113">To insert text as an attribute value</span></span>  
  
- <span data-ttu-id="b76d6-114">En el ejemplo siguiente se muestra cómo insertar el texto contenido en la variable `phoneType` como el valor del atributo `type`.</span><span class="sxs-lookup"><span data-stu-id="b76d6-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="b76d6-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b76d6-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="b76d6-116">Para insertar texto para un nombre de elemento</span><span class="sxs-lookup"><span data-stu-id="b76d6-116">To insert text for an element name</span></span>  
  
- <span data-ttu-id="b76d6-117">En el ejemplo siguiente se muestra cómo insertar el texto contenido en la variable `elementName` como el nombre de un elemento.</span><span class="sxs-lookup"><span data-stu-id="b76d6-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="b76d6-118">Al crear elementos mediante esta técnica, debe cerrarlos con la etiqueta \</>.</span><span class="sxs-lookup"><span data-stu-id="b76d6-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="b76d6-119">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b76d6-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b76d6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b76d6-120">See also</span></span>

- [<span data-ttu-id="b76d6-121">Crear literales XML</span><span class="sxs-lookup"><span data-stu-id="b76d6-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [<span data-ttu-id="b76d6-122">Expresiones incrustadas en XML</span><span class="sxs-lookup"><span data-stu-id="b76d6-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="b76d6-123">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b76d6-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="b76d6-124">XML</span><span class="sxs-lookup"><span data-stu-id="b76d6-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
