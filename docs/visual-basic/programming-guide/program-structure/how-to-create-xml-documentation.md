---
title: "Cómo: crear documentación XML en Visual Basic | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML comments
- XML documentation, creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
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
ms.openlocfilehash: 363a20c0fce05566b61e764d05932a9dfb779f90
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Cómo: Crear documentación XML en Visual Basic
Este ejemplo muestra cómo agregar comentarios de documentación XML al código.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Para crear documentación XML para un tipo o miembro  
  
1.  En el **Editor de código**, coloque el cursor en la línea anterior del tipo o miembro para el que desea crear documentación.  
  
2.  Tipo `'''` (tres comillas simples).  
  
     Se agrega un esquema XML para el tipo o miembro en el **Editor de código**.  
  
3.  Agregar información descriptiva entre las etiquetas adecuadas.  
  
    > [!NOTE]
    >  Si agrega líneas adicionales dentro del bloque de documentación XML, cada línea debe comenzar con `'''`.  
  
4.  Agregar código adicional que utiliza el tipo o miembro con los nuevos comentarios de documentación XML.  
  
     IntelliSense muestra el texto de la \<resumen > etiqueta para el tipo o miembro.  
  
5.  Compile el código para generar un archivo XML que contiene los comentarios de documentación. Para obtener más información, consulte [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>Vea también  
 [Documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [Etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
