---
title: "Estructura del programa y las convenciones de código (Visual Basic) | Documentos de Microsoft"
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
- coding conventions
- Visual Basic code, coding conventions
- coding conventions, Visual Basic
- programs, structure
- program structure
- naming conventions, Visual Basic
- best practices, coding conventions
- conventions, Visual Basic coding
- Visual Basic code
- programming, Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cd25d99d74bf1e4d416c9da63758f6ad04027258
ms.lasthandoff: 03/13/2017

---
# <a name="program-structure-and-code-conventions-visual-basic"></a>Convenciones de código y estructura de programas (Visual Basic)
Esta sección presenta típica [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] estructura del programa, proporciona un sencillo [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programa "Hello, World" y se explican [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] convenciones de código. Convenciones de código son sugerencias que centran no en la lógica de un programa, sino en el aspecto y la estructura física. A continuación de ellos, el código será más fácil de leer, comprender y mantener. Convenciones de código pueden incluir, entre otros:  
  
-   Formatos estandarizados para etiquetar y comentar código.  
  
-   Directrices para el espaciado, formato y aplicar sangría al código.  
  
-   Convenciones de nomenclatura para objetos, variables y procedimientos.  
  
 Los temas siguientes presentan un conjunto de directrices para de programación [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programas, junto con ejemplos de uso correcto.  
  
## <a name="in-this-section"></a>En esta sección  
 [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 Proporciona información general de los elementos que componen un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programa.  
  
 [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 Describe el procedimiento que actúa como el inicio de punto y control general de la aplicación.  
  
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 Describe cómo hacer referencia a objetos de otros ensamblados.  
  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 Describe cómo organizan objetos en los ensamblados de los espacios de nombres.  
  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 Incluye directrices generales para la nomenclatura de procedimientos, constantes, variables, argumentos y objetos.  
  
 [Convenciones de código de Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 Revisa las directrices utilizadas para desarrollar los ejemplos de esta documentación.  
  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Describe cómo la compilación selectiva de bloques concretos de código mientras se indica al compilador que ignore otros.  
  
 [Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 Muestra cómo dividir instrucciones largas en varias líneas y combinar instrucciones cortas en una sola línea.  
  
 [Contraer y ocultar secciones de código](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 Muestra cómo contraer y ocultar secciones de código en el [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] editor de código.  
  
 [Aplicar etiquetas a las instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 Muestra cómo marcar una línea de código e identificarla para su uso con instrucciones como `On Error Goto`.  
  
 [Caracteres especiales en el código](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 Explica cómo y dónde utilizar caracteres no numéricos y no alfabéticos.  
  
 [Comentarios en código](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 Describe cómo agregar comentarios descriptivos al código.  
  
 [Palabras clave como nombres de elementos en código](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 Describe cómo usar corchetes (`[]`) para delimitar nombres de variable que también son [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] palabras clave.  
  
 [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 Describe varias maneras de hacer referencia a elementos de un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programa.  
  
 [Limitaciones de Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 Explica la eliminación de limitaciones de código conocidas en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Convenciones tipográficas y de código](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 Proporciona convenciones de codificación estándar para [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 [Escribir código](https://docs.microsoft.com/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 Describe características que facilitan la escritura y administrar el código.
