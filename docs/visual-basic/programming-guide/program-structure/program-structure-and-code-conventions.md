---
title: "Convenciones de c&#243;digo y estructura de programas (Visual Basic) | Microsoft Docs"
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
  - "convenciones de código"
  - "código de Visual Basic, convenciones de código"
  - "convenciones de código, Visual Basic"
  - "programas, estructura"
  - "estructura de programas"
  - "convenciones de nomenclatura, Visual Basic"
  - "procedimientos recomendados, convenciones de codificación"
  - "convenciones, código en Visual Basic"
  - "código de Visual Basic"
  - "programación, convenciones de código de Visual Basic"
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Convenciones de c&#243;digo y estructura de programas (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En esta sección se introduce la estructura de programas de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] típica, se proporciona un programa de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] sencillo \("Hello, World"\) y se describen las convenciones de código de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Las convenciones de código son sugerencias que no se centran en la lógica de un programa, sino en la apariencia y la estructura física.  Si se cumplen, se facilita la lectura, la comprensión y el mantenimiento del código.  Las convenciones de código pueden incluir, entre otras cosas:  
  
-   Formatos estandarizados para etiquetar y comentar código.  
  
-   Instrucciones para agregar espacios, dar formato y aplicar sangría al código.  
  
-   Convenciones de nomenclatura para objetos, variables y procedimientos.  
  
 Los temas siguientes presentan un conjunto de directrices de programación para los programas de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], junto con ejemplos de uso correcto.  
  
## En esta sección  
 [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 Proporciona información general sobre los elementos que forman un programa de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 Describe el procedimiento que sirve como punto inicial y control general de la aplicación.  
  
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 Explica cómo hacer referencia a objetos de otros ensamblados.  
  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 Explica la forma en que los espacios de nombres organizan los objetos contenidos en ensamblados.  
  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 Proporciona instrucciones generales acerca de la nomenclatura de procedimientos, constantes, variables, argumentos y objetos.  
  
 [Convenciones de código de Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 Revisa las directrices utilizadas para desarrollar los ejemplos de esta documentación.  
  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Describe cómo se compilan selectivamente bloques concretos de código, al tiempo que se indica al compilador que pase por alto otros.  
  
 [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 Muestra cómo dividir instrucciones largas en diversas líneas y cómo combinar instrucciones cortas en una sola línea.  
  
 [Cómo: Contraer y ocultar secciones de código](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 Muestra la forma de contraer y ocultar secciones de código en el editor de código de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Cómo: Aplicar etiquetas a las instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 Muestra cómo marcar una línea de código a fin de identificarla para su utilización en instrucciones del tipo `On Error Goto`.  
  
 [Caracteres especiales en código](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 Explica cómo y dónde utilizar caracteres no numéricos y no alfabéticos.  
  
 [Comentarios en código](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 Explica cómo agregar comentarios descriptivos al código.  
  
 [Palabras clave como nombres de elementos en código](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 Describe cómo se utilizan corchetes \(`[]`\) para delimitar nombres de variable que también son palabras clave de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 Describe diversas maneras de hacer referencia a los elementos de un programa de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Limitaciones de Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 Explica la eliminación de limitaciones de código conocidas en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Secciones relacionadas  
 [Convenciones tipográficas y de código](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 Proporciona convenciones de codificación estándar para [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Escribir código](/visual-studio/ide/writing-code-in-the-code-and-text-editor)  
 Describe características que le permiten escribir y administrar el código.