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
ms.openlocfilehash: 11f62b8fe8a28d6fe6401d53dac4b9bc1c45b21d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554611"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Crear instancias de un objeto DateTimeOffset

El <xref:System.DateTimeOffset> estructura ofrece varias maneras de crear nuevos <xref:System.DateTimeOffset> valores. Muchos de ellos se corresponden directamente con los métodos disponibles para crear instancias de nuevos <xref:System.DateTime> valores, con mejoras que le permiten especificar el valor de fecha y hora del desplazamiento de hora Universal coordinada (UTC). En concreto, puede crear instancias de un <xref:System.DateTimeOffset> valor de las maneras siguientes:

* Mediante el uso de una fecha y hora literal.

* Mediante una llamada a un <xref:System.DateTimeOffset> constructor.

* Mediante la conversión implícita de un valor para <xref:System.DateTimeOffset> valor.

* Mediante el análisis de la representación de una cadena de una fecha y hora.

Este tema proporciona más detalles y ejemplos de código que ilustran estos métodos de creación de nuevas instancias <xref:System.DateTimeOffset> valores.

## <a name="date-and-time-literals"></a>Literales de fecha y hora

Los lenguajes que admiten, una de las maneras más comunes para crear instancias de un <xref:System.DateTime> valor consiste en proporcionar la fecha y hora como un valor literal codificado de forma rígida. Por ejemplo, el siguiente código de Visual Basic crea un <xref:System.DateTime> objeto cuyo valor es el 1 de enero de 2008, a las 10:00 AM.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset> los valores también se pueden inicializar mediante literales de fecha y hora cuando se utilizan los lenguajes que admiten <xref:System.DateTime> literales. Por ejemplo, el siguiente código de Visual Basic crea un <xref:System.DateTimeOffset> objeto.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Como se muestra en la salida de consola, el <xref:System.DateTimeOffset> valor creado de esta forma se asigna al desplazamiento de la zona horaria local. Esto significa que un <xref:System.DateTimeOffset> valor asignado mediante un literal de carácter no identifica un punto temporal único si el código se ejecuta en equipos diferentes.

## <a name="datetimeoffset-constructors"></a>Constructores de DateTimeOffset

El <xref:System.DateTimeOffset> tipo define seis constructores. Cuatro de ellas se corresponden directamente con <xref:System.DateTime> constructores con un parámetro adicional del tipo <xref:System.TimeSpan> que define la fecha y hora de desplazamiento de UTC. Estos le permiten definir un <xref:System.DateTimeOffset> valor según el valor de su fecha individuales y los componentes de tiempo. Por ejemplo, el código siguiente usa estos cuatro constructores para crear instancias <xref:System.DateTimeOffset> objetos con valores idénticos de 1/7/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Tenga en cuenta que, cuando el valor de la <xref:System.DateTimeOffset> crea una instancia mediante un <xref:System.Globalization.PersianCalendar> objeto como uno de los argumentos a su constructor se muestra en la consola, y se expresa como una fecha en el calendario gregoriano en lugar de en el calendario persa. Para generar una fecha con el calendario persa, vea el ejemplo en el <xref:System.Globalization.PersianCalendar> tema.

Los otros dos constructores crean un <xref:System.DateTimeOffset> objeto desde un <xref:System.DateTime> valor. El primero de ellos tiene un único parámetro, el <xref:System.DateTime> valor para convertir en un <xref:System.DateTimeOffset> valor. El desplazamiento del resultante <xref:System.DateTimeOffset> valor depende del <xref:System.DateTime.Kind%2A> propiedad del único parámetro del constructor. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el desplazamiento se establece igual que <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. De lo contrario, su desplazamiento se establece igual al de la zona horaria local. El ejemplo siguiente muestra el uso de este constructor para crear una instancia de <xref:System.DateTimeOffset> objetos que representan la hora UTC y la zona horaria local:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Llamar a la sobrecarga de la <xref:System.DateTimeOffset> constructor que tiene una sola <xref:System.DateTime> parámetro equivale al realizar una conversión implícita de un <xref:System.DateTime> valor a un <xref:System.DateTimeOffset> valor.

El segundo constructor crea un <xref:System.DateTimeOffset> objeto desde un <xref:System.DateTime> valor tiene dos parámetros: el <xref:System.DateTime> valor para convertir y un <xref:System.TimeSpan> valor que representa la fecha y hora de desplazamiento de UTC. Este valor de desplazamiento debe corresponder a la <xref:System.DateTime.Kind%2A> propiedad del primer parámetro del constructor o un <xref:System.ArgumentException> se produce. Si el <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el valor del segundo parámetro debe ser <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Si el <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, el valor del segundo parámetro debe ser el desplazamiento de zona horaria del sistema local. Si el <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, el desplazamiento puede ser cualquier valor válido. El código siguiente muestra las llamadas a este constructor para convertir <xref:System.DateTime> a <xref:System.DateTimeOffset> valores.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Conversión de tipos implícita

El <xref:System.DateTimeOffset> tipo admite una conversión de tipos implícita: desde un <xref:System.DateTime> valor a un <xref:System.DateTimeOffset> valor. (Una conversión de tipos implícita es una conversión de un tipo a otro que no requiere una conversión explícita (en C#) o una conversión (en Visual Basic) y que no pierde la información. Así hace posible código como el siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

El desplazamiento del resultante <xref:System.DateTimeOffset> valor depende de la <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> valor de propiedad. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el desplazamiento se establece igual que <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Si su valor es <xref:System.DateTimeKind.Local?displayProperty=nameWithType> o <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, el desplazamiento se establece igual que el de la zona horaria local.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Análisis de la representación de cadena de una fecha y hora

El <xref:System.DateTimeOffset> tipo admite cuatro métodos que permiten convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> valor:

* <xref:System.DateTimeOffset.Parse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> de valor y produce una excepción si se produce un error en la conversión.

* <xref:System.DateTimeOffset.TryParse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> valor y devuelve `false` si se produce un error en la conversión.

* <xref:System.DateTimeOffset.ParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado a un <xref:System.DateTimeOffset> valor. El método inicia una excepción si se produce un error en la conversión.

* <xref:System.DateTimeOffset.TryParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado a un <xref:System.DateTimeOffset> valor. El método devuelve `false` si se produce un error de conversión.

El ejemplo siguiente muestra las llamadas a cada uno de estos métodos de conversión de cadena de cuatro a crear una instancia de un <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
