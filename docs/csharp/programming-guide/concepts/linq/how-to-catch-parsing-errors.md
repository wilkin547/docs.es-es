---
title: "Cómo: Detectar errores de análisis (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bf9469a328d80cca95fc5da2b143a494490089c2
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-catch-parsing-errors-c"></a>Cómo: Detectar errores de análisis (C#)
En este tema se describe cómo detectar XML no válido o mal formado.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] se implementa usando <xref:System.Xml.XmlReader>. Si se pasa a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] un XML no válido o con un formato incorrecto, la clase <xref:System.Xml.XmlReader> subyacente producirá una excepción. Los diferentes métodos que analizan XML, como <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, no detectan la excepción, que puede detectarla luego la aplicación.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código intenta analizar XML no válido:  
  
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
  
 Cuando ejecuta este código, devuelve la siguiente excepción:  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 Para obtener información sobre las excepciones que puede esperar que produzcan los métodos <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> y <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, consulte la documentación de <xref:System.Xml.XmlReader>.  
  
## <a name="see-also"></a>Vea también  
 [Parsing XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md) (Analizar XML [C#])
