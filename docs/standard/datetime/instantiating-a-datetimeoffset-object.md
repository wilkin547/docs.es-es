---
title: Crear instancias de un objeto DateTimeOffset
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
ms.openlocfilehash: 1b1178623258393eab28a7087eb04c47b55a9176
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122311"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Crear instancias de un objeto DateTimeOffset

La estructura de <xref:System.DateTimeOffset> ofrece varias maneras de crear nuevos valores de <xref:System.DateTimeOffset>. Muchos de ellos se corresponden directamente con los métodos disponibles para crear instancias de nuevos valores de <xref:System.DateTime>, con mejoras que le permiten especificar el desplazamiento del valor de fecha y hora con respecto a la hora universal coordinada (UTC). En concreto, puede crear una instancia de un valor <xref:System.DateTimeOffset> de las maneras siguientes:

- Mediante el uso de un literal de fecha y hora.

- Llamando a un constructor de <xref:System.DateTimeOffset>.

- Mediante la conversión implícita de un valor en <xref:System.DateTimeOffset> valor.

- Mediante el análisis de la representación de una cadena de una fecha y hora.

En este tema se proporcionan más detalles y ejemplos de código que ilustran estos métodos para crear instancias de nuevos valores de <xref:System.DateTimeOffset>.

## <a name="date-and-time-literals"></a>Literales de fecha y hora

En el caso de los lenguajes que lo admiten, una de las formas más comunes de crear instancias de un valor <xref:System.DateTime> es proporcionar la fecha y la hora como un valor literal codificado de forma rígida. Por ejemplo, el siguiente código de Visual Basic crea un objeto <xref:System.DateTime> cuyo valor es el 1 de enero de 2008, a las 10:00 A.M.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

los valores de <xref:System.DateTimeOffset> también se pueden inicializar mediante literales de fecha y hora cuando se usan lenguajes que admiten literales de <xref:System.DateTime>. Por ejemplo, el siguiente código de Visual Basic crea un objeto <xref:System.DateTimeOffset>.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Como se muestra en la salida de la consola, el valor <xref:System.DateTimeOffset> creado de esta manera se asigna al desplazamiento de la zona horaria local. Esto significa que un valor <xref:System.DateTimeOffset> asignado mediante un literal de carácter no identifica un único punto de tiempo si el código se ejecuta en equipos diferentes.

## <a name="datetimeoffset-constructors"></a>Constructores DateTimeOffset

El tipo de <xref:System.DateTimeOffset> define seis constructores. Cuatro de ellos se corresponden directamente con constructores de <xref:System.DateTime>, con un parámetro adicional de tipo <xref:System.TimeSpan> que define el desplazamiento de la fecha y la hora con respecto a la hora UTC. Estos permiten definir un valor de <xref:System.DateTimeOffset> basado en el valor de sus componentes individuales de fecha y hora. Por ejemplo, el código siguiente usa estos cuatro constructores para crear instancias de <xref:System.DateTimeOffset> objetos con valores idénticos de 7/1/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Tenga en cuenta que, cuando el valor del objeto <xref:System.DateTimeOffset> al que se ha creado una instancia mediante un objeto <xref:System.Globalization.PersianCalendar> como uno de los argumentos de su constructor se muestra en la consola, se expresa como una fecha en el calendario gregoriano en lugar de en el calendario persa. Para generar una fecha mediante el calendario persa, vea el ejemplo del tema <xref:System.Globalization.PersianCalendar>.

Los otros dos constructores crean un objeto <xref:System.DateTimeOffset> a partir de un valor de <xref:System.DateTime>. El primero de ellos tiene un único parámetro, el valor <xref:System.DateTime> que se va a convertir en un valor <xref:System.DateTimeOffset>. El desplazamiento del valor de <xref:System.DateTimeOffset> resultante depende de la propiedad <xref:System.DateTime.Kind%2A> del parámetro único del constructor. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el desplazamiento se establece igual a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. De lo contrario, su desplazamiento se establece igual al de la zona horaria local. En el ejemplo siguiente se muestra el uso de este constructor para crear instancias de <xref:System.DateTimeOffset> objetos que representan la hora UTC y la zona horaria local:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Llamar a la sobrecarga del constructor <xref:System.DateTimeOffset> que tiene un único parámetro <xref:System.DateTime> es equivalente a realizar una conversión implícita de un valor <xref:System.DateTime> en un valor de <xref:System.DateTimeOffset>.

El segundo constructor que crea un objeto <xref:System.DateTimeOffset> a partir de un valor <xref:System.DateTime> tiene dos parámetros: el valor de <xref:System.DateTime> que se va a convertir y un valor de <xref:System.TimeSpan> que representa el desplazamiento de la fecha y la hora con respecto a la hora UTC. Este valor de desplazamiento debe corresponder a la propiedad <xref:System.DateTime.Kind%2A> del primer parámetro del constructor o se produce una <xref:System.ArgumentException>. Si la propiedad <xref:System.DateTime.Kind%2A> del primer parámetro es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el valor del segundo parámetro debe ser <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Si la propiedad <xref:System.DateTime.Kind%2A> del primer parámetro es <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, el valor del segundo parámetro debe ser el desplazamiento de la zona horaria del sistema local. Si la propiedad <xref:System.DateTime.Kind%2A> del primer parámetro es <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, el desplazamiento puede ser cualquier valor válido. En el código siguiente se muestran las llamadas a este constructor para convertir <xref:System.DateTime> en <xref:System.DateTimeOffset> valores.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Conversión implícita de tipos

El tipo de <xref:System.DateTimeOffset> admite una conversión de tipos implícita: de un valor de <xref:System.DateTime> a un valor de <xref:System.DateTimeOffset>. (Una conversión de tipos implícita es una conversión de un tipo a otro que no requiere una conversión explícita (en C#) o una conversión (en Visual Basic) y que no pierde la información. Así hace posible código como el siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

El desplazamiento del valor de <xref:System.DateTimeOffset> resultante depende del valor de la propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el desplazamiento se establece igual a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Si su valor es <xref:System.DateTimeKind.Local?displayProperty=nameWithType> o <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, el desplazamiento se establece igual que el de la zona horaria local.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Analizar la representación de cadena de una fecha y hora

El tipo de <xref:System.DateTimeOffset> admite cuatro métodos que permiten convertir la representación de cadena de una fecha y hora en un valor <xref:System.DateTimeOffset>:

- <xref:System.DateTimeOffset.Parse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un valor <xref:System.DateTimeOffset> y produce una excepción si se produce un error en la conversión.

- <xref:System.DateTimeOffset.TryParse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un valor <xref:System.DateTimeOffset> y devuelve `false` si se produce un error en la conversión.

- <xref:System.DateTimeOffset.ParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado en un valor de <xref:System.DateTimeOffset>. El método inicia una excepción si se produce un error en la conversión.

- <xref:System.DateTimeOffset.TryParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado en un valor de <xref:System.DateTimeOffset>. El método devuelve `false` si se produce un error de conversión.

En el ejemplo siguiente se muestran las llamadas a cada uno de estos cuatro métodos de conversión de cadena para crear instancias de un valor de <xref:System.DateTimeOffset>.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
