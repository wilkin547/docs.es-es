---
title: Procedimiento para crear documentación XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 1421cc85beba42b3cf3656c34b1d02347fbaf164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403244"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Cómo: Crear documentación XML en Visual Basic

En este ejemplo se muestra cómo agregar comentarios de documentación XML al código.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a>Para crear documentación XML para un tipo o miembro

1. En el **Editor de código**, coloque el cursor en la línea sobre el tipo o miembro para el que desea crear la documentación.

2. Escriba `'''` (tres comillas simples).

    En el **Editor de código**se agrega un esqueleto XML para el tipo o miembro.

3. Agregue información descriptiva entre las etiquetas adecuadas.

    > [!NOTE]
    > Si agrega líneas adicionales en el bloque de documentación XML, cada línea debe comenzar por `'''` .

4. Agregue código adicional que use el tipo o el miembro con los nuevos comentarios de documentación XML.

    IntelliSense muestra el texto de la \<summary> etiqueta para el tipo o miembro.

5. Compile el código para generar un archivo XML que contenga los comentarios de documentación. Para obtener más información, vea [-doc](../../reference/command-line-compiler/doc.md).

## <a name="see-also"></a>Vea también

- [Documentar el código con XML](documenting-your-code-with-xml.md)
- [Etiquetas de comentario XML](../../language-reference/xmldoc/index.md)
- [-doc](../../reference/command-line-compiler/doc.md)
