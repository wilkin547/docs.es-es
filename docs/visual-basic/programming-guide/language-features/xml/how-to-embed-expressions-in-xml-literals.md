---
description: 'Más información acerca de cómo: incrustar expresiones en literales XML (Visual Basic)'
title: Procedimiento para insertar expresiones en literales XML
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 18bc6164c4466532956f1a5df70c1ff2a8dbbfd5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480055"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="4511a-103">Cómo: Incrustar expresiones en literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4511a-103">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>

<span data-ttu-id="4511a-104">Puede combinar literales XML con expresiones incrustadas para crear un documento, fragmento o elemento XML que contenga contenido creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4511a-104">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="4511a-105">En los siguientes ejemplos se muestra cómo utilizar expresiones incrustadas para rellenar el contenido de los elementos, los atributos y los nombres de elemento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4511a-105">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="4511a-106">La sintaxis de una expresión incrustada es `<%=` `exp` `%>` , que es la misma sintaxis que utiliza ASP.net.</span><span class="sxs-lookup"><span data-stu-id="4511a-106">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that ASP.NET uses.</span></span> <span data-ttu-id="4511a-107">Para obtener más información, vea [expresiones incrustadas en XML](embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4511a-107">For more information, see [Embedded Expressions in XML](embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="4511a-108">También puede usar las [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="4511a-108">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="4511a-109">Para obtener más información, vea <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="4511a-109">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="4511a-110">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4511a-110">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="4511a-111">Para insertar texto como contenido de elemento</span><span class="sxs-lookup"><span data-stu-id="4511a-111">To insert text as element content</span></span>  
  
- <span data-ttu-id="4511a-112">En el ejemplo siguiente se muestra cómo insertar el texto contenido en la `contactName` variable entre los elementos de nombre de apertura y de cierre.</span><span class="sxs-lookup"><span data-stu-id="4511a-112">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="4511a-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="4511a-113">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="4511a-114">Para insertar texto como un valor de atributo</span><span class="sxs-lookup"><span data-stu-id="4511a-114">To insert text as an attribute value</span></span>  
  
- <span data-ttu-id="4511a-115">En el ejemplo siguiente se muestra cómo insertar el texto contenido en la `phoneType` variable como el valor del `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="4511a-115">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="4511a-116">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="4511a-116">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="4511a-117">Para insertar texto para un nombre de elemento</span><span class="sxs-lookup"><span data-stu-id="4511a-117">To insert text for an element name</span></span>  
  
- <span data-ttu-id="4511a-118">En el ejemplo siguiente se muestra cómo insertar el texto contenido en la `elementName` variable como el nombre de un elemento.</span><span class="sxs-lookup"><span data-stu-id="4511a-118">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="4511a-119">Al crear elementos mediante esta técnica, debe cerrarlos con la \</> etiqueta.</span><span class="sxs-lookup"><span data-stu-id="4511a-119">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="4511a-120">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="4511a-120">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4511a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4511a-121">See also</span></span>

- [<span data-ttu-id="4511a-122">Procedimiento para crear literales XML</span><span class="sxs-lookup"><span data-stu-id="4511a-122">How to: Create XML Literals</span></span>](how-to-create-xml-literals.md)
- [<span data-ttu-id="4511a-123">Expresiones insertadas en XML</span><span class="sxs-lookup"><span data-stu-id="4511a-123">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)
- [<span data-ttu-id="4511a-124">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4511a-124">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="4511a-125">XML</span><span class="sxs-lookup"><span data-stu-id="4511a-125">XML</span></span>](index.md)
