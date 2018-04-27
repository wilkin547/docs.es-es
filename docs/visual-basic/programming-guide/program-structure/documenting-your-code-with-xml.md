---
title: Documentar el código con XML (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d132fa514008d072158a0e6bedaff511c55b18c0
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Documentar el código con XML (Visual Basic)
En Visual Basic, puede documentar el código con XML  
  
## <a name="xml-documentation-comments"></a>Comentarios de la documentación XML  
 Visual Basic proporciona una manera sencilla para crear automáticamente documentación XML para los proyectos. Puede generar automáticamente un esquema XML para los tipos y miembros y, a continuación, proporcionar resúmenes, documentación descriptiva para cada parámetro y otros comentarios. Con la configuración apropiada, la documentación XML se emite automáticamente en un archivo XML con el mismo nombre que el proyecto y la extensión .xml. Para obtener más información, vea [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 El archivo XML puede ser consumido o manipularse como XML. Este archivo se encuentra en el mismo directorio que el archivo de salida .exe o .dll del proyecto.  
  
 Documentación XML empieza con `'''`. El procesamiento de estos comentarios tiene algunas restricciones:  
  
-   La documentación debe ser XML con formato correcto. Si el código XML no está bien formado, se genera una advertencia y el archivo de documentación contiene un comentario que indica que se detectó un error.  
  
-   Los desarrolladores pueden crear su propio conjunto de etiquetas, Hay un conjunto recomendado de etiquetas (vea "Secciones relacionadas" en este tema). Algunas de las etiquetas recomendadas tienen significados especiales:  
  
    -   La etiqueta \<param> se usa para describir parámetros. Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación. Si se produce un error en la comprobación, el compilador emite una advertencia.  
  
    -   El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código. El compilador comprueba que existe este elemento de código. Si se produce un error en la comprobación, el compilador emite una advertencia. El compilador también respeta cualquier `Imports` instrucciones cuando se busca un tipo descrito en el `cref` atributo.  
  
    -   El \<resumen > etiqueta se usa por IntelliSense en Visual Studio para mostrar información adicional sobre un tipo o miembro.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información sobre cómo crear un archivo XML con los comentarios de documentación, vea los temas siguientes:  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Procesamiento del archivo XML](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Herramientas XML en Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de aplicaciones con Visual Basic](../../../visual-basic/developing-apps/index.md)  
 [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)
