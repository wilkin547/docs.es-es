---
title: Procedimiento Detectar errores (Visual Basic) de análisis
ms.date: 07/20/2015
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
ms.openlocfilehash: f438a247866fdea8935be2b881a77f97c152b98f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667094"
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a>Procedimiento Detectar errores (Visual Basic) de análisis
En este tema se describe cómo detectar XML no válido o mal formado.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se implementa con <xref:System.Xml.XmlReader>. Si se pasa XML no válido o mal formado a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], la clase <xref:System.Xml.XmlReader> subyacente iniciará una excepción. Los diferentes métodos que analizan XML, como <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> no detectan la excepción; la excepción se propaga de forma que la aplicación pueda detectarla.  
  
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
  
 Para obtener información acerca de las excepciones que puede esperar que devuelva los métodos <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, vea la documentación de <xref:System.Xml.XmlReader>.  
  
## <a name="see-also"></a>Vea también
- [Analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
