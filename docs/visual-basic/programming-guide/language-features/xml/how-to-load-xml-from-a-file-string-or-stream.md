---
title: "Cómo: cargar XML desde un archivo, cadena o secuencia (Visual Basic) | Documentos de Microsoft"
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
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 242c8b79cbe1329b6f53e9fd4e5495d4a157e08c
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Cómo: Cargar XML desde un archivo, cadena o secuencia (Visual Basic)
Puede crear [literales XML](../../../../visual-basic/language-reference/xml-literals/index.md) y rellenarlos con el contenido de un origen externo como un archivo, una cadena o una secuencia mediante varios métodos. Estos métodos se muestran en los ejemplos siguientes.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Para cargar XML desde un archivo  
  
-   Para rellenar un literal como XML un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>objeto desde un archivo, utilice el `Load` método.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Este método puede tomar una ruta de acceso de archivo, una secuencia de texto o una secuencia XML como entrada.  
  
     En el ejemplo de código siguiente se muestra el uso de la <xref:System.Xml.Linq.XDocument.Load%28System.String%29>método para rellenar un <xref:System.Xml.Linq.XDocument>objeto con XML de un archivo de texto.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%28System.String%29>  
  
     [!code-vb[VbXMLSamples&#43;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>Para cargar XML desde una cadena  
  
-   Para rellenar un literal como XML un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>objeto a partir de una cadena, puede utilizar el `Parse` método.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
     En el ejemplo de código siguiente se muestra el uso de la <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>método para rellenar un <xref:System.Xml.Linq.XDocument>objeto con XML de una cadena.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>  
  
     [!code-vb[VbXMLSamples&#47;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>Para cargar XML desde una secuencia  
  
-   Para rellenar un literal como XML un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>objeto a partir de una secuencia, puede usar el `Load` método o el <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>método.</xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
 En el ejemplo de código siguiente se muestra el uso de la <xref:System.Xml.Linq.XNode.ReadFrom%2A>método para rellenar un <xref:System.Xml.Linq.XDocument>objeto con XML de una secuencia XML.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
 [!code-vb[VbXMLSamples nº&46;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>   
 [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)

