---
title: Reglas de confiabilidad (análisis de código)
description: Más información sobre las reglas de confiabilidad del análisis de código.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- rules, reliability
- reliability rules
- managed code analysis rules, reliability rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: a747dd4dcda351a1ddb0f3d069bb7bac895c32f8
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "96594426"
---
# <a name="reliability-rules"></a>Reglas de confiabilidad

Las reglas de confiabilidad admiten la confiabilidad de bibliotecas y aplicaciones, como la correcta utilización de la memoria y el subproceso. Las reglas de confiabilidad incluyen:

|Regla|Descripción|
|----------|-----------------|
|[CA2000: Desechar objetos antes de perder el ámbito](ca2000.md)|Dado que podría producirse un evento excepcional que evitaría que el finalizador de un objeto se ejecutase, el objeto debe estar disponible en su lugar antes de que todas las referencias a él estén fuera del ámbito.|
|[CA2002: No bloquear objetos con identidad débil](ca2002.md)|Se dice que un objeto tiene una identidad débil cuando se puede tener acceso directamente a través de los límites del dominio de aplicación. Un subproceso que intenta obtener un bloqueo en un objeto que tiene identidad débil se puede bloquear con un segundo subproceso en un dominio de aplicación diferente que tenga bloqueado el mismo objeto.|
|[CA2007: No esperar una tarea directamente](ca2007.md)|Un método asincrónico [espera](../../../csharp/language-reference/operators/await.md) <xref:System.Threading.Tasks.Task> directamente.|
|[CA2008: No crear tareas sin pasar un elemento TaskScheduler](ca2008.md)|Una operación de creación o continuación de tareas utiliza una sobrecarga de método que no especifica un <xref:System.Threading.Tasks.TaskScheduler> parámetro.|
|[CA2009: No llame a ToImmutableCollection en un valor ImmutableCollection](ca2009.md)|`ToImmutable` se llamó innecesariamente al método en una colección inmutable desde el <xref:System.Collections.Immutable> espacio de nombres.|
|[CA2011: No asignar la propiedad dentro de su establecedor](ca2011.md) | Se asignó accidentalmente un valor a una propiedad dentro de su propio [descriptor de acceso set](../../../csharp/programming-guide/classes-and-structs/using-properties.md#the-set-accessor). |
|[CA2012: Usar ValueTasks correctamente](ca2012.md) | Los ValueTasks devueltos de las invocaciones de miembro están diseñados para esperarse directamente.  Los intentos de consumir un ValueTask varias veces o de tener acceso directamente a uno de los resultados antes de que se sepa que se han completado pueden producir una excepción o daños.  Omitir tal ValueTask es probable que se trate de un error funcional y puede degradar el rendimiento. |
|[CA2013: No usar ReferenceEquals con tipos de valor](ca2013.md) | Al comparar valores mediante <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> , si objA y objB son tipos de valor, se les aplica la conversión boxing antes de que se pasen al <xref:System.Object.ReferenceEquals%2A> método. Esto significa que, aunque objA y objB representen la misma instancia de un tipo de valor, el <xref:System.Object.ReferenceEquals%2A> método devuelve false. |
|[CA2014: no use stackalloc en los bucles.](ca2014.md) | El espacio de pila asignado por stackalloc solo se libera al final de la invocación del método actual.  Su uso en un bucle puede dar lugar a un crecimiento de pila sin enlazar y a condiciones de desbordamiento de pila eventuales. |
|[CA2015: no definir finalizadores para los tipos derivados de MemoryManager &lt; T&gt;](ca2015.md) | Agregar un finalizador a un tipo derivado de <xref:System.Buffers.MemoryManager%601> puede permitir que la memoria se libere mientras esté siendo utilizada por <xref:System.Span%601> . |
|[CA2016: Reenviar el parámetro CancellationToken a los métodos que lo usan](ca2016.md) | Reenvíe el `CancellationToken` parámetro a los métodos que toman uno para asegurarse de que las notificaciones de cancelación de la operación se propagan correctamente, o que `CancellationToken.None` se pasan explícitamente para indicar que no se propague el token de forma intencionada. |
