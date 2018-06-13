---
title: Limitaciones de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 57378c3aa18a5cc108c10e8654e55803f3cf9052
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649934"
---
# <a name="visual-basic-limitations"></a>Limitaciones de Visual Basic
Las versiones anteriores de Visual Basic aplican límites en el código, como la longitud de los nombres de variable, el número de variables permitidas en los módulos y el tamaño de módulo. En Visual Basic. NET, se han reducido estas restricciones, lo que le proporciona mayor libertad para crear y organizar el código.  
  
 Límites físicos dependen más de memoria en tiempo de ejecución que en las consideraciones de tiempo de compilación. Si se utilizan prácticas de programación prudentes y aplicaciones grandes se dividen en varias clases y módulos, hay muy pocas probabilidades de encontrar una limitación interna de Visual Basic.  
  
 Las siguientes son algunas limitaciones que pueden surgir en casos extremos:  
  
-   **Longitud del nombre.** Hay un número máximo de caracteres para el nombre de cada elemento de programación declarado. Este valor máximo se aplica a una cadena de calificación completa si hay que califica el nombre del elemento. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Longitud de línea.** Hay un máximo de 65535 caracteres en una línea física de código fuente. La línea de código de origen lógico puede tener más si se usan caracteres de continuación de línea. Vea [Cómo: interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Dimensiones de la matriz.** Hay un número máximo de dimensiones que se pueden declarar para una matriz. Esto limita cuántos índices se pueden utilizar para especificar un elemento de matriz. Vea [matriz dimensiones en Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Longitud de cadena.** Hay un número máximo de caracteres Unicode que pueden almacenar en una sola cadena. Vea [tipo de datos de cadena](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Longitud de la cadena de entorno.** Hay un máximo de 32768 caracteres para cualquier cadena de entorno que se usa como un argumento de línea de comandos. Se trata de una limitación en todas las plataformas.  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
