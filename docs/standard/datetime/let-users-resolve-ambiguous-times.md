---
title: Procedimiento para permitir que los usuarios resuelvan horas ambiguas
ms.date: 04/10/2017
helpviewer_keywords:
- time zones [.NET], ambiguous time
- ambiguous time [.NET]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
ms.openlocfilehash: d543db20161057764749210533f35f7c2a1ec81d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817801"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a>Procedimiento para permitir que los usuarios resuelvan horas ambiguas

Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC). Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar. Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:

- Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.

- Piense cómo se corresponde esa hora con la hora UTC. Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.

En este tema se muestra cómo permitir que un usuario resuelva una hora ambigua.

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a>Para permitir que un usuario resuelva una hora ambigua

1. Obtenga la entrada de fecha y hora del usuario.

2. Llame al <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> método para determinar si la hora es ambigua.

3. Si la hora es ambigua, llame al <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> método para recuperar una matriz de <xref:System.TimeSpan> objetos. Cada elemento de la matriz contiene un desplazamiento UTC al que se puede asignar la hora ambigua.

4. Permita que el usuario seleccione la diferencia horaria que quiera.

5. Para obtener la fecha y hora UTC, reste de la hora local la diferencia horaria que ha seleccionado el usuario.

6. Llame al `static` `Shared` método (en Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A> para establecer la propiedad del valor de fecha y hora UTC <xref:System.DateTime.Kind%2A> en <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se le pide al usuario que escriba un valor de fecha y hora y, si es ambiguo, se permite que el usuario seleccione la hora UTC con la que se corresponde dicha hora ambigua.

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

En el núcleo del código de ejemplo se usa una matriz de <xref:System.TimeSpan> objetos para indicar posibles desplazamientos de la hora ambigua con respecto a la hora UTC. Pero es probable que estas diferencias horarias sean poco significativas para el usuario. Para aclarar el significado de las diferencias horarias, el código también indica si una diferencia horaria representa la hora estándar o el horario de verano de la zona horaria local. El código determina qué hora es estándar y qué hora es el horario de verano comparando el desplazamiento con el valor de la <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad. Esta propiedad indica la diferencia entre la hora UTC y la hora estándar de la zona horaria.

En este ejemplo, todas las referencias a la zona horaria local se realizan a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad; la zona horaria local nunca se asigna a una variable de objeto. Se trata de una práctica recomendada, ya que una llamada al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> método invalida los objetos a los que está asignada la zona horaria local.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que el <xref:System> espacio de nombres se debe importar con la `using` instrucción (necesaria en el código de C#).

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](index.md)
- [Cómo: resolver horas ambiguas](resolve-ambiguous-times.md)
