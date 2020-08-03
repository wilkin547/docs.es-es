---
title: Procedimiento para detectar errores de análisis (C#)
description: En este ejemplo de LINQ to XML en C# se detecta XML con formato incorrecto o no válido. LINQ to XML usa XmlReader, que inicia una excepción para XML con formato incorrecto o no válido.
ms.date: 07/20/2015
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
ms.openlocfilehash: 0a891097322ef6acce062ea927692b01cc425e6c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105411"
---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="d0c4c-104">Procedimiento para detectar errores de análisis (C#)</span><span class="sxs-lookup"><span data-stu-id="d0c4c-104">How to catch parsing errors (C#)</span></span>
<span data-ttu-id="d0c4c-105">En este tema se describe cómo detectar XML no válido o mal formado.</span><span class="sxs-lookup"><span data-stu-id="d0c4c-105">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="d0c4c-106">se implementa con <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="d0c4c-106">is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="d0c4c-107">Si se pasa XML no válido o mal formado a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], la clase <xref:System.Xml.XmlReader> subyacente iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="d0c4c-107">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="d0c4c-108">Los diferentes métodos que analizan XML, como <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> no detectan la excepción; la excepción se propaga de forma que la aplicación pueda detectarla.</span><span class="sxs-lookup"><span data-stu-id="d0c4c-108">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0c4c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0c4c-109">Example</span></span>  
 <span data-ttu-id="d0c4c-110">El siguiente código intenta analizar XML no válido:</span><span class="sxs-lookup"><span data-stu-id="d0c4c-110">The following code tries to parse invalid XML:</span></span>  
  
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
  
 <span data-ttu-id="d0c4c-111">Cuando ejecuta este código, devuelve la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="d0c4c-111">When you run this code, it throws the following exception:</span></span>  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="d0c4c-112">Para obtener información acerca de las excepciones que puede esperar que devuelva los métodos <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, vea la documentación de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="d0c4c-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  