---
description: 'Más información acerca de: limitaciones de Visual Basic'
title: Limitaciones
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 9182c5fe475e4350cb17ed3e4b734e3924bb9f7b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432850"
---
# <a name="visual-basic-limitations"></a>Limitaciones de Visual Basic

Las versiones anteriores de Visual Basic los límites aplicados en el código, como la longitud de los nombres de variable, el número de variables permitidas en los módulos y el tamaño del módulo. En Visual Basic .NET, estas restricciones se han reducido, lo que le aporta mayor libertad para escribir y organizar el código.  
  
 Los límites físicos dependen más en la memoria en tiempo de ejecución que en las consideraciones en tiempo de compilación. Si usa prácticas de programación prudentes y divide aplicaciones grandes en varias clases y módulos, hay muy pocas probabilidades de encontrar una limitación de Visual Basic interna.  
  
 A continuación se indican algunas limitaciones que pueden surgir en casos extremos:  
  
- **Longitud del nombre.** Hay un número máximo de caracteres para el nombre de cada elemento de programación declarado. Este máximo se aplica a toda la cadena de calificación si el nombre del elemento está calificado. Vea [Declared Element Names](../language-features/declared-elements/declared-element-names.md).  
  
- **Longitud de línea.** Hay un máximo de 65535 caracteres en una línea física de código fuente. La línea de código fuente lógica puede ser más larga si usa caracteres de continuación de línea. Vea [Cómo: interrumpir y combinar instrucciones en el código](how-to-break-and-combine-statements-in-code.md).  
  
- **Dimensiones de la matriz.** Hay un número máximo de dimensiones que puede declarar para una matriz. Esto limita el número de índices que puede utilizar para especificar un elemento de la matriz. Vea [dimensiones de la matriz en Visual Basic](../language-features/arrays/array-dimensions.md).  
  
- **Longitud de la cadena.** Hay un número máximo de caracteres Unicode que se pueden almacenar en una sola cadena. Vea [tipo de datos de cadena](../../language-reference/data-types/string-data-type.md).  
  
- **Longitud de la cadena de entorno.** Hay un máximo de 32768 caracteres para cualquier cadena de entorno utilizada como argumento de la línea de comandos. Se trata de una limitación en todas las plataformas.  
  
## <a name="see-also"></a>Consulte también

- [Convenciones de código y estructura de programas](program-structure-and-code-conventions.md)
- [Convenciones de nomenclatura de Visual Basic](naming-conventions.md)
