---
title: Limitaciones de Visual Basic | Documentos de Microsoft
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
- limits
- limitations, Visual Basic
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: d556b045b4ebae6ba24c0571a6cb7e5337c6a8f2
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-limitations"></a>Limitaciones de Visual Basic
Las versiones anteriores de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] aplica límites en el código, como la longitud de los nombres de variable, el número de variables permitidas en los módulos y el tamaño de módulo. En [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], se han reducido estas restricciones, lo que proporciona mayor libertad para crear y organizar el código.  
  
 Límites físicos dependen más de memoria de tiempo de ejecución que en tiempo de compilación consideraciones. Si se utilizan prácticas de programación prudentes y aplicaciones grandes se dividen en varias clases y módulos, hay muy pocas probabilidades de encontrar interna [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] limitación.  
  
 Los siguientes son algunas limitaciones que podría encontrar en casos extremos:  
  
-   **Longitud del nombre.** Hay un número máximo de caracteres para el nombre de cada elemento de programación declarado. Este valor máximo se aplica a una cadena de calificación completa si se califica el nombre del elemento. Consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Longitud de la línea.** Hay un máximo de 65535 caracteres en una línea física de código fuente. La línea de código de origen lógico puede ser mayor si utiliza caracteres de continuación de línea. Consulte [Cómo: interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Dimensiones de la matriz.** Hay un número máximo de dimensiones que se pueden declarar para una matriz. Esto limita cuántos índices se pueden utilizar para especificar un elemento de matriz. Consulte [dimensiones en Visual Basic de matriz](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Longitud de cadena.** Hay un número máximo de caracteres Unicode que se puede almacenar en una sola cadena. Consulte [el tipo de datos de cadena](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Longitud de la cadena de entorno.** Hay un máximo de 32768 caracteres para cualquier cadena de entorno que se utiliza como un argumento de línea de comandos. Esta es una limitación en todas las plataformas.  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
