---
title: 'Cambio importante: BinaryFormatter.Deserialize vuelve a encapsular algunas excepciones'
description: Obtenga información sobre el cambio importante en .NET 5.0, donde BinaryFormatter.Deserialize vuelve a encapsular algunos objetos de excepción dentro de SerializationException.
ms.date: 08/18/2020
ms.openlocfilehash: 90dc4cce6785fdb38644cca2a2e9aff65eb7a313
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760140"
---
# <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a>BinaryFormatter.Deserialize vuelve a encapsular algunas excepciones en SerializationException

El método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> ahora vuelve a encapsular algunos objetos de excepción dentro de una excepción <xref:System.Runtime.Serialization.SerializationException> antes de propagarla de vuelta al auto de la llamada.

## <a name="change-description"></a>Descripción del cambio

Anteriormente, el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> permitía que algunas excepciones arbitrarias, como <xref:System.ArgumentNullException>, se propagaran arriba de la pila a sus autores de la llamada.

En .NET 5.0 y versiones posteriores, el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> detecta de forma más agresiva las excepciones que se producen debido a operaciones de deserialización no válidas y las encapsula en una excepción <xref:System.Runtime.Serialization.SerializationException>.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

En la mayoría de los casos, no tiene que realizar ninguna acción. Sin embargo, si el sitio de llamada depende de que se inicie una excepción determinada, puede desencapsular la excepción de la excepción <xref:System.Runtime.Serialization.SerializationException> externa, como se muestra en el ejemplo siguiente.

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx) when (serEx.InnerException is MyException myEx)
{
    // Handle 'myEx' here in case it was wrapped in SerializationException.
}
```

## <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

### Category

Serialization

-->
