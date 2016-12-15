---
title: "Documentar el c&#243;digo con XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "código de Visual Basic, documentar con XML"
  - "comentarios XML, Visual Basic"
  - "XML, documentar código"
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Documentar el c&#243;digo con XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] se puede documentar el código utilizando XML  
  
## Comentarios de la documentación XML  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona un medio sencillo para crear automáticamente documentación XML para los proyectos.  Puede generar automáticamente un esquema XML para los tipos y miembros y, a continuación, proporcionar resúmenes, documentación descriptiva para cada parámetro y otros comentarios.  Con la configuración apropiada, la documentación XML se emite automáticamente en un archivo XML que tiene el mismo nombre que el proyecto y la extensión .xml.  Para obtener más información, vea [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 El archivo XML se puede utilizar o, de lo contrario, manipularse como XML.  Este archivo se encuentra en el mismo directorio que el archivo .exe de salida o el archivo .dll del proyecto.  
  
 La documentación XML empieza con `'''`.  El procesamiento de estos comentarios presenta algunas restricciones:  
  
-   La documentación debe estar en XML bien formado.  Si el código XML no está bien formado, se generará una advertencia y el archivo de documentación incluirá un comentario que mencione el error encontrado.  
  
-   Los programadores pueden crear su propio conjunto de etiquetas.  Existe un conjunto de etiquetas recomendado \(vea "Secciones relacionadas" en este tema\).  Algunas de las etiquetas recomendadas tienen significados especiales:  
  
    -   La etiqueta \<param\> se usa para describir parámetros.  Cuando se utiliza, el compilador comprueba si el parámetro existe y si todos los parámetros están descritos en la documentación.  Si la comprobación no tiene éxito, el compilador emite una advertencia.  
  
    -   El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código.  El compilador comprueba si existe ese elemento de código.  Si la comprobación no tiene éxito, el compilador emite una advertencia.  El compilador también respeta cualquier instrucción `Imports` cuando busca un tipo descrito en el atributo `cref`.  
  
    -   La etiqueta \<summary\> la utiliza IntelliSense en [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] para mostrar información adicional sobre un tipo o miembro.  
  
## Secciones relacionadas  
 Si desea obtener información sobre cómo crear un archivo XML con comentarios de documentación, vea los siguientes temas:  
  
-   [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Procesar el archivo XML](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [Cómo: Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Herramientas XML en Visual Studio](/visual-studio/xml-tools/xml-tools-in-visual-studio)  
  
## Vea también  
 [Desarrollo de aplicaciones con Visual Basic](../../../visual-basic/developing-apps/index.md)   
 [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)