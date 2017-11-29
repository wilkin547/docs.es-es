---
title: Convenciones de nomenclatura de Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a59139b57568810de80de764388eeffa5f8d7ac9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-naming-conventions"></a>Convenciones de nomenclatura de Visual Basic
Al dar nombre a un elemento en la aplicación de Visual Basic, el primer carácter del nombre debe ser un carácter alfabético o un carácter de subrayado. Sin embargo, tenga en cuenta que los nombres que empiecen por un carácter de subrayado no son compatibles con el [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS).  
  
 Las sugerencias siguientes se aplican a la nomenclatura.  
  
-   Empiece cada palabra independiente de un nombre con una letra mayúscula, como en `FindLastRecord` y `RedrawMyForm`.  
  
-   Empiece los nombres de método y de función con un verbo, como en `InitNameArray` o `CloseDialog`.  
  
-   Comenzar la clase, estructura, módulo y nombres de propiedad con un nombre, como en `EmployeeName` o `CarAccessory`.  
  
-   Empiece los nombres de interfaz con el prefijo "I", seguido de un nombre o una frase, como `IComponent`, o con un adjetivo que describa el comportamiento de la interfaz, como `IPersistable`. No utilice el carácter de subrayado y utilice las abreviaturas con moderación, ya que pueden causar confusión.  
  
-   Empiece los nombres de controlador de eventos con un nombre que describe el tipo de evento seguido por el "`EventHandler`"sufijo, como en"`MouseEventHandler`".  
  
-   En nombres de clases de argumento de evento, incluya el "`EventArgs`" sufijo.  
  
-   Si un evento tiene un concepto de "before" o "after", utilice un sufijo en tiempo presente o pasado, como en "`ControlAdd`"o"`ControlAdded`".  
  
-   Para obtener términos largos o utilizados con frecuencia, utilice abreviaturas para mantener las longitudes de nombre razonable, por ejemplo, "HTML", en lugar de "Lenguaje de marcado de hipertexto". En general, los nombres de variable mayores que 32 caracteres son difíciles de leer en un monitor configurado con una resolución baja. Además, asegúrese de que sus abreviaturas sean coherentes a lo largo de toda la aplicación. Cambio de forma aleatoria en un proyecto entre "HTML" y "Lenguaje de marcado de hipertexto" puede producir confusión.  
  
-   Evite el uso de nombres en un ámbito interno que son los mismos que los nombres en un ámbito externo. Puede producir un error si se tiene acceso a la variable equivocada. Si se produce un conflicto entre una variable y la palabra clave del mismo nombre, debe identificar la palabra clave anterior con la biblioteca de tipos adecuada. Por ejemplo, si tiene una variable denominada `Date`, puede utilizar la función intrínseca `Date` función solo mediante una llamada a <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave como nombres de elementos en código](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)
