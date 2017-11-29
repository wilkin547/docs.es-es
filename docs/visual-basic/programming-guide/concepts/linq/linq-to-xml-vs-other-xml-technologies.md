---
title: LINQ to XML frente a Otros Technologies2 XML
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72ce3a82-ffc6-488c-98e7-b9b40f3591ec
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba342b68828d427bfbddf51fa3d2da5d3c614dae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-vs-other-xml-technologies"></a>LINQ to XML frente a otras tecnologías XML
Este tema compara [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con las siguientes tecnologías XML: <xref:System.Xml.XmlReader>, XSLT, MSXML y XmlLite. Esta información puede ayudarle a decidir la tecnología que utilizará.  
  
 Para ver una comparación de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con Document Object Model (DOM), vea [LINQ to XML frente a DOM (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-dom.md).  
  
## <a name="linq-to-xml-vs-xmlreader"></a>LINQ to XML frente a XmlReader  
 <xref:System.Xml.XmlReader> es un analizador rápido, de solo avance y sin almacenamiento en caché.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se implementa sobre <xref:System.Xml.XmlReader> y ambos están estrechamente integrados. Sin embargo, puede utilizar también <xref:System.Xml.XmlReader> por sí solo.  
  
 Por ejemplo, supongamos que está creando un servicio Web que analizará cientos de documentos XML por segundo y los documentos tienen la misma estructura, lo que significa que solo tiene que escribir una implementación de código para analizar el XML. En ese caso, probablemente deseará usar <xref:System.Xml.XmlReader> de forma independiente.  
  
 Por el contrario, si crea un sistema que analiza muchos documentos XML más pequeños y cada uno es diferente, quizás quiera aprovechar las mejoras de productividad que [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona.  
  
## <a name="linq-to-xml-vs-xslt"></a>LINQ to XML frente a XSLT  
 Tanto [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] como XSLT proporcionan amplias capacidades de transformación de documentos XML. XSLT es un enfoque declarativo basado en reglas. Los programadores de XSLT avanzado escriben XSLT en un estilo de programación funcional que resalta un enfoque sin estado. Las transformaciones se pueden escribir con funciones puras que se implementan sin efectos secundarios. Este enfoque basado en reglas o funcional no es familiar para muchos desarrolladores y su aprendizaje puede requerir bastante tiempo.  
  
 XSLT puede ser un sistema muy productivo que produce aplicaciones de alto rendimiento. Por ejemplo, algunas grandes compañías web utilizan XSLT como forma de generar HTML a partir de XML extraído de diversos almacenes de datos. El motor XSLT administrado compila código XSLT a CLR y tiene un rendimiento incluso mejor en algunos escenarios que el motor XSLT nativo.  
  
 No obstante, XSLT no aprovecha el conocimiento de C# y Visual Basic que muchos desarrolladores tienen. Requiere que los desarrolladores escriban código en un lenguaje de programación complejo y diferente. Usar dos sistemas de desarrollo diferentes no integrados como C# (o Visual Basic) y XSLT tiene como resultado sistemas de software que son más difíciles de desarrollar y mantener.  
  
 Cuando se dominan las expresiones de consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], las transformaciones de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] son una tecnología eficaz y fácil de usar. Básicamente, se forman documentos XML utilizando construcciones funcionales, extrayendo datos de varios orígenes, construyendo objetos <xref:System.Xml.Linq.XElement> dinámicamente y ensamblando el conjunto en un nuevo árbol XML. La transformación puede generar un documento completamente nuevo. La construcción de transformaciones en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es relativamente sencilla e intuitiva y el código resultante es legible. Esto reduce los costos de desarrollo y mantenimiento.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] no se ha diseñado para sustituir a XSLT. XSLT sigue siendo la herramienta preferida de transformaciones XML complicadas y basadas en documentos, especialmente si la estructura del documento no está bien definida.  
  
 XSLT tiene la ventaja de que es un estándar de World Wide Web Consortium (W3C). Si tiene el requisito de usar solamente tecnologías que son estándares, XSLT puede ser más adecuado.  
  
 XSLT es XML y, por lo tanto, se puede manipular mediante programación.  
  
## <a name="linq-to-xml-vs-msxml"></a>LINQ to XML frente a MSXML  
 MSXML es la tecnología basada en COM utilizada para procesar XML y que se incluye con Microsoft Windows. MSXML ofrece una implementación nativa de DOM, que es compatible con XPath y XSLT. También contiene el analizador basado en eventos y sin almacenamiento en caché SAX2.  
  
 MSXML tiene un buen rendimiento, es seguro de forma predeterminada en la mayoría de casos y se puede tener acceso a él en Internet Explorer para realizar procesamiento XML en el cliente en aplicaciones de estilo AJAX. MSXML se puede usar en cualquier lenguaje de programación que admita COM, incluyendo C++, JavaScript y [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 6.0.  
  
 No se recomienda el uso de MSXML en código administrado basado en Common Language Runtime (CLR).  
  
## <a name="linq-to-xml-vs-xmllite"></a>LINQ to XML frente a XmlLite  
 XmlLite es un analizador de extracción sin almacenamiento en caché, de solo avance. Los desarrolladores utilizan principalmente XmlLite con C++. No se recomienda a los desarrolladores usar XmlLite con código administrado.  
  
 La principal ventaja de XmlLite es que es un analizador XML rápido y ligero que es seguro en la mayoría de casos. Su área de exposición a amenazas es muy pequeña. Si debe analizar documentos que no son de confianza y desea protegerse de ataques tales como denegación de servicio o exposición de datos, XmlLite puede ser una buena opción.  
  
 XmlLite no se integra con [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. No proporciona al programador mejoras de productividad que sean la fuerza motivadora detrás de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Introducción (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
