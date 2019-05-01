---
title: Procedimiento Crear documentación XML en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 95f6c5b23deadc16eb1e81f274e2cc5149598fb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050443"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Procedimiento Crear documentación XML en Visual Basic
En este ejemplo se muestra cómo agregar comentarios de documentación XML en el código.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Para crear documentación XML para un tipo o miembro  
  
1. En el **Editor de código**, sitúe el cursor a la línea sobre el tipo o miembro para el que desea crear documentación.  
  
2. Tipo `'''` (tres comillas simples).  
  
     Se agrega un esquema XML para el tipo o miembro en el **Editor de código**.  
  
3. Agregar información descriptiva entre las etiquetas correspondientes.  
  
    > [!NOTE]
    >  Si agrega líneas adicionales dentro del bloque de documentación XML, cada línea debe comenzar con `'''`.  
  
4. Agregar código adicional que utiliza el tipo o miembro con los nuevos comentarios de documentación XML.  
  
     IntelliSense muestra el texto de la \<resumen > etiqueta para el tipo o miembro.  
  
5. Compile el código para generar un archivo XML que contiene los comentarios de documentación. Para obtener más información, vea [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>Vea también

- [Documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
