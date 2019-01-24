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
ms.openlocfilehash: 0f356b52304110299ed0af9bbccd5d03893f31a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596363"
---
# <a name="visual-basic-limitations"></a>Limitaciones de Visual Basic
Las versiones anteriores de Visual Basic aplican límites en el código, como la longitud de los nombres de variable, el número de variables permitidas en los módulos y el tamaño de módulo. En Visual Basic. NET, se han reducido estas restricciones, lo que le proporciona mayor libertad para crear y organizar el código.  
  
 Límites físicos dependen más de memoria en tiempo de ejecución que en las consideraciones de tiempo de compilación. Si se utilizan prácticas de programación prudentes y aplicaciones grandes se dividen en varias clases y módulos, hay muy pocas probabilidades de encontrar una limitación interna de Visual Basic.  
  
 Estas son algunas limitaciones que pueden surgir en casos extremos:  
  
-   **Longitud del nombre.** Hay un número máximo de caracteres para el nombre de cada elemento de programación declarado. Este valor máximo se aplica a una cadena de calificación completa si está calificado el nombre del elemento. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Longitud de línea.** Hay un máximo de 65535 caracteres en una línea de código fuente física. La línea de código de origen lógico puede ser mayor si usa caracteres de continuación de línea. Vea [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Dimensiones de la matriz.** Hay un número máximo de dimensiones que se pueden declarar para una matriz. Esto limita cuántos índices se pueden utilizar para especificar un elemento de matriz. Consulte [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Longitud de cadena.** Hay un número máximo de caracteres Unicode que puede almacenar en una sola cadena. Consulte [tipo de datos de cadena](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Longitud de cadena de entorno.** Hay un máximo de 32 768 caracteres para cualquier cadena de entorno que se usa como argumento de línea de comandos. Esta es una limitación en todas las plataformas.  
  
## <a name="see-also"></a>Vea también
- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
