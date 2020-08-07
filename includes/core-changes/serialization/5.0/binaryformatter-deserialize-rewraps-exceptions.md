---
ms.openlocfilehash: 4aef35502fc93cbf0399e3c8d0932338829d6c07
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517363"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a>BinaryFormatter.Deserialize vuelve a encapsular algunas excepciones en SerializationException

El método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> ahora vuelve a encapsular algunos objetos de excepción dentro de una excepción <xref:System.Runtime.Serialization.SerializationException> antes de propagarla de vuelta al auto de la llamada.

#### <a name="change-description"></a>Descripción del cambio

Anteriormente, el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> permitía que algunas excepciones arbitrarias, como <xref:System.ArgumentNullException>, se propagaran arriba de la pila a sus autores de la llamada.

En .NET 5.0 y versiones posteriores, el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> detecta de forma más agresiva las excepciones que se producen debido a operaciones de deserialización no válidas y las encapsula en una excepción <xref:System.Runtime.Serialization.SerializationException>.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 1)

#### <a name="recommended-action"></a>Acción recomendada

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
catch (SerializationException serEx)
{
    if (serEx.InnerException is MyException myEx)
    {
        // Handle 'myEx' here in case it was wrapped in SerializationException.
    }
    else
    {
        throw;
    }
}
```

#### <a name="category"></a>Categoría

Serialización

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->
