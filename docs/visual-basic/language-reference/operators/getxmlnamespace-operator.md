---
title: "GetXmlNamespace (Operador) (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.GetXmlNamespace"
  - "GetXmlNamespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetXmlNamespace (palabra clave)"
  - "GetXmlNamespace (operador)"
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# GetXmlNamespace (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Obtiene el objeto <xref:System.Xml.Linq.XNamespace> que corresponde al prefijo de espacio de nombres XML especificado.  
  
## Sintaxis  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## Elementos  
 `xmlNamespacePrefix`  
 Opcional.  Cadena que identifica el prefijo de espacio de nombres XML.  Si se proporciona, esta cadena debe ser un identificador XML válido.  Para obtener más información, vea [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  Si no se especifica ningún prefijo, se devuelve el espacio de nombres predeterminado.  Si no se especifica ningún espacio de nombres predeterminado, se devuelve el espacio de nombres vacío.  
  
## Valor devuelto  
 Objeto <xref:System.Xml.Linq.XNamespace> que corresponde al prefijo de espacio de nombres XML.  
  
## Comentarios  
 El operador `GetXmlNamespace` obtiene el objeto <xref:System.Xml.Linq.XNamespace> que corresponde al prefijo de espacio de nombres XML `xmlNamespacePrefix`.  
  
 Los prefijos de espacio de nombres XML pueden usarse directamente en los literales XML y propiedades de eje XML.  Sin embargo, se debe usar el operador `GetXmlNamespace` para convertir un prefijo de espacio de nombres en un objeto <xref:System.Xml.Linq.XNamespace> antes de usarlo en el código.  Se puede anexar un nombre de elemento incompleto a un objeto <xref:System.Xml.Linq.XNamespace> para obtener un objeto <xref:System.Xml.Linq.XName> completo, que muchos métodos de [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] requieren.  
  
## Ejemplo  
 En el ejemplo siguiente se importa `ns` como prefijo de espacio de nombres XML.  A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario que tiene el nombre completo `ns:phone`.  Después, se pasa ese nodo secundario a la subrutina `ShowName`, que construye un nombre completo mediante el operador `GetXmlNamespace`.  La subrutina `ShowName` pasa el nombre completo al método <xref:System.Xml.Linq.XNode.Ancestors%2A> para obtener el nodo `ns:contact` primario.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 Al llamar a `TestGetXmlNamespace.RunSample()`, se muestra un cuadro de mensaje con el texto siguiente:  
  
 `Name: Patrick Hines`  
  
## Vea también  
 [Imports \(Instrucción, Espacio de nombres XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Obtener acceso a XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)