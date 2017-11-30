---
title: "Cómo: Detectar errores de análisis (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e541a004833ccd2aaecfd4ea13652b03a1270186
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="91934-102">Cómo: Detectar errores de análisis (C#)</span><span class="sxs-lookup"><span data-stu-id="91934-102">How to: Catch Parsing Errors (C#)</span></span>
<span data-ttu-id="91934-103">En este tema se describe cómo detectar XML no válido o mal formado.</span><span class="sxs-lookup"><span data-stu-id="91934-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="91934-104"> se implementa con <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="91934-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="91934-105">Si se pasa XML no válido o mal formado a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], la clase <xref:System.Xml.XmlReader> subyacente iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="91934-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="91934-106">Los diferentes métodos que analizan XML, como <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> no detectan la excepción; la excepción se propaga de forma que la aplicación pueda detectarla.</span><span class="sxs-lookup"><span data-stu-id="91934-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91934-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91934-107">Example</span></span>  
 <span data-ttu-id="91934-108">El siguiente código intenta analizar XML no válido:</span><span class="sxs-lookup"><span data-stu-id="91934-108">The following code tries to parse invalid XML:</span></span>  
  
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
  
 <span data-ttu-id="91934-109">Cuando ejecuta este código, devuelve la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="91934-109">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="91934-110">Para obtener información acerca de las excepciones que puede esperar que devuelva los métodos <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, vea la documentación de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="91934-110">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91934-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="91934-111">See Also</span></span>  
 [<span data-ttu-id="91934-112">Analizar XML (C#)</span><span class="sxs-lookup"><span data-stu-id="91934-112">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
