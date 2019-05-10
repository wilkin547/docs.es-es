---
title: Convenciones de nomenclatura de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: ce8d4c5ede0d722d2c1768b9c2cd7929f296114e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651244"
---
# <a name="visual-basic-naming-conventions"></a>Convenciones de nomenclatura de Visual Basic
Al dar nombre a un elemento en la aplicación de Visual Basic, el primer carácter del nombre debe ser un carácter alfabético o un carácter de subrayado. Sin embargo, tenga en cuenta que los nombres que empiezan por un carácter de subrayado no son compatibles con el [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Las sugerencias siguientes se aplican a la nomenclatura.  
  
- Empiece cada palabra independiente de un nombre con una letra mayúscula, como en `FindLastRecord` y `RedrawMyForm`.  
  
- Empiece los nombres de función y método con un verbo, como en `InitNameArray` o `CloseDialog`.  
  
- Empezar a la clase, estructura, módulo y los nombres de propiedad y un sustantivo, como en `EmployeeName` o `CarAccessory`.  
  
- Empiece los nombres de interfaz con el prefijo "I", seguido por un nombre o una frase del sistema, como `IComponent`, o con un adjetivo que describe el comportamiento de la interfaz, como `IPersistable`. No utilice el carácter de subrayado y utilizar las abreviaturas con moderación, ya que pueden causar confusión.  
  
- Empiece los nombres de controlador de eventos y un sustantivo que describe el tipo de evento seguido por el "`EventHandler`"sufijo, como en"`MouseEventHandler`".  
  
- En los nombres de las clases de argumento de evento, incluya el "`EventArgs`" sufijo.  
  
- Si un evento tiene un concepto de "before" o "after", utilice un sufijo en tiempo presente o pasado, como en "`ControlAdd`"o"`ControlAdded`".  
  
- Para términos largos o utilizados con frecuencia, utilice abreviaturas para mantener las longitudes de nombre razonable, por ejemplo, "HTML", en lugar de "Lenguaje de marcado de hipertexto". En general, los nombres de variable mayores que 32 caracteres son difíciles de leer en un monitor configurado con una resolución baja. Además, asegúrese de que sus abreviaturas son coherentes en toda la aplicación. Cambio de forma aleatoria en un proyecto entre "HTML" y "Lenguaje de marcado de hipertexto" puede crearle confusión.  
  
- Evite el uso de nombres en un ámbito interno que son los mismos que los nombres en un ámbito externo. Puede producir un error si se tiene acceso a la variable equivocada. Si se produce un conflicto entre una variable y la palabra clave del mismo nombre, debe identificar la palabra clave anteponiendo la biblioteca de tipos adecuado. Por ejemplo, si tiene una variable denominada `Date`, puede usar la función intrínseca `Date` función solo mediante una llamada a <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- [Palabras clave como nombres de elementos en código](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)
