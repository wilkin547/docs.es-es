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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50cc71b62581e1fb9302fe241abf6349afd33f8d
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106641"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Crear instancias de un objeto DateTimeOffset

La <xref:System.DateTimeOffset> estructura ofrece varias maneras de crear nuevos <xref:System.DateTimeOffset> valores. Muchos de ellos se corresponden directamente con los métodos disponibles para crear instancias <xref:System.DateTime> de nuevos valores, con mejoras que le permiten especificar el desplazamiento del valor de fecha y hora con respecto a la hora universal coordinada (UTC). En concreto, puede crear instancias de un <xref:System.DateTimeOffset> valor de las siguientes maneras:

- Mediante el uso de un literal de fecha y hora.

- Llamando a un <xref:System.DateTimeOffset> constructor.

- Mediante la conversión implícita de un valor <xref:System.DateTimeOffset> en un valor.

- Mediante el análisis de la representación de una cadena de una fecha y hora.

En este tema se proporcionan más detalles y ejemplos de código que ilustran estos métodos <xref:System.DateTimeOffset> para crear instancias de nuevos valores.

## <a name="date-and-time-literals"></a>Literales de fecha y hora

En el caso de los lenguajes que lo admiten, una de las formas <xref:System.DateTime> más comunes de crear instancias de un valor es proporcionar la fecha y la hora como un valor literal codificado de forma rígida. Por ejemplo, el siguiente código de Visual Basic crea <xref:System.DateTime> un objeto cuyo valor es el 1 de enero de 2008, a las 10:00 a.m.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset>los valores también se pueden inicializar mediante literales de fecha y hora cuando se usan <xref:System.DateTime> lenguajes que admiten literales. Por ejemplo, el siguiente código de Visual Basic crea <xref:System.DateTimeOffset> un objeto.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Como se muestra en la salida de <xref:System.DateTimeOffset> la consola, se asigna el desplazamiento de la zona horaria local al valor creado de esta manera. Esto significa que un <xref:System.DateTimeOffset> valor asignado mediante un literal de carácter no identifica un único punto de tiempo si el código se ejecuta en equipos diferentes.

## <a name="datetimeoffset-constructors"></a>Constructores DateTimeOffset

El <xref:System.DateTimeOffset> tipo define seis constructores. Cuatro de ellos se <xref:System.DateTime> corresponden directamente con los constructores, con un parámetro adicional de tipo <xref:System.TimeSpan> que define el desplazamiento de la fecha y la hora con respecto a la hora UTC. Estos permiten definir un <xref:System.DateTimeOffset> valor basado en el valor de sus componentes individuales de fecha y hora. Por ejemplo, el código siguiente usa estos cuatro constructores para crear instancias <xref:System.DateTimeOffset> de objetos con valores idénticos de 7/1/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Tenga en cuenta que, cuando el valor <xref:System.DateTimeOffset> del objeto al que se <xref:System.Globalization.PersianCalendar> ha creado una instancia mediante un objeto como uno de los argumentos de su constructor se muestra en la consola, se expresa como una fecha en el calendario gregoriano en lugar de en el calendario persa. Para generar una fecha mediante el calendario persa, consulte el ejemplo <xref:System.Globalization.PersianCalendar> del tema.

Los otros dos constructores crean un <xref:System.DateTimeOffset> objeto a partir <xref:System.DateTime> de un valor. El primero de ellos tiene un único parámetro, el <xref:System.DateTime> valor que se va a <xref:System.DateTimeOffset> convertir en un valor. El desplazamiento del valor resultante <xref:System.DateTimeOffset> depende de la <xref:System.DateTime.Kind%2A> propiedad del parámetro único del constructor. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el desplazamiento se establece en. <xref:System.TimeSpan.Zero?displayProperty=nameWithType> De lo contrario, su desplazamiento se establece igual al de la zona horaria local. En el ejemplo siguiente se muestra el uso de este constructor para crear <xref:System.DateTimeOffset> instancias de objetos que representan la hora UTC y la zona horaria local:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Llamar a la sobrecarga del <xref:System.DateTimeOffset> constructor que tiene un único <xref:System.DateTime> parámetro es equivalente a realizar una conversión implícita de un <xref:System.DateTime> valor en un <xref:System.DateTimeOffset> valor.

El segundo constructor que crea un <xref:System.DateTimeOffset> objeto a partir <xref:System.DateTime> de un valor tiene dos parámetros <xref:System.DateTime> : el valor que se va <xref:System.TimeSpan> a convertir y un valor que representa el desplazamiento de la fecha y la hora con respecto a la hora UTC. Este valor de desplazamiento debe corresponder <xref:System.DateTime.Kind%2A> a la propiedad del primer parámetro del constructor o <xref:System.ArgumentException> se produce una excepción. Si la <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el valor del segundo parámetro debe ser <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Si la <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, el valor del segundo parámetro debe ser el desplazamiento de la zona horaria del sistema local. Si la <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, el desplazamiento puede ser cualquier valor válido. En el código siguiente se muestran las llamadas a este constructor <xref:System.DateTime> para <xref:System.DateTimeOffset> convertirlos en valores.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Conversión implícita de tipos

El <xref:System.DateTimeOffset> tipo admite una conversión de tipos implícita: de <xref:System.DateTime> un valor a <xref:System.DateTimeOffset> un valor. (Una conversión de tipos implícita es una conversión de un tipo a otro que no requiere una conversión explícita (en C#) o una conversión (en Visual Basic) y que no pierde la información. Así hace posible código como el siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

El desplazamiento del valor resultante <xref:System.DateTimeOffset> depende del <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> valor de propiedad. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el desplazamiento se establece en. <xref:System.TimeSpan.Zero?displayProperty=nameWithType> Si su valor es <xref:System.DateTimeKind.Local?displayProperty=nameWithType> o <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, el desplazamiento se establece igual que el de la zona horaria local.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Analizar la representación de cadena de una fecha y hora

El <xref:System.DateTimeOffset> tipo admite cuatro métodos que permiten convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> valor:

- <xref:System.DateTimeOffset.Parse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> valor y produce una excepción si se produce un error en la conversión.

- <xref:System.DateTimeOffset.TryParse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> valor y devuelve `false` si se produce un error en la conversión.

- <xref:System.DateTimeOffset.ParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado en un <xref:System.DateTimeOffset> valor. El método inicia una excepción si se produce un error en la conversión.

- <xref:System.DateTimeOffset.TryParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado en un <xref:System.DateTimeOffset> valor. El método devuelve `false` si se produce un error de conversión.

En el ejemplo siguiente se muestran las llamadas a cada uno de estos cuatro métodos de conversión de <xref:System.DateTimeOffset> cadena para crear instancias de un valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
