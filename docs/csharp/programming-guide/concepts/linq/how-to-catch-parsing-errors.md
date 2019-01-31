---
title: Procedimiento para detectar errores de análisis (C#)
ms.date: 07/20/2015
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
ms.openlocfilehash: 2f56ca48278f9ad8b38f8564f54a379cc09f94ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515867"
---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="3d270-102">Procedimiento para detectar errores de análisis (C#)</span><span class="sxs-lookup"><span data-stu-id="3d270-102">How to: Catch Parsing Errors (C#)</span></span>
<span data-ttu-id="3d270-103">En este tema se describe cómo detectar XML no válido o mal formado.</span><span class="sxs-lookup"><span data-stu-id="3d270-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3d270-104">se implementa con <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="3d270-104">is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="3d270-105">Si se pasa XML no válido o mal formado a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], la clase <xref:System.Xml.XmlReader> subyacente iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="3d270-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="3d270-106">Los diferentes métodos que analizan XML, como <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> no detectan la excepción; la excepción se propaga de forma que la aplicación pueda detectarla.</span><span class="sxs-lookup"><span data-stu-id="3d270-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d270-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d270-107">Example</span></span>  
 <span data-ttu-id="3d270-108">El siguiente código intenta analizar XML no válido:</span><span class="sxs-lookup"><span data-stu-id="3d270-108">The following code tries to parse invalid XML:</span></span>  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 <span data-ttu-id="3d270-109">Cuando ejecuta este código, devuelve la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="3d270-109">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="3d270-110">Para obtener información acerca de las excepciones que puede esperar que devuelva los métodos <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, vea la documentación de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="3d270-110">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d270-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d270-111">See also</span></span>

- [<span data-ttu-id="3d270-112">Analizar XML (C#)</span><span class="sxs-lookup"><span data-stu-id="3d270-112">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
