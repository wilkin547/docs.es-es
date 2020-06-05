---
title: Introducción a LINQ to XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 044aca634f5a0aa6e557a7dd9c0e1de64e35dc15
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374660"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Información general sobre LINQ to XML en Visual Basic
Visual Basic proporciona compatibilidad con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] a través de los literales XML y las propiedades del eje XML. Esto le permite usar una sintaxis familiar y cómoda para trabajar con XML en el código de Visual Basic. Los *literales XML* permiten incluir XML directamente en el código. *Las propiedades del eje XML* permiten tener acceso a los nodos secundarios, nodos descendientes y atributos de un literal XML. Para obtener más información, vea [información general sobre literales XML](xml-literals-overview.md) y [acceso a XML en Visual Basic](accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]es una API de programación XML en memoria diseñada específicamente para aprovechar las ventajas de Language-Integrated Query (LINQ). Aunque puede llamar directamente a las API de LINQ, solo Visual Basic permite declarar literales XML y acceder directamente a las propiedades del eje XML.  
  
> [!NOTE]
> Los literales XML y las propiedades del eje XML no se admiten en el código declarativo de una página ASP.NET. Para usar Visual Basic características XML, coloque el código en una página de código subyacente en la aplicación ASP.NET.  
  
 [Botón reproducir](./media/overview-of-linq-to-xml/play-video-icon-example.gif) Para ver demostraciones de vídeo relacionadas, consulte [¿Cómo puedo empezar a trabajar con LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) y [Cómo creo hojas de cálculo de Excel con LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).
  
## <a name="creating-xml"></a>Creación de XML  
 Hay dos maneras de crear árboles XML en Visual Basic. Puede declarar un literal XML directamente en el código o puede usar las API de LINQ para crear el árbol. Ambos procesos permiten que el código refleje la estructura final del árbol XML. Por ejemplo, en el ejemplo de código siguiente se crea un elemento XML:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Para obtener más información, vea [crear XML en Visual Basic](creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Obtener acceso a XML y navegar por él  
 Visual Basic proporciona propiedades de eje XML para tener acceso a estructuras XML y navegar por ellas. Estas propiedades permiten tener acceso a los elementos y atributos XML especificando los nombres de los elementos secundarios XML. Como alternativa, puede llamar explícitamente a los métodos LINQ para navegar y buscar elementos y atributos. Por ejemplo, en el ejemplo de código siguiente se usan las propiedades del eje XML para hacer referencia a los atributos y elementos secundarios de un elemento XML. En el ejemplo de código se usa una consulta LINQ para recuperar los elementos secundarios y enviarlos como elementos XML, con lo que se realiza una transformación de forma eficaz.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Para obtener más información, vea [acceso a XML en Visual Basic](accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 Visual Basic permite especificar un alias para un espacio de nombres XML global mediante la `Imports` instrucción. En el ejemplo siguiente se muestra cómo utilizar la `Imports` instrucción para importar un espacio de nombres XML:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 Puede utilizar un alias de espacio de nombres XML al obtener acceso a las propiedades del eje XML y declarar literales XML para los elementos y documentos XML.  
  
 Puede recuperar un <xref:System.Xml.Linq.XNamespace> objeto para un prefijo de espacio de nombres determinado mediante el [operador GetXmlNamespace](../../../language-reference/operators/getxmlnamespace-operator.md).  
  
 Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../../../language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Usar espacios de nombres XML en literales XML  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Xml.Linq.XElement> objeto que utiliza el espacio de nombres global `ns` :  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 El compilador de Visual Basic traduce los literales XML que contienen los alias de espacio de nombres XML en un código equivalente que utiliza la notación XML para utilizar espacios de nombres XML con el `xmlns` atributo. Cuando se compila, el código del ejemplo de la sección anterior genera esencialmente el mismo código ejecutable que el ejemplo siguiente:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Usar espacios de nombres XML en las propiedades del eje XML  
 Los espacios de nombres XML declarados en literales XML no están disponibles para su uso en las propiedades de eje XML. Sin embargo, los espacios de nombres globales se pueden utilizar con las propiedades del eje XML. Use un signo de dos puntos para separar el prefijo del espacio de nombres XML del nombre del elemento local. El siguiente es un ejemplo:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>Consulte también

- [XML](index.md)
- [Crear XML en Visual Basic](creating-xml.md)
- [Obtener acceso a XML en Visual Basic](accessing-xml.md)
- [Manipular XML en Visual Basic](manipulating-xml.md)
