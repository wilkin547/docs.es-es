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
ms.openlocfilehash: c290af0c9cef619000a6620ba35209489856c5b8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281601"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Crear instancias de un objeto DateTimeOffset

La <xref:System.DateTimeOffset> estructura ofrece varias maneras de crear nuevos <xref:System.DateTimeOffset> valores. Muchos de ellos se corresponden directamente con los métodos disponibles para crear instancias de nuevos <xref:System.DateTime> valores, con mejoras que le permiten especificar el desplazamiento del valor de fecha y hora con respecto a la hora universal coordinada (UTC). En concreto, puede crear instancias de un <xref:System.DateTimeOffset> valor de las siguientes maneras:

- Mediante el uso de un literal de fecha y hora.

- Llamando a un <xref:System.DateTimeOffset> constructor.

- Mediante la conversión implícita de un valor en un <xref:System.DateTimeOffset> valor.

- Mediante el análisis de la representación de una cadena de una fecha y hora.

En este tema se proporcionan más detalles y ejemplos de código que ilustran estos métodos para crear instancias de nuevos <xref:System.DateTimeOffset> valores.

## <a name="date-and-time-literals"></a>Literales de fecha y hora

En el caso de los lenguajes que lo admiten, una de las formas más comunes de crear instancias de un <xref:System.DateTime> valor es proporcionar la fecha y la hora como un valor literal codificado de forma rígida. Por ejemplo, el siguiente código de Visual Basic crea un <xref:System.DateTime> objeto cuyo valor es el 1 de enero de 2008, a las 10:00 a.m.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset>los valores también se pueden inicializar mediante literales de fecha y hora cuando se usan lenguajes que admiten <xref:System.DateTime> literales. Por ejemplo, el siguiente código de Visual Basic crea un <xref:System.DateTimeOffset> objeto.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Como se muestra en la salida de la consola, <xref:System.DateTimeOffset> se asigna el desplazamiento de la zona horaria local al valor creado de esta manera. Esto significa que un <xref:System.DateTimeOffset> valor asignado mediante un literal de carácter no identifica un único punto de tiempo si el código se ejecuta en equipos diferentes.

## <a name="datetimeoffset-constructors"></a>Constructores DateTimeOffset

El <xref:System.DateTimeOffset> tipo define seis constructores. Cuatro de ellos se corresponden directamente con <xref:System.DateTime> los constructores, con un parámetro adicional de tipo <xref:System.TimeSpan> que define el desplazamiento de la fecha y la hora con respecto a la hora UTC. Estos permiten definir un <xref:System.DateTimeOffset> valor basado en el valor de sus componentes individuales de fecha y hora. Por ejemplo, el código siguiente usa estos cuatro constructores para crear instancias <xref:System.DateTimeOffset> de objetos con valores idénticos de 7/1/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Tenga en cuenta que, cuando el valor del objeto al que <xref:System.DateTimeOffset> se ha creado una instancia mediante un <xref:System.Globalization.PersianCalendar> objeto como uno de los argumentos de su constructor se muestra en la consola, se expresa como una fecha en el calendario gregoriano en lugar de en el calendario persa. Para generar una fecha mediante el calendario persa, consulte el ejemplo del <xref:System.Globalization.PersianCalendar> tema.

Los otros dos constructores crean un <xref:System.DateTimeOffset> objeto a partir de un <xref:System.DateTime> valor. El primero de ellos tiene un único parámetro, el <xref:System.DateTime> valor que se va a convertir en un <xref:System.DateTimeOffset> valor. El desplazamiento del valor resultante <xref:System.DateTimeOffset> depende de la <xref:System.DateTime.Kind%2A> propiedad del parámetro único del constructor. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> , el desplazamiento se establece en <xref:System.TimeSpan.Zero?displayProperty=nameWithType> . De lo contrario, su desplazamiento se establece igual al de la zona horaria local. En el ejemplo siguiente se muestra el uso de este constructor para crear instancias de <xref:System.DateTimeOffset> objetos que representan la hora UTC y la zona horaria local:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Llamar a la sobrecarga del <xref:System.DateTimeOffset> constructor que tiene un único <xref:System.DateTime> parámetro es equivalente a realizar una conversión implícita de un <xref:System.DateTime> valor en un <xref:System.DateTimeOffset> valor.

El segundo constructor que crea un <xref:System.DateTimeOffset> objeto a partir de un <xref:System.DateTime> valor tiene dos parámetros: el <xref:System.DateTime> valor que se va a convertir y un <xref:System.TimeSpan> valor que representa el desplazamiento de la fecha y la hora con respecto a la hora UTC. Este valor de desplazamiento debe corresponder a la <xref:System.DateTime.Kind%2A> propiedad del primer parámetro del constructor o <xref:System.ArgumentException> se produce una excepción. Si la <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> , el valor del segundo parámetro debe ser <xref:System.TimeSpan.Zero?displayProperty=nameWithType> . Si la <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Local?displayProperty=nameWithType> , el valor del segundo parámetro debe ser el desplazamiento de la zona horaria del sistema local. Si la <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> , el desplazamiento puede ser cualquier valor válido. En el código siguiente se muestran las llamadas a este constructor para convertirlos <xref:System.DateTime> en <xref:System.DateTimeOffset> valores.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Conversión implícita de tipos

El <xref:System.DateTimeOffset> tipo admite una conversión de tipos implícita: de un <xref:System.DateTime> valor a un <xref:System.DateTimeOffset> valor. (Una conversión de tipos implícita es una conversión de un tipo a otro que no requiere una conversión explícita (en C#) o una conversión (en Visual Basic) y que no pierde la información. Así hace posible código como el siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

El desplazamiento del valor resultante <xref:System.DateTimeOffset> depende del valor de <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> propiedad. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> , el desplazamiento se establece en <xref:System.TimeSpan.Zero?displayProperty=nameWithType> . Si su valor es <xref:System.DateTimeKind.Local?displayProperty=nameWithType> o <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> , el desplazamiento se establece igual que el de la zona horaria local.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Analizar la representación de cadena de una fecha y hora

El <xref:System.DateTimeOffset> tipo admite cuatro métodos que permiten convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> valor:

- <xref:System.DateTimeOffset.Parse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> valor y produce una excepción si se produce un error en la conversión.

- <xref:System.DateTimeOffset.TryParse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> valor y devuelve `false` si se produce un error en la conversión.

- <xref:System.DateTimeOffset.ParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado en un <xref:System.DateTimeOffset> valor. El método inicia una excepción si se produce un error en la conversión.

- <xref:System.DateTimeOffset.TryParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado en un <xref:System.DateTimeOffset> valor. El método devuelve `false` si se produce un error de conversión.

En el ejemplo siguiente se muestran las llamadas a cada uno de estos cuatro métodos de conversión de cadena para crear instancias de un <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Consulte también

- [Fechas, horas y zonas horarias](index.md)
