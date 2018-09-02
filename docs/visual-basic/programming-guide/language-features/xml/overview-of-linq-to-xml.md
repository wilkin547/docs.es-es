---
title: Información general sobre LINQ to XML en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 65df48112834be04dc8d3b62b8b163316b06c4a6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421248"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Información general sobre LINQ to XML en Visual Basic
Visual Basic ofrece compatibilidad con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] mediante literales XML y propiedades de eje XML. Esto le permite usar una sintaxis familiar y cómoda para trabajar con XML en el código de Visual Basic. *Literales XML* permiten incluir XML directamente en el código. *Propiedades de eje XML* permitirle acceso a los nodos secundarios, los nodos descendientes y los atributos de un literal XML. Para obtener más información, consulte [información general sobre literales de XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) y [acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se ha diseñado específicamente para aprovechar las ventajas de API de programación de un XML en memoria [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Aunque se puede llamar a la [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] directamente las API, solo Visual Basic permite declarar literales XML y tener acceso directamente a las propiedades de eje XML.  
  
> [!NOTE]
>  No se admiten literales XML y propiedades de eje XML en código declarativo en una página ASP.NET. Para usar características XML de Visual Basic, coloque el código en una página de código subyacente en la aplicación ASP.NET.  
  
 ![vínculo a vídeo](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") para demostraciones en vídeo relacionadas, vea [How Do I Get Started with LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) y [¿cómo puedo crear hojas de cálculo Excel mediante LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).  
  
## <a name="creating-xml"></a>Creación de XML  
 Hay dos maneras de crear árboles XML en Visual Basic. Se puede declarar un literal XML directamente en el código, o puede usar el [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] API para crear el árbol. Ambos procesos permiten que el código reflejar la estructura final del árbol XML. Por ejemplo, en el ejemplo de código siguiente se crea un elemento XML:  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Para obtener más información, consulte [crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Acceso y navegar por XML  
 Visual Basic proporciona propiedades de eje XML para obtener acceso y navegar por las estructuras XML. Estas propiedades permiten tener acceso a elementos y atributos XML especificando los nombres de elementos XML secundarios. Como alternativa, puede llamar explícitamente la [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] métodos para explorar y buscar elementos y atributos. Por ejemplo, el siguiente ejemplo de código utiliza propiedades de eje XML para hacer referencia a los atributos y elementos secundarios de un elemento XML. El ejemplo de código se usa un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consulta para recuperar los elementos secundarios y generarlos como elementos XML, realizando eficazmente una transformación.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Para obtener más información, consulte [acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 Visual Basic le permite especificar un alias para un espacio de nombres XML global utilizando el `Imports` instrucción. El ejemplo siguiente muestra cómo usar el `Imports` instrucción para importar un espacio de nombres XML:  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 Puede usar un alias de espacio de nombres XML al tener acceso a propiedades de eje XML y declarar literales XML para los elementos y documentos XML.  
  
 Puede recuperar un <xref:System.Xml.Linq.XNamespace> objeto para un prefijo de espacio de nombres determinado mediante el uso de la [GetXmlNamespace (operador)](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Uso de espacios de nombres XML en literales XML  
 El ejemplo siguiente muestra cómo crear un <xref:System.Xml.Linq.XElement> objeto que utiliza el espacio de nombres global `ns`:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 El compilador de Visual Basic traduce los literales XML que contienen un alias de espacio de nombres XML en el código equivalente que utiliza la notación de XML para usar espacios de nombres XML, con el `xmlns` atributo. Cuando se compila, el código de ejemplo de la sección anterior genera básicamente el mismo código ejecutable que el ejemplo siguiente:  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Uso de espacios de nombres XML en las propiedades de eje XML  
 Espacios de nombres XML declarados en literales XML no están disponibles para su uso en las propiedades de eje XML. Sin embargo, se pueden usar espacios de nombres globales con las propiedades de eje XML. Utilice dos puntos para separar el prefijo del espacio de nombres XML del nombre del elemento local. A continuación se muestra un ejemplo:  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>Vea también  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
