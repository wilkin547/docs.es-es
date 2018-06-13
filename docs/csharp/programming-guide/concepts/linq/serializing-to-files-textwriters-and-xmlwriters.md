---
title: Serializar en archivos, escritores de texto y escritores XML
ms.date: 07/20/2015
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
ms.openlocfilehash: 903e6f5b6a8cd88c140e6759136301a6305cee2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330215"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="08e01-102">Serializar en archivos, escritores de texto y escritores XML</span><span class="sxs-lookup"><span data-stu-id="08e01-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="08e01-103">Puede serializar árboles XML en <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="08e01-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="08e01-104">Puede serializar cualquier componente XML, entre los que se incluyen <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement>, en una cadena con el método `ToString`.</span><span class="sxs-lookup"><span data-stu-id="08e01-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="08e01-105">Si desea suprimir el formato al serializar en una cadena, puede usar el método <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="08e01-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="08e01-106">El comportamiento predeterminado al serializar en un archivo consiste en dar formato (aplicar sangría) al documento XML resultante.</span><span class="sxs-lookup"><span data-stu-id="08e01-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="08e01-107">Cuando aplica una sangría, en el árbol XML no se conservan los espacios en blanco más insignificantes.</span><span class="sxs-lookup"><span data-stu-id="08e01-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="08e01-108">Para serializar con formato, use una de las sobrecargas de los métodos siguientes que no toman <xref:System.Xml.Linq.SaveOptions> como argumento:</span><span class="sxs-lookup"><span data-stu-id="08e01-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="08e01-109">Si desea que la opción no aplique una sangría y conserve los espacios en blanco más insignificantes del árbol XML, use una de las sobrecargas de los métodos siguientes que toman <xref:System.Xml.Linq.SaveOptions> como argumento:</span><span class="sxs-lookup"><span data-stu-id="08e01-109">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="08e01-110">Por obtener ejemplos, vea el tema de referencia correspondiente.</span><span class="sxs-lookup"><span data-stu-id="08e01-110">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e01-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="08e01-111">See Also</span></span>  
 [<span data-ttu-id="08e01-112">Serializar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="08e01-112">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
