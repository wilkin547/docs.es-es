---
title: Procesamiento de datos XML utilizando LINQ to XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 059d6b9d-63f7-4011-9ba8-8406f0bbae7d
ms.openlocfilehash: f45c5c9dccd2c1e8bdd67000a8b2f22425822ac9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710471"
---
# <a name="process-xml-data-using-linq-to-xml"></a><span data-ttu-id="79338-102">Procesamiento de datos XML utilizando LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="79338-102">Process XML Data Using LINQ to XML</span></span>
<span data-ttu-id="79338-103">LINQ to XML es el nuevo modelo que incorpora .NET Framework versión 3.5 para el procesamiento de datos XML.</span><span class="sxs-lookup"><span data-stu-id="79338-103">LINQ to XML is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="79338-104">LINQ to XML permite a los desarrolladores hacer con XML todo aquello que podrían esperar: consultar, modificar, crear, guardar y serializar documentos XML.</span><span class="sxs-lookup"><span data-stu-id="79338-104">LINQ to XML allows developers to do everything they would expect with XML data: querying, modifying, creating, saving, and serializing XML documents.</span></span> <span data-ttu-id="79338-105">Las principales ventajas son la posibilidad de realizar consultas y de crear documentos XML.</span><span class="sxs-lookup"><span data-stu-id="79338-105">The real advantages lie in the query and creation capabilities.</span></span>  
  
 <span data-ttu-id="79338-106">En LINQ to XML, las consultas son concisas y expresivas, ya que utilizan una sintaxis más parecida a SQL en comparación con XPath o XQuery.</span><span class="sxs-lookup"><span data-stu-id="79338-106">Queries in LINQ to XML are succinct and expressive, using syntax more similar to SQL than to XPath or XQuery.</span></span> <span data-ttu-id="79338-107">Dado que los resultados de las consultas se pueden obtener como colecciones de elementos o atributos que, a su vez, se puede utilizar como parámetros para objetos XElement, es posible transformar árboles XML con facilidad de una forma a otra.</span><span class="sxs-lookup"><span data-stu-id="79338-107">Because query results can be returned as collections of elements or attributes and can be used as parameters for XElement objects, XML trees can be easily transformed from one shape to another.</span></span>  
  
 <span data-ttu-id="79338-108">LINQ to XML aprovecha la tecnología Language-Integrated Query (LINQ) de .NET Framework versión  3.5.</span><span class="sxs-lookup"><span data-stu-id="79338-108">LINQ to XML leverages the language-integrated query (LINQ) technology in the .NET Framework version 3.5.</span></span> <span data-ttu-id="79338-109">LINQ extiende la sintaxis de los lenguajes C# y Visual Basic para ofrecer una serie de funcionalidades de consulta que se pueden expandir prácticamente a cualquier almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="79338-109">LINQ extends the language syntax of C# and Visual Basic to provide powerful query capabilities that can be extended to potentially any data store.</span></span>  
  
 <span data-ttu-id="79338-110">Para leer una explicación detallada de su uso, vea [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) y [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="79338-110">For a detailed discussion of its use, see [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="79338-111">Para ver una introducción al marco LINQ, consulte [Language Integrated Query (LINQ) (C#)](../../../csharp/programming-guide/concepts/linq/index.md) o [Language-Integrated Query (LINQ) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="79338-111">For an overview of the LINQ framework, see [Language-Integrated Query (LINQ) - C#](../../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79338-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="79338-112">See also</span></span>

- <xref:System.Xml.Linq>
- <xref:System.Linq>
- [<span data-ttu-id="79338-113">LINQ to XML frente a DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="79338-113">LINQ to XML vs. DOM (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/linq-to-xml-vs-dom.md)
- [<span data-ttu-id="79338-114">LINQ to XML frente a DOM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79338-114">LINQ to XML vs. DOM (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-dom.md)
- [<span data-ttu-id="79338-115">LINQ to XML frente a otras tecnologías XML (C#)</span><span class="sxs-lookup"><span data-stu-id="79338-115">LINQ to XML vs. Other XML Technologies (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
- [<span data-ttu-id="79338-116">LINQ to XML frente a otras tecnologías XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79338-116">LINQ to XML vs. Other XML Technologies (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
