---
title: GetXmlNamespace (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47ba67bc58debf8f144f6468bf510932414c0698
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace (Operador) (Visual Basic)
Obtiene el <xref:System.Xml.Linq.XNamespace> objeto que se corresponde con el prefijo de espacio de nombres XML especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Elementos  
 `xmlNamespacePrefix`  
 Opcional. La cadena que identifica el prefijo del espacio de nombres XML. Si se proporciona, esta cadena debe ser un identificador XML válido. Para obtener más información, consulte [nombres de declarar elementos y atributos XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Si no se especifica ningún prefijo, se devuelve el espacio de nombres predeterminado. Si no se especifica ningún espacio de nombres predeterminado, se devuelve el espacio de nombres vacío.  
  
## <a name="return-value"></a>Valor devuelto  
 La <xref:System.Xml.Linq.XNamespace> objeto que se corresponde con el prefijo de espacio de nombres XML.  
  
## <a name="remarks"></a>Comentarios  
 El `GetXmlNamespace` operador obtiene la <xref:System.Xml.Linq.XNamespace> objeto que se corresponde con el prefijo de espacio de nombres XML `xmlNamespacePrefix`.  
  
 Puede usar los prefijos de espacio de nombres XML directamente en literales XML y propiedades de eje XML. Sin embargo, debe utilizar el `GetXmlNamespace` operador para convertir un prefijo de espacio de nombres para un <xref:System.Xml.Linq.XNamespace> objeto antes de que se puede usar en el código. Puede anexar un nombre de elemento sin calificar a un <xref:System.Xml.Linq.XNamespace> objeto que se va a obtener un completo <xref:System.Xml.Linq.XName> objeto qué varios [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] métodos requieren.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente importa `ns` como un prefijo de espacio de nombres XML. A continuación, utiliza el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario que tiene el nombre completo `ns:phone`. A continuación, pasa ese nodo secundario a la `ShowName` subrutina, que crea un nombre completo mediante el `GetXmlNamespace` operador. El `ShowName` subrutina, a continuación, pasa el nombre completo para la <xref:System.Xml.Linq.XNode.Ancestors%2A> método para obtener el elemento primario `ns:contact` nodo.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 Cuando se llama a `TestGetXmlNamespace.RunSample()`, muestra un cuadro de mensaje que contiene el texto siguiente:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vea también  
 [Imports (instrucción), espacio de nombres XML](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [Obtener acceso a XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
