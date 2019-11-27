---
title: 'Cómo: Detectar errores de análisis'
ms.date: 07/20/2015
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
ms.openlocfilehash: 14c4f76c5f10616f9346084cda276e2862b2b41d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353346"
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="a484e-102">Cómo: detectar errores de análisis (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a484e-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="a484e-103">En este tema se describe cómo detectar XML no válido o mal formado.</span><span class="sxs-lookup"><span data-stu-id="a484e-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="a484e-104">se implementa con <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="a484e-104">is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="a484e-105">Si se pasa XML no válido o mal formado a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], la clase <xref:System.Xml.XmlReader> subyacente iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="a484e-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="a484e-106">Los diferentes métodos que analizan XML, como <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> no detectan la excepción; la excepción se propaga de forma que la aplicación pueda detectarla.</span><span class="sxs-lookup"><span data-stu-id="a484e-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="a484e-107">Tenga en cuenta que no puede obtener errores de análisis si utiliza literales XML.</span><span class="sxs-lookup"><span data-stu-id="a484e-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="a484e-108">El compilador de Visual Basic detectará errores de XML no válido o mal formado.</span><span class="sxs-lookup"><span data-stu-id="a484e-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a484e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a484e-109">Example</span></span>  
 <span data-ttu-id="a484e-110">El siguiente código intenta analizar XML no válido:</span><span class="sxs-lookup"><span data-stu-id="a484e-110">The following code tries to parse invalid XML:</span></span>  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 <span data-ttu-id="a484e-111">Cuando ejecuta este código, devuelve la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="a484e-111">When you run this code, it throws the following exception:</span></span>  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="a484e-112">Para obtener información acerca de las excepciones que puede esperar que devuelva los métodos <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, vea la documentación de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="a484e-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a484e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a484e-113">See also</span></span>

- [<span data-ttu-id="a484e-114">Analizar XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a484e-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
