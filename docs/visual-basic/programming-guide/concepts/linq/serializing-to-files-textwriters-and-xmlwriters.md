---
title: Serializar en archivos, escritores y XmlWriters3
ms.date: 07/20/2015
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
ms.openlocfilehash: d8b929ef02b8fd9c6a9f29ea997a754699a6e1c4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403568"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="47e85-102">Serializar en archivos, escritores de texto y escritores XML</span><span class="sxs-lookup"><span data-stu-id="47e85-102">Serializing to Files, TextWriters, and XmlWriters</span></span>

<span data-ttu-id="47e85-103">Puede serializar árboles XML en <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="47e85-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>

<span data-ttu-id="47e85-104">Puede serializar cualquier componente XML, entre los que se incluyen <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement>, en una cadena con el método `ToString`.</span><span class="sxs-lookup"><span data-stu-id="47e85-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>

<span data-ttu-id="47e85-105">Si desea suprimir el formato al serializar en una cadena, puede usar el método <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="47e85-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="47e85-106">El comportamiento predeterminado al serializar en un archivo consiste en formatear el documento XML resultante (aplicarle una sangría).</span><span class="sxs-lookup"><span data-stu-id="47e85-106">The default behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="47e85-107">Cuando aplica una sangría, en el árbol XML no se conservan los espacios en blanco más insignificantes.</span><span class="sxs-lookup"><span data-stu-id="47e85-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="47e85-108">Para serializar con formato, use una de las sobrecargas de los métodos siguientes que no toman <xref:System.Xml.Linq.SaveOptions> como argumento:</span><span class="sxs-lookup"><span data-stu-id="47e85-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="47e85-109">Si desea que la opción no aplique una sangría y conserve los espacios en blanco más insignificantes del árbol XML, use una de las sobrecargas de los métodos siguientes que toman <xref:System.Xml.Linq.SaveOptions> como argumento:</span><span class="sxs-lookup"><span data-stu-id="47e85-109">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="47e85-110">Por obtener ejemplos, vea el tema de referencia correspondiente.</span><span class="sxs-lookup"><span data-stu-id="47e85-110">For examples, see the appropriate reference topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="47e85-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="47e85-111">See also</span></span>

- [<span data-ttu-id="47e85-112">Serializar árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47e85-112">Serializing XML Trees (Visual Basic)</span></span>](serializing-xml-trees.md)
