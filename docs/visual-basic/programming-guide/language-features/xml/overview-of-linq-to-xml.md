---
title: "Información general de LINQ to XML en Visual Basic | Documentos de Microsoft"
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
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 508d4a97b0636f10607326eb35c4c5d8c7860873
ms.lasthandoff: 03/13/2017

---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Información general sobre LINQ to XML en Visual Basic
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]proporciona compatibilidad para [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] mediante literales XML y propiedades de eje XML. Esto le permite utilizar una sintaxis familiar y adecuada para trabajar con XML en su [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] código. *Literales XML* permiten incluir XML directamente en el código. *Propiedades de eje XML* permiten acceso a los nodos secundarios, los nodos descendientes y los atributos de un literal XML. Para obtener más información, consulte [información general sobre literales de XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) y [acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]está diseñado específicamente para aprovechar de API de programación de XML en memoria [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]. Aunque se puede llamar a la [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] API directamente, sólo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] permite declarar literales XML y tener acceso directamente a las propiedades de eje XML.  
  
> [!NOTE]
>  No se admiten literales XML y propiedades de eje XML en código declarativo en una página ASP.NET. Para usar características XML de Visual Basic, coloque el código en una página de código subyacente de la aplicación ASP.NET.  
  
 ![vínculo a vídeo](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") para demostraciones en vídeo relacionadas, vea [How Do I Get Started with LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) y [¿cómo puedo crear hojas de cálculo Excel utilizando LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).  
  
## <a name="creating-xml"></a>Crear XML  
 Hay dos maneras de crear árboles XML en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Se puede declarar un literal XML directamente en código o puede usar el [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] las API para crear el árbol. Ambos procesos permiten que el código refleje la estructura final del árbol XML. Por ejemplo, en el ejemplo de código siguiente se crea un elemento XML:  
  
 [!code-vb[VbXmlSamples&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Para obtener más información, consulte [crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Obtener acceso y navegar en XML  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona propiedades de eje XML para obtener acceso y navegar por las estructuras XML. Estas propiedades permiten tener acceso a elementos y atributos XML especificando los nombres de elemento XML secundario. Como alternativa, se puede llamar explícitamente el [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] métodos para explorar y buscar elementos y atributos. Por ejemplo, en el ejemplo de código siguiente se utiliza propiedades de eje XML para hacer referencia a los atributos y elementos secundarios de un elemento XML. El ejemplo de código se usa un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consulta para recuperar los elementos secundarios y generarlos como elementos XML, realizando eficazmente una transformación.  
  
 [!code-vb[VbXmlSamples Nº&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Para obtener más información, consulte [acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]permite especificar un alias para un espacio de nombres XML global utilizando la `Imports` instrucción. En el ejemplo siguiente se muestra cómo utilizar el `Imports` instrucción para importar un espacio de nombres XML:  
  
 [!code-vb[1 VbXMLSamples](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 Puede utilizar un alias de espacio de nombres XML cuando se tiene acceso a propiedades de eje XML y declara literales XML para elementos y documentos XML.  
  
 Puede recuperar un <xref:System.Xml.Linq.XNamespace>objeto para un prefijo de espacio de nombres determinado mediante el uso de la [GetXmlNamespace (operador)](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).</xref:System.Xml.Linq.XNamespace>  
  
 Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Uso de espacios de nombres XML en literales XML  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Xml.Linq.XElement>objeto que utiliza el espacio de nombres global `ns`:</xref:System.Xml.Linq.XElement>  
  
 [!code-vb[VbXMLSamples&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 El [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador traduce los literales XML que contienen los alias de espacio de nombres XML en código equivalente que utiliza la notación XML para usar espacios de nombres XML con el `xmlns` atributo. Cuando se compila, el código de ejemplo de la sección anterior genera básicamente el mismo código ejecutable que el ejemplo siguiente:  
  
 [!code-vb[VbXMLSamples&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Uso de espacios de nombres XML en Propiedades de eje XML  
 Espacios de nombres XML declarados en literales XML no están disponibles para su uso en las propiedades de eje XML. Sin embargo, los espacios de nombres globales se pueden utilizar con las propiedades de eje XML. Utilice un coma para separar el prefijo del espacio de nombres XML del nombre del elemento local. A continuación se muestra un ejemplo:  
  
 [!code-vb[VbXMLSamples Nº&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>Vea también  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
