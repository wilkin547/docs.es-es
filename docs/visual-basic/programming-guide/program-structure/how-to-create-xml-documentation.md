---
title: "C&#243;mo: Crear documentaci&#243;n XML en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comentarios XML"
  - "documentación XML, crear"
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# C&#243;mo: Crear documentaci&#243;n XML en Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este ejemplo se muestra cómo agregar comentarios de documentación XML al código.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para crear documentación XML para un tipo o miembro  
  
1.  En el **Editor de código**, coloque el cursor en la línea situada encima del tipo o miembro para el que desea crear la documentación.  
  
2.  Escriba `'''` \(tres comillas simples\).  
  
     Se agrega una estructura XML para el tipo o miembro en el **Editor de código**.  
  
3.  Agregue información descriptiva entre las etiquetas adecuadas.  
  
    > [!NOTE]
    >  Si agrega líneas adicionales dentro del bloque de documentación XML, cada línea debe comenzar con `'''`.  
  
4.  Agregue código adicional que utilice el tipo o miembro con los nuevos comentarios de documentación XML.  
  
     IntelliSense muestra el texto de la etiqueta \<summary\> para el tipo o miembro.  
  
5.  Compile el código para generar un archivo XML que incluya los comentarios de la documentación.  Para obtener más información, vea [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Vea también  
 [Documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)