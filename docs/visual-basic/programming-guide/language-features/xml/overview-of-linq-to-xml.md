---
title: Introducción a LINQ to XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 0481a140541a7f45c682c5150bc1c3d647de90bd
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266903"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Información general sobre LINQ to XML en Visual Basic
Visual Basic proporciona [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] compatibilidad a través de literales XML y propiedades de eje XML. Esto le permite usar una sintaxis familiar y conveniente para trabajar con XML en el código de Visual Basic. *Los literales XML* le permiten incluir XML directamente en el código. Las propiedades del *eje XML* permiten tener acceso a nodos secundarios, nodos descendientes y atributos de un literal XML. Para obtener más información, vea [Información general sobre literales XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) y Acceso a XML en Visual [Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]es una API de programación XML en memoria diseñada específicamente para aprovechar las ventajas de Language-Integrated Query (LINQ). Aunque puede llamar a las API LINQ directamente, solo Visual Basic le permite declarar literales XML y tener acceso directamente a las propiedades del eje XML.  
  
> [!NOTE]
> Los literales XML y las propiedades del eje XML no se admiten en el código declarativo de una página ASP.NET. Para usar las características XML de Visual Basic, coloque el código en una página de código subyacente en la aplicación ASP.NET.  
  
 [Botón de reproducción](./media/overview-of-linq-to-xml/play-video-icon-example.gif) Para obtener demostraciones de vídeo relacionadas, vea [¿Cómo puedo empezar a usar LINQ to XMLLINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) y Cómo puedo crear hojas de cálculo de [Excel con LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).
  
## <a name="creating-xml"></a>Creación de XML  
 Hay dos maneras de crear árboles XML en Visual Basic. Puede declarar un literal XML directamente en el código o puede usar las API LINQ para crear el árbol. Ambos procesos permiten que el código refleje la estructura final del árbol XML. Por ejemplo, en el ejemplo de código siguiente se crea un elemento XML:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Para obtener más información, vea [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Acceso y navegación por XML  
 Visual Basic proporciona propiedades de eje XML para tener acceso y navegar por las estructuras XML. Estas propiedades permiten tener acceso a elementos y atributos XML especificando los nombres de elementos secundarios XML. Como alternativa, puede llamar explícitamente a los métodos LINQ para navegar y localizar elementos y atributos. Por ejemplo, en el ejemplo de código siguiente se utilizan propiedades de eje XML para hacer referencia a los atributos y elementos secundarios de un elemento XML. En el ejemplo de código se usa una consulta LINQ para recuperar elementos secundarios y generarlos como elementos XML, realizando eficazmente una transformación.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Para obtener más información, vea [Acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 Visual Basic permite especificar un alias para un `Imports` espacio de nombres XML global mediante la instrucción. En el ejemplo siguiente `Imports` se muestra cómo utilizar la instrucción para importar un espacio de nombres XML:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 Puede usar un alias de espacio de nombres XML al tener acceso a las propiedades del eje XML y declarar literales XML para documentos y elementos XML.  
  
 Puede recuperar <xref:System.Xml.Linq.XNamespace> un objeto para un prefijo de espacio de nombres determinado mediante el [operador GetXmlNamespace](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Para obtener más información, vea [Imports (instrucción) (espacio de nombres XML).](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Uso de espacios de nombres XML en literales XML  
 En el ejemplo siguiente <xref:System.Xml.Linq.XElement> se muestra cómo `ns`crear un objeto que utiliza el espacio de nombres global:  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 El compilador de Visual Basic traduce literales XML que contienen alias de espacio de nombres `xmlns` XML en código equivalente que usa la notación XML para usar espacios de nombres XML, con el atributo. Cuando se compila, el código del ejemplo de la sección anterior genera esencialmente el mismo código ejecutable que en el ejemplo siguiente:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Uso de espacios de nombres XML en propiedades de eje XML  
 Los espacios de nombres XML declarados en literales XML no están disponibles para su uso en propiedades de eje XML. Sin embargo, los espacios de nombres globales se pueden usar con las propiedades del eje XML. Use dos puntos para separar el prefijo de espacio de nombres XML del nombre del elemento local. El siguiente es un ejemplo:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>Consulte también

- [Xml](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
