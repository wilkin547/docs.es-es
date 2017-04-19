---
title: "Documentar el código con XML (Visual Basic) | Documentos de Microsoft"
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
- XML, documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
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
ms.openlocfilehash: 2ec4907ff96a0861f97de21bdf45662c558d0a95
ms.lasthandoff: 03/13/2017

---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Documentar el código con XML (Visual Basic)
En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], puede documentar el código utilizando XML  
  
## <a name="xml-documentation-comments"></a>Comentarios de la documentación XML  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona una manera fácil de crear automáticamente documentación XML para los proyectos. Puede generar automáticamente un esquema XML para los tipos y miembros y, a continuación, proporcionar resúmenes, documentación descriptiva para cada parámetro y otros comentarios. Con la configuración apropiada, la documentación XML se emite automáticamente en un archivo XML con el mismo nombre que el proyecto y la extensión .xml. Para obtener más información, consulte [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 El archivo XML se puede utilizar o manipularse como XML. Este archivo se encuentra en el mismo directorio que el archivo de salida .exe o .dll del proyecto.  
  
 Documentación XML empieza con `'''`. El procesamiento de estos comentarios presenta algunas restricciones:  
  
-   La documentación debe ser correcto XML. Si el XML no está bien formado, se genera una advertencia y el archivo de documentación contiene un comentario que indica que se detectó un error.  
  
-   Los desarrolladores pueden crear su propio conjunto de etiquetas. Hay un conjunto recomendado de etiquetas (vea "Secciones relacionadas" en este tema). Algunas de las etiquetas recomendadas tienen significados especiales:  
  
    -   El \<param > etiqueta se utiliza para describir los parámetros. Si utiliza esta opción, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación. Si se produce un error en la comprobación, el compilador emite una advertencia.  
  
    -   El `cref` atributo se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código. El compilador comprueba si existe ese elemento de código. Si se produce un error en la comprobación, el compilador emite una advertencia. El compilador también respeta cualquier `Imports` instrucciones cuando busca un tipo descrito en el `cref` atributo.  
  
    -   El \<resumen > etiqueta utiliza IntelliSense en [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] para mostrar información adicional sobre un tipo o miembro.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información sobre la creación de un archivo XML con comentarios de documentación, vea los temas siguientes:  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Procesamiento del archivo XML](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Herramientas XML en Visual Studio](https://docs.microsoft.com/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones con Visual Basic](../../../visual-basic/developing-apps/index.md)   
 [Guía de programación de Visual Basic](../../../visual-basic/programming-guide/index.md)
