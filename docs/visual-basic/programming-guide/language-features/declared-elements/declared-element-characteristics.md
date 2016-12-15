---
title: "Caracter&#237;sticas de los elementos declarados (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "niveles de acceso, elementos declarados"
  - "tipos de datos [Visual Basic], elementos declarados"
  - "elementos declarados, nivel de acceso"
  - "elementos declarados, duración"
  - "elementos declarados, ámbito"
  - "elementos declarados, visibilidad"
  - "elementos, programar"
  - "duración, elementos declarados"
  - "ámbito, elementos declarados"
  - "visibilidad, elementos declarados"
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Caracter&#237;sticas de los elementos declarados (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una *característica* de un elemento declarado es un aspecto del elemento que afecta a la forma de interactuar del código con él.  Cada elemento declarado tiene una o varias de las siguientes características asociadas a él:  
  
-   *Tipo de datos*: valores que el elemento puede contener y cómo almacena esos valores.  Para obtener más información, vea [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
-   *Período de duración*: período en tiempo de ejecución durante el cual el elemento está disponible para su uso.  Para obtener más información, vea [Período de duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Ámbito*: conjunto de código que puede hacer referencia al elemento sin calificar su nombre.  Para obtener más información, vea [Cómo: Controlar el ámbito de una variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Nivel de acceso*: permiso otorgado al código para hacer uso del elemento.  Para obtener más información, vea [Cómo: Controlar la disponibilidad de una variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## Características de los elementos  
 La tabla siguiente muestra los elementos declarados y las características que se les aplican.  
  
|Elemento|Tipo de datos|Período de duración|Ámbito <sup>1</sup>|Nivel de acceso|  
|--------------|-------------------|-------------------------|-------------------------|---------------------|  
|Variable|Sí|Sí|Sí|Sí|  
|Constante|Sí|No|Sí|Sí|  
|Enumeración|Sí|No|Sí|Sí|  
|Estructura|No|No|Sí|Sí|  
|Propiedad.|Sí|Sí|Sí|Sí|  
|Método|No|Sí|Sí|Sí|  
|Procedimiento \(`Sub` o `Function`\)|No|Sí|Sí|Sí|  
|Parámetro de procedimiento|Sí|Sí|Sí|No|  
|Valor devuelto de función|Sí|Sí|Sí|No|  
|Operador|Sí|No|Sí|Sí|  
|Interfaz|No|No|Sí|Sí|  
|Clase|No|No|Sí|Sí|  
|Evento|No|No|Sí|Sí|  
|Delegado|No|No|Sí|Sí|  
  
 <sup>1</sup> A veces, se hace referencia al ámbito como *visibilidad*.  
  
## Vea también  
 [Elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Período de duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)