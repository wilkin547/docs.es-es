---
title: GetXmlNamespace (operador) (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
dev_langs:
- VB
helpviewer_keywords:
- GetXmlNamespace operator
- GetXmlNamespace keyword
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 929ba4edae9e155245228670424a3898896da807
ms.lasthandoff: 03/13/2017

---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace (Operador) (Visual Basic)
Obtiene el <xref:System.Xml.Linq.XNamespace>objeto que corresponde al prefijo de espacio de nombres XML especificado.</xref:System.Xml.Linq.XNamespace>  
  
## <a name="syntax"></a>Sintaxis  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Elementos  
 `xmlNamespacePrefix`  
 Opcional. Cadena que identifica el prefijo del espacio de nombres XML. Si se proporciona, esta cadena debe ser un identificador XML válido. Para obtener más información, consulte [nombres de declarar elementos y atributos XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Si no se especifica ningún prefijo, se devuelve el espacio de nombres predeterminado. Si no se especifica ningún espacio de nombres predeterminado, se devuelve el espacio de nombres vacío.  
  
## <a name="return-value"></a>Valor devuelto  
 La <xref:System.Xml.Linq.XNamespace>objeto que corresponde al prefijo de espacio de nombres XML.</xref:System.Xml.Linq.XNamespace>  
  
## <a name="remarks"></a>Comentarios  
 El `GetXmlNamespace` operador obtiene la <xref:System.Xml.Linq.XNamespace>objeto que corresponde al prefijo de espacio de nombres XML `xmlNamespacePrefix`.</xref:System.Xml.Linq.XNamespace>  
  
 Puede usar prefijos de espacio de nombres XML directamente en los literales XML y propiedades de eje XML. Sin embargo, debe utilizar el `GetXmlNamespace` para convertir un prefijo de espacio de nombres a un <xref:System.Xml.Linq.XNamespace>antes de usarlo en el código de objeto.</xref:System.Xml.Linq.XNamespace> Puede anexar el nombre de un elemento sin calificar a un <xref:System.Xml.Linq.XNamespace>objeto para obtener un completo <xref:System.Xml.Linq.XName>objeto qué varios [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] métodos requieren.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace>  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente importa `ns` como un prefijo de espacio de nombres XML. A continuación, usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario que tiene el nombre completo `ns:phone`. A continuación, pasa ese nodo secundario a la `ShowName` subrutina, que crea un nombre completo mediante el `GetXmlNamespace` operador. El `ShowName` subrutina, a continuación, pasa el nombre completo para el <xref:System.Xml.Linq.XNode.Ancestors%2A>método para obtener el elemento primario `ns:contact` nodo.</xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
 [!code-vb[VbXMLSamples&#38;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 Cuando se llama a `TestGetXmlNamespace.RunSample()`, aparecerá un cuadro de mensaje que contiene el texto siguiente:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vea también  
 [Imports (instrucción) (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Obtener acceso a XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
