---
title: Elegir entre clases y structs
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bb05b825113c025781a790dc206d500633a3b08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573586"
---
# <a name="choosing-between-class-and-struct"></a>Elegir entre clases y structs
Una de las decisiones de diseño básico que se enfrenta a cada diseñador framework es si va a diseñar un tipo como una clase (un tipo de referencia) o como un struct (un tipo de valor). Buena comprensión de las diferencias en el comportamiento de los tipos de referencia y tipos de valor es fundamental en la creación de esta opción.  
  
 La primera diferencia entre los tipos de referencia y tipos de valor se tendrá en cuenta es que los tipos de referencia se asignan en el montón y recolección, mientras que los tipos de valor se asignan en la pila o en línea en que contiene los tipos y se desasigna cuando la pila desenreda o cuando obtiene cancela la asignación de su tipo contenedor. Por lo tanto, las asignaciones y cancelaciones de asignación de tipos de valor son en general más económico que las asignaciones y cancelaciones de asignación de tipos de referencia.  
  
 A continuación, matrices de tipos de referencia asignan a fuera de línea, lo que significa que la matriz de elementos son simplemente las referencias a las instancias del tipo de referencia que residen en el montón. Matrices de tipo de valor se asignan en línea, lo que significa que los elementos de matriz son las instancias reales de tipo de valor. Por lo tanto, las asignaciones y desasignaciones de matrices de tipo de valor son mucho más baratas que las asignaciones y desasignaciones de matrices de tipo de referencia. Además, en la mayoría de casos de matrices de tipo de valor exhiben mucho mejor grado de emplazamiento de referencia.  
  
 La diferencia siguiente está relacionado con el uso de memoria. Tipos de valor obtengan conversión boxing cuando se convierte en un tipo de referencia o una de las interfaces que implementan. Obtienen conversión unboxing cuando se convierte al tipo de valor. Dado que cuadros son objetos que se asignan en el montón y son recolección, demasiado conversión boxing y unboxing puede tener un impacto negativo en el montón, el recolector de elementos no utilizados y, en última instancia, el rendimiento de la aplicación.  En cambio, se produce ninguna conversión boxing tal como tipos de referencia se convierten.  
  
 A continuación, las asignaciones de tipo de referencia copiar la referencia, mientras que las asignaciones del tipo de valor copie el valor completo. Por lo tanto, las asignaciones de tipos de referencia de gran tamaño son más baratas que las asignaciones de tipos de valor grande.  
  
 Por último, los tipos de referencia se pasan por referencia, mientras que los tipos de valor se pasan por valor. Cambios en una instancia de un tipo de referencia afectan a todas las referencias que señalan a la instancia. Instancias del tipo de valor se copian cuando se pasan por valor. Cuando se cambia una instancia de un tipo de valor, evidentemente no afecta a cualquiera de sus copias. Dado que las copias no se crean explícitamente por el usuario, pero se crean de forma implícita cuando los argumentos se pasan o devuelven los valores se devuelven, los tipos de valor que se pueden cambiar pueden ser confusos para muchos usuarios. Por lo tanto, los tipos de valor deben ser inmutables.  
  
 Como regla general, la mayoría de los tipos en un marco de trabajo debe ser clases. Sin embargo, existen algunas situaciones en que las características de un tipo de valor que sea más adecuado usar structs.  
  
 **✓ CONSIDER** definir una estructura en lugar de una clase si instancias del tipo son pequeñas y normalmente corta duración o suelen estar incrustadas en otros objetos.  
  
 **X AVOID** definir un struct a menos que el tipo tenga todas las características siguientes:  
  
-   Representa lógicamente un valor único, de forma similar a los tipos primitivos (`int`, `double`, etcetera.).  
  
-   Tiene un tamaño de instancia inferior a 16 bytes.  
  
-   Es inmutable.  
  
-   No tendrá que realizar la conversión boxing con frecuencia.  
  
 En todos los demás casos, debe definir los tipos como clases.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
