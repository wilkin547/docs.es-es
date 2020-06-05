---
title: Convenciones de nomenclatura
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
ms.openlocfilehash: 20531e379ddf9b93a278795e9b3c0eb91b47e077
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398349"
---
# <a name="visual-basic-naming-conventions"></a>Convenciones de nomenclatura de Visual Basic
Al asignar un nombre a un elemento en la aplicación Visual Basic, el primer carácter de ese nombre debe ser un carácter alfabético o un carácter de subrayado. Sin embargo, tenga en cuenta que los nombres que empiezan por un carácter de subrayado no son compatibles con la [independencia del lenguaje y los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Las sugerencias siguientes se aplican a la asignación de nombres.  
  
- Empiece cada palabra independiente en un nombre con una letra mayúscula, como en `FindLastRecord` y `RedrawMyForm` .  
  
- Comience los nombres de función y método con un verbo, como en `InitNameArray` o `CloseDialog` .  
  
- Empiece la clase, la estructura, el módulo y los nombres de propiedad con un nombre, como en `EmployeeName` o `CarAccessory` .  
  
- Comience los nombres de interfaz con el prefijo "I", seguido de un sustantivo o un sustantivo, como `IComponent` , o con un adjetivo que describa el comportamiento de la interfaz, como `IPersistable` . No use el carácter de subrayado y use las abreviaturas con moderación, ya que las abreviaturas pueden causar confusión.  
  
- Comience los nombres de los controladores de eventos con un nombre que describa el tipo de evento seguido del `EventHandler` sufijo "", como en " `MouseEventHandler` ".  
  
- En los nombres de las clases de argumento de evento, incluya el `EventArgs` sufijo "".  
  
- Si un evento tiene un concepto de "Before" o "after", use un sufijo en el pasado o en el pasado, como en " `ControlAdd` " o " `ControlAdded` ".  
  
- Para términos largos o usados con frecuencia, use abreviaturas para mantener las longitudes de nombre razonables, por ejemplo, "HTML", en lugar de "Lenguaje de marcado de hipertexto". En general, los nombres de variable de más de 32 caracteres son difíciles de leer en un monitor establecido en una resolución baja. Además, asegúrese de que las abreviaturas son coherentes en toda la aplicación. El cambio aleatorio de un proyecto entre "HTML" y "Lenguaje de marcado de hipertexto" puede producir confusión.  
  
- Evite usar nombres en un ámbito interno que coincidan con los nombres de un ámbito externo. Se pueden producir errores si se tiene acceso a la variable equivocada. Si se produce un conflicto entre una variable y la palabra clave con el mismo nombre, debe identificar la palabra clave anteponiendo la biblioteca de tipos adecuada. Por ejemplo, si tiene una variable denominada `Date` , solo puede utilizar la función intrínseca `Date` llamando a <xref:System.DateTime.Date%2A?displayProperty=nameWithType> .  
  
## <a name="see-also"></a>Consulte también

- [Palabras clave como nombres de elementos en el código](keywords-as-element-names-in-code.md)
- [Me, My, MyBase y MyClass](me-my-mybase-and-myclass.md)
- [Declared Element Names](../language-features/declared-elements/declared-element-names.md)
- [Convenciones de código y estructura de programas](program-structure-and-code-conventions.md)
- [Referencia del lenguaje Visual Basic](../../language-reference/index.md)
