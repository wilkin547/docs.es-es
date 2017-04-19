---
title: "Cómo: detectar errores (Visual Basic) de análisis | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0c4ba619d1f269352b3288f6cadf3b6f37a0dc2d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-catch-parsing-errors-visual-basic"></a>Cómo: detectar errores (Visual Basic) de análisis
En este tema se describe cómo detectar XML no válido o mal formado.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]se implementa utilizando <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> Si se pasa XML no válido o mal formado a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], subyacente <xref:System.Xml.XmlReader>clase producirá una excepción.</xref:System.Xml.XmlReader> Los diferentes métodos que analizan XML, como <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, no detectan la excepción; a continuación, se puede detectar la excepción mediante la aplicación.</xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
 Tenga en cuenta que no puede obtener errores de análisis si utiliza literales XML. El compilador de Visual Basic detectará errores de XML no válido o mal formado.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código intenta analizar XML no válido:  
  
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
  
 Cuando ejecuta este código, devuelve la siguiente excepción:  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 Para obtener información sobre las excepciones que puede esperar el <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, y <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>métodos para producir, consulte el <xref:System.Xml.XmlReader>documentación.</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>Vea también  
 [Analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
