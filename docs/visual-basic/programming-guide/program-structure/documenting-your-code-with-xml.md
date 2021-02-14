---
description: Más información acerca de cómo documentar el código con XML (Visual Basic)
title: Documentar el código con XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: b554007bdd5183d0d92dc7ff62d08885f4b7f486
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476012"
---
# <a name="document-your-code-with-xml-visual-basic"></a>Documentación del código con XML (Visual Basic)

En Visual Basic, puede documentar el código mediante XML.

## <a name="xml-documentation-comments"></a>Comentarios de la documentación XML

Visual Basic proporciona una manera sencilla de crear automáticamente documentación XML para los proyectos de. Puede generar automáticamente un esqueleto XML para los tipos y miembros y, a continuación, proporcionar resúmenes, documentación descriptiva para cada parámetro y otros comentarios. Con la configuración adecuada, la documentación XML se emite automáticamente en un archivo XML con el mismo nombre de archivo raíz que el proyecto. Para obtener más información, vea [-doc](../../reference/command-line-compiler/doc.md).

El archivo XML se puede consumir o manipular de otra manera como XML. Este archivo se encuentra en el mismo directorio que el archivo. exe o. dll de salida del proyecto.

La documentación XML empieza con `'''`. El procesamiento de estos comentarios tiene algunas restricciones:

- La documentación debe ser XML con formato correcto. Si el código XML no es correcto, se genera una advertencia y el archivo de documentación contiene un comentario que indica que se ha detectado un error.

- Los desarrolladores pueden crear su propio conjunto de etiquetas, Hay un conjunto recomendado de etiquetas (consulte [etiquetas de comentario XML](../../language-reference/xmldoc/index.md)). Algunas de las etiquetas recomendadas tienen significados especiales:

  - La etiqueta \<param> se usa para describir parámetros. Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación. Si se produce un error en la comprobación, el compilador emite una advertencia.

  - El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código. El compilador comprueba si existe este elemento de código. Si se produce un error en la comprobación, el compilador emite una advertencia. El compilador también respeta cualquier `Imports` instrucción al buscar un tipo descrito en el `cref` atributo.

  - \<summary>IntelliSense usa la etiqueta en Visual Studio para mostrar información adicional sobre un tipo o miembro.

## <a name="related-sections"></a>Secciones relacionadas

Para obtener más información sobre cómo crear un archivo XML con comentarios de documentación, vea los temas siguientes:

- [-doc](../../reference/command-line-compiler/doc.md)

- [Etiquetas de comentario XML](../../language-reference/xmldoc/index.md)

- [Procesar el archivo XML](processing-the-xml-file.md)

- [Procedimiento para crear documentación XML](how-to-create-xml-documentation.md)

- [Herramientas XML en Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>Vea también

- [Desarrollo de aplicaciones con Visual Basic](../../developing-apps/index.md)
- [Guía de programación en Visual Basic](../index.md)
