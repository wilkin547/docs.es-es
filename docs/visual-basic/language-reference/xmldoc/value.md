---
title: "&lt;value&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<value> (etiqueta XML)"
  - "value (etiqueta XML)"
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;value&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica la descripción de una propiedad.  
  
## Sintaxis  
  
```  
<value>property-description</value>  
```  
  
#### Parámetros  
 `property-description`  
 Descripción de la propiedad.  
  
## Comentarios  
 Utilice la etiqueta `<value>` para describir una propiedad.  Tenga en cuenta que al agregar una propiedad mediante un asistente para código en el entorno de desarrollo de Visual Studio, se agregará una etiqueta [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md) para la nueva propiedad.  A continuación, se debe agregar manualmente una etiqueta `<value>` que describa el valor que representa la propiedad.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<value>` para describir qué valor incluye la propiedad `Counter`.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)