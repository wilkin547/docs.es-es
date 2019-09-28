---
title: Procedimiento Detectar errores de análisis (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
ms.openlocfilehash: a0c0749e8bc6d3fb1a71595778bfc5effaaf8533
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71352932"
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="2cd9e-102">Procedimiento Detectar errores de análisis (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cd9e-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="2cd9e-103">En este tema se describe cómo detectar XML no válido o mal formado.</span><span class="sxs-lookup"><span data-stu-id="2cd9e-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="2cd9e-104">se implementa con <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="2cd9e-104">is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="2cd9e-105">Si se pasa XML no válido o mal formado a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], la clase <xref:System.Xml.XmlReader> subyacente iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="2cd9e-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="2cd9e-106">Los diferentes métodos que analizan XML, como <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> no detectan la excepción; la excepción se propaga de forma que la aplicación pueda detectarla.</span><span class="sxs-lookup"><span data-stu-id="2cd9e-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="2cd9e-107">Tenga en cuenta que no puede obtener errores de análisis si utiliza literales XML.</span><span class="sxs-lookup"><span data-stu-id="2cd9e-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="2cd9e-108">El compilador de Visual Basic detectará errores de XML no válido o mal formado.</span><span class="sxs-lookup"><span data-stu-id="2cd9e-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cd9e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cd9e-109">Example</span></span>  
 <span data-ttu-id="2cd9e-110">El siguiente código intenta analizar XML no válido:</span><span class="sxs-lookup"><span data-stu-id="2cd9e-110">The following code tries to parse invalid XML:</span></span>  
  
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
  
 <span data-ttu-id="2cd9e-111">Cuando ejecuta este código, devuelve la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="2cd9e-111">When you run this code, it throws the following exception:</span></span>  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="2cd9e-112">Para obtener información acerca de las excepciones que puede esperar que devuelva los métodos <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, vea la documentación de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="2cd9e-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd9e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cd9e-113">See also</span></span>

- [<span data-ttu-id="2cd9e-114">Analizar XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cd9e-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
