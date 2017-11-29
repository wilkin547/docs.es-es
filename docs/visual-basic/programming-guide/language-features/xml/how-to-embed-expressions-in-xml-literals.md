---
title: "Cómo: Incrustar expresiones en literales XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bef4662d69ca7ceddeb2641cbe265d93712c5d16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="31ed8-102">Cómo: Incrustar expresiones en literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31ed8-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="31ed8-103">Literales XML se pueden combinar con expresiones incrustadas para crear un documento XML, fragmento o elemento que incluye contenido creado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="31ed8-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="31ed8-104">Los ejemplos siguientes muestran cómo utilizar expresiones incrustadas para rellenar el contenido de los elementos, atributos y nombres de elementos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="31ed8-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="31ed8-105">La sintaxis para una expresión incrustada es `<%=` `exp` `%>`, que es la misma sintaxis que [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] utiliza.</span><span class="sxs-lookup"><span data-stu-id="31ed8-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="31ed8-106">Para obtener más información, consulte [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="31ed8-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="31ed8-107">También puede usar el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="31ed8-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="31ed8-108">Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="31ed8-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="31ed8-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="31ed8-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="31ed8-110">Para insertar texto como contenido del elemento</span><span class="sxs-lookup"><span data-stu-id="31ed8-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="31ed8-111">En el ejemplo siguiente se muestra cómo insertar el texto que se encuentra en la `contactName` variable entre los elementos de nombre de apertura y cierre.</span><span class="sxs-lookup"><span data-stu-id="31ed8-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     <span data-ttu-id="31ed8-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="31ed8-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="31ed8-113">Para insertar texto como un valor de atributo</span><span class="sxs-lookup"><span data-stu-id="31ed8-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="31ed8-114">En el ejemplo siguiente se muestra cómo insertar el texto que se encuentra en la `phoneType` variable como el valor de la `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="31ed8-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     <span data-ttu-id="31ed8-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="31ed8-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="31ed8-116">Para insertar texto para un nombre de elemento</span><span class="sxs-lookup"><span data-stu-id="31ed8-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="31ed8-117">En el ejemplo siguiente se muestra cómo insertar el texto que se encuentra en la `elementName` variable como el nombre de un elemento.</span><span class="sxs-lookup"><span data-stu-id="31ed8-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="31ed8-118">Al crear elementos mediante esta técnica, debe cerrarlos con la \</ > etiqueta.</span><span class="sxs-lookup"><span data-stu-id="31ed8-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     <span data-ttu-id="31ed8-119">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="31ed8-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="31ed8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="31ed8-120">See Also</span></span>  
 [<span data-ttu-id="31ed8-121">Crear literales XML</span><span class="sxs-lookup"><span data-stu-id="31ed8-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [<span data-ttu-id="31ed8-122">Expresiones incrustadas en XML</span><span class="sxs-lookup"><span data-stu-id="31ed8-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="31ed8-123">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31ed8-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="31ed8-124">XML</span><span class="sxs-lookup"><span data-stu-id="31ed8-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
