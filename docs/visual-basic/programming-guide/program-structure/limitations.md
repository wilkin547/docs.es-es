---
title: "Limitaciones de Visual Basic | Microsoft Docs"
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
  - "limitaciones"
  - "limitaciones, Visual Basic"
  - "límites"
  - "límites, código de Visual Basic"
  - "código de Visual Basic, limitaciones"
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Limitaciones de Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las versiones anteriores de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] aplicaban límites en el código, como la longitud de los nombres de variable, el número de variables permitidas en los módulos y el tamaño de los módulos.  En [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] se han reducido estas restricciones, lo que proporciona mayor libertad para crear y organizar el código.  
  
 Los límites físicos dependen más de la memoria en tiempo de ejecución que de las consideraciones en tiempo de compilación.  Si se utilizan prácticas de programación prudentes y las aplicaciones grandes se dividen en varias clases y módulos, hay muy pocas probabilidades de encontrar una limitación interna en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 Las siguientes son algunas limitaciones que podría encontrar en casos extremos:  
  
-   **Longitud del nombre.** Hay un número de caracteres máximo para el nombre de cada elemento de programación declarado.  Este máximo se aplica a toda la cadena de calificación si el nombre del elemento está completo.  Vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Longitud de la línea.** En una línea física de código fuente, hay un máximo de 65535 caracteres.  La línea de código fuente lógica puede ser más larga si se utilizan caracteres de continuación de línea.  Vea [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Dimensiones de matriz.** Hay un número máximo de dimensiones que se pueden declarar para una matriz.  Esto limita cuántos índices se pueden utilizar para especificar un elemento de matriz.  Vea [Dimensiones de matrices en Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Longitud de cadena.** Hay un número máximo de caracteres Unicode que se pueden almacenar en una sola cadena.  Vea [String \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Longitud de cadena del entorno.** Hay un máximo de 32768 caracteres para cualquier cadena del entorno que se utilice como argumento de la línea de comandos.  Ésta es una limitación de todas las plataformas.  
  
## Vea también  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)