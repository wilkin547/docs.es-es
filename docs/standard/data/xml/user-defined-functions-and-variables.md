---
title: Funciones y variables definidas por el usuario
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 4772f20e-1e7f-496e-93c2-1484473be555
ms.openlocfilehash: 7040c2ccf6e3bfc6efcbec3505c633c6c3c6508f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710068"
---
# <a name="user-defined-functions-and-variables"></a>Funciones y variables definidas por el usuario
La clase <xref:System.Xml.XPath.XPathNavigator> proporciona un conjunto de métodos que se utilizan para interactuar con los datos de <xref:System.Xml.XPath.XPathDocument>. Puede suplementar las funciones XPath estándar implementando funciones y variables de extensión para utilizarlas en las expresiones de consulta XPath. El método <xref:System.Xml.XPath.XPathExpression.SetContext%2A> puede aceptar un contexto definido por el usuario derivado de <xref:System.Xml.Xsl.XsltContext>. Las funciones definidas por el usuario las resuelve el contexto personalizado.  
  
 Las funciones y variables de extensión pueden ser útiles en la prevención de ataques de inyección de XML. En estos escenarios, los datos proporcionados por el usuario se asignan a variables personalizadas y se procesan mediante funciones de extensión, no como datos sin procesar concatenados con instrucciones de procesamiento. Las funciones y variables de extensión contienen los datos proporcionados por el usuario de manera que estos solo actúan sobre los datos XML de la forma que pretendía el diseñador.  
  
 Para usar las extensiones, se implementa una clase <xref:System.Xml.Xsl.XsltContext> personalizada junto con las interfaces <xref:System.Xml.Xsl.IXsltContextFunction> y <xref:System.Xml.Xsl.IXsltContextVariable> que admiten las funciones y variables de extensión. Una <xref:System.Xml.XPath.XPathExpression> agrega datos proporcionados por el usuario con su <xref:System.Xml.Xsl.XsltArgumentList> al <xref:System.Xml.Xsl.XsltContext> personalizado.  
  
 La <xref:System.Xml.XPath.XPathExpression> representa una consulta compilada que <xref:System.Xml.XPath.XPathNavigator> utiliza para buscar y procesar los nodos identificados por la expresión.  
  
 El ejemplo siguiente muestra cómo implementar una clase de contexto personalizada derivada de <xref:System.Xml.Xsl.XsltContext>: Los comentarios del código describen los miembros de la clase y su uso en las funciones personalizadas. A continuación de ese segmento de código se encuentran las implementaciones de las funciones y variables, y una aplicación de ejemplo que utiliza estas implementaciones.  
  
 [!code-csharp[XPathExtensionFunctions#2](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#2)]
 [!code-vb[XPathExtensionFunctions#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#2)]  
  
 El código siguiente implementa <xref:System.Xml.Xsl.IXsltContextFunction>. La clase que implementa <xref:System.Xml.Xsl.IXsltContextFunction> resuelve y ejecuta las funciones definidas por el usuario. Este ejemplo utiliza la función identificada por la declaración `private int CountChar(string title, char charTocount)`.  
  
 Los comentarios del código describen los miembros de la clase.  
  
 [!code-csharp[XPathExtensionFunctions#3](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#3)]
 [!code-vb[XPathExtensionFunctions#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#3)]  
  
 El código siguiente implementa <xref:System.Xml.Xsl.IXsltContextVariable>. Esta clase resuelve las referencias a variables definidas por el usuario en las expresiones de consulta XPath en tiempo de ejecución. El método invalidado <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A> de la clase <xref:System.Xml.Xsl.XsltContext> crea y devuelve una instancia de dicha clase.  
  
 Los comentarios del código describen los miembros de la clase.  
  
 [!code-csharp[XPathExtensionFunctions#4](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#4)]
 [!code-vb[XPathExtensionFunctions#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#4)]  
  
 Teniendo en cuenta las definiciones de las clases anteriores, el código siguiente utiliza la función personalizada para contar los caracteres de los elementos del documento `Tasks.xml`. Los comentarios existentes en el código describen el código que compila la función personalizada y la ejecuta con el documento `Tasks.xml`.  
  
 [!code-csharp[XPathExtensionFunctions#1](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#1)]
 [!code-vb[XPathExtensionFunctions#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#1)]  
  
 Este ejemplo utiliza los datos XML siguientes.  
  
 [!code-xml[XPathExtensionFunctions#5](../../../../samples/snippets/xml/VS_Snippets_Data/xpathextensionfunctions/XML/tasks.xml#5)]
