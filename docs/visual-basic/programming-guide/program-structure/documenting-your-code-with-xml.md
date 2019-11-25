---
title: Documentar el código con XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: bdf0da7a8acc919e4a1d66b81e30c9ed912dd321
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347440"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Documentar el código con XML (Visual Basic)

In Visual Basic, you can document your code using XML

## <a name="xml-documentation-comments"></a>Comentarios de la documentación XML

Visual Basic provides an easy way to automatically create XML documentation for projects. You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks. With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension. Para obtener más información, vea [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).

The XML file can be consumed or otherwise manipulated as XML. This file is located in the same directory as the output .exe or .dll file of your project.

XML documentation starts with `'''`. El procesamiento de estos comentarios tiene algunas restricciones:

- La documentación debe ser XML con formato correcto. If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.

- Los desarrolladores pueden crear su propio conjunto de etiquetas, There is a recommended set of tags (see "Related Sections" in this topic). Algunas de las etiquetas recomendadas tienen significados especiales:

  - La etiqueta \<param> se usa para describir parámetros. Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación. If the verification fails, the compiler issues a warning.

  - El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código. El compilador comprueba si existe este elemento de código. If the verification fails, the compiler issues a warning. The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.

  - The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.

## <a name="related-sections"></a>Secciones relacionadas

For details on creating an XML file with documentation comments, see the following topics:

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)

- [Procesamiento del archivo XML](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [Herramientas XML en Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>Vea también

- [Desarrollo de aplicaciones con Visual Basic](../../../visual-basic/developing-apps/index.md)
- [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)
