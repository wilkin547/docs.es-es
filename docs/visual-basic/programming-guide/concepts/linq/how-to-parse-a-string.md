---
title: Procedimiento Analizar una cadena (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: b97ce93c1018ec48649ab8b259d5f1a07109b9fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956378"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="80c2b-102">Procedimiento Analizar una cadena (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80c2b-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="80c2b-103">En este tema se muestra cómo crear un árbol XML C#en.</span><span class="sxs-lookup"><span data-stu-id="80c2b-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80c2b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80c2b-104">Example</span></span>  
 <span data-ttu-id="80c2b-105">Puede analizar una cadena en Visual Basic mediante el `XElement.Parse` método.</span><span class="sxs-lookup"><span data-stu-id="80c2b-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="80c2b-106">Sin embargo, resulta más eficaz usar literales XML, tal como se muestra en el código siguiente, ya que dichos literales no sufren las mismas pérdidas de rendimiento que se producen al analizar XML de una cadena.</span><span class="sxs-lookup"><span data-stu-id="80c2b-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="80c2b-107">Mediante el uso de literales XML, solo puede copiar y pegar el archivo XML en el programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="80c2b-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80c2b-108">Analizar texto o cargar un documento XML de un archivo de texto es menos eficaz que la construcción funcional.</span><span class="sxs-lookup"><span data-stu-id="80c2b-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="80c2b-109">Si inicializa un árbol XML a partir de código, el uso de la construcción funcional consume menos tiempo de procesador que el análisis de texto.</span><span class="sxs-lookup"><span data-stu-id="80c2b-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="80c2b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="80c2b-110">See also</span></span>

- [<span data-ttu-id="80c2b-111">Analizar XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80c2b-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
