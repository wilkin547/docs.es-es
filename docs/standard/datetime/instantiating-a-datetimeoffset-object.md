---
title: Crear instancias de un objeto DateTimeOffset
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f072aecf45aaaf9bd4aec845a698d6f12916fedb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="instantiating-a-datetimeoffset-object"></a>Crear instancias de un objeto DateTimeOffset

El <xref:System.DateTimeOffset> estructura ofrece varias maneras de crear nuevas <xref:System.DateTimeOffset> valores. Muchos de ellos corresponden directamente a los métodos disponibles para crear nuevas instancias <xref:System.DateTime> valores, con mejoras que le permiten especificar el valor de fecha y hora del desplazamiento de hora Universal coordinada (UTC). En concreto, puede crear instancias de un <xref:System.DateTimeOffset> valor de las maneras siguientes:

* Mediante el uso de una fecha y hora literal.

* Mediante una llamada a un <xref:System.DateTimeOffset> constructor.

* Mediante la conversión implícita de un valor para <xref:System.DateTimeOffset> valor.

* Mediante el análisis de la representación de una cadena de una fecha y hora.

Este tema proporciona más detalles y ejemplos de código que muestran estos métodos de creación de instancias nuevas <xref:System.DateTimeOffset> valores.

## <a name="date-and-time-literals"></a>Literales de fecha y hora

Para los lenguajes que admiten, una de las maneras más comunes para crear instancias de un <xref:System.DateTime> valor es proporcionar la fecha y hora como un valor literal codificado de forma rígida. Por ejemplo, el siguiente código de Visual Basic crea un <xref:System.DateTime> objeto cuyo valor es el 1 de enero de 2008, a las 10:00 AM.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset>valores también se pueden inicializar mediante literales de fecha y hora cuando se utilizan lenguajes que admiten <xref:System.DateTime> literales. Por ejemplo, el siguiente código de Visual Basic crea un <xref:System.DateTimeOffset> objeto.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Como se muestra en la salida de la consola, el <xref:System.DateTimeOffset> valor creado de esta manera se asigna el desplazamiento de la zona horaria local. Esto significa que un <xref:System.DateTimeOffset> valor asignado mediante un literal de carácter no identifica un punto único de tiempo si el código se ejecuta en equipos diferentes.

## <a name="datetimeoffset-constructors"></a>Constructores de DateTimeOffset

El <xref:System.DateTimeOffset> tipo define seis constructores. Cuatro de ellas corresponden directamente a <xref:System.DateTime> constructores, con un parámetro adicional del tipo <xref:System.TimeSpan> que define la fecha y el desplazamiento de hora a la hora UTC. Éstos permiten definir un <xref:System.DateTimeOffset> valor basado en el valor de su fecha individual y componentes de tiempo. Por ejemplo, el código siguiente utiliza estos cuatro constructores para crear instancias de <xref:System.DateTimeOffset> objetos con valores idénticos de 1/7/2008 12:05 A.M. + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Tenga en cuenta que, cuando el valor de la <xref:System.DateTimeOffset> objeto instanciarse mediante un <xref:System.Globalization.PersianCalendar> en la consola se muestra el objeto como uno de los argumentos a su constructor, se expresa como una fecha del calendario gregoriano en lugar de con el calendario persa. Para producir una fecha con el calendario persa, vea el ejemplo en el <xref:System.Globalization.PersianCalendar> tema.

Los otros dos constructores crean un <xref:System.DateTimeOffset> objeto desde un <xref:System.DateTime> valor. La primera de ellas tiene un único parámetro, el <xref:System.DateTime> valor para convertir a un <xref:System.DateTimeOffset> valor. El desplazamiento del resultante <xref:System.DateTimeOffset> valor depende del <xref:System.DateTime.Kind%2A> propiedad del único parámetro del constructor. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el desplazamiento se establece igual que <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. De lo contrario, su desplazamiento se establece igual al de la zona horaria local. En el ejemplo siguiente se muestra el uso de este constructor para crear instancias de <xref:System.DateTimeOffset> objetos que representan la hora UTC y la zona horaria local:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Llamar a la sobrecarga de la <xref:System.DateTimeOffset> constructor que tiene una sola <xref:System.DateTime> parámetro es equivalente al realizar una conversión implícita de un <xref:System.DateTime> valor a un <xref:System.DateTimeOffset> valor.

El segundo constructor crea un <xref:System.DateTimeOffset> objeto desde un <xref:System.DateTime> valor tiene dos parámetros: el <xref:System.DateTime> valor para convertir y un <xref:System.TimeSpan> desplazamiento de valor que representa la fecha y hora a la hora UTC. Este valor de desplazamiento debe corresponder a la <xref:System.DateTime.Kind%2A> propiedad del primer parámetro del constructor o un <xref:System.ArgumentException> se produce. Si el <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el valor del segundo parámetro debe ser <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Si el <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, el valor del segundo parámetro debe ser el desplazamiento de zona horaria del sistema local. Si el <xref:System.DateTime.Kind%2A> propiedad del primer parámetro es <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, el desplazamiento puede ser cualquier valor válido. El código siguiente muestra las llamadas a este constructor para convertir <xref:System.DateTime> a <xref:System.DateTimeOffset> valores.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Conversión de tipos implícita

El <xref:System.DateTimeOffset> tipo es compatible con una conversión de tipos implícita: de un <xref:System.DateTime> valor a un <xref:System.DateTimeOffset> valor. (Una conversión de tipos implícita es una conversión de un tipo a otro que no requiere una conversión explícita (en C#) o una conversión (en Visual Basic) y que no pierde la información. Así hace posible código como el siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

El desplazamiento del resultante <xref:System.DateTimeOffset> valor depende de la <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> valor de propiedad. Si su valor es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, el desplazamiento se establece igual que <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Si su valor es <xref:System.DateTimeKind.Local?displayProperty=nameWithType> o <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, el ajuste se establece igual que el de la zona horaria local.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Análisis de la representación de cadena de una fecha y hora

El <xref:System.DateTimeOffset> tipo es compatible con cuatro métodos que permiten convertir la representación de cadena de una fecha y hora en un <xref:System.DateTimeOffset> valor:

* <xref:System.DateTimeOffset.Parse%2A>, que intenta convertir la representación de cadena de una fecha y hora para una <xref:System.DateTimeOffset> valor y produce una excepción si se produce un error en la conversión.

* <xref:System.DateTimeOffset.TryParse%2A>, que intenta convertir la representación de cadena de una fecha y hora para una <xref:System.DateTimeOffset> valor determinado y devuelve `false` si se produce un error en la conversión.

* <xref:System.DateTimeOffset.ParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado en un <xref:System.DateTimeOffset> valor. El método inicia una excepción si se produce un error en la conversión.

* <xref:System.DateTimeOffset.TryParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora en un formato especificado en un <xref:System.DateTimeOffset> valor. El método devuelve `false` si se produce un error de conversión.

En el ejemplo siguiente se muestra las llamadas a cada uno de estos métodos de conversión de cadena de cuatro para crear instancias de un <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
