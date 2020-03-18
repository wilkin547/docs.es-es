---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568142"
---
### <a name="jsonelement-api-changes"></a>Cambios en la API de JsonElement

A partir de la versión preliminar 7 de .NET Core 3.0, algunas API de <xref:System.Text.Json.JsonElement> han cambiado para permitir una detección más sencilla y una mayor facilidad de uso.

#### <a name="change-description"></a>Descripción del cambio

En la versión preliminar 7 de .NET Core 3.0, las API de <xref:System.Text.Json.JsonElement> han cambiado de la manera siguiente para permitir una detección más sencilla y una mayor facilidad de uso.

1. Todas las sobrecargas del método `WriteProperty` se han quitado de <xref:System.Text.Json.JsonElement>. Esto afecta a código como el siguiente:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
      JsonElement root = doc.RootElement;
      root.WriteProperty(propertyNameString, writer);
      // ..
      root.WriteProperty(propertyNameSpan, writer);
      // ..
      root.WriteProperty(propertyNameJsonEncoded, writer);
      // ..
      root.WriteProperty(utf8PropertyName, writer);
      //..
   }
   ```

1. Se ha cambiado el nombre de `WriteValue` a <xref:System.Text.Json.JsonElement.WriteTo%2A>. Esto afecta a código como el siguiente:

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <xref:System.Text.Json.JsonElement.WriteTo%2A> produce ahora una <xref:System.ArgumentNullException> cuando su parámetro de método es `null`.

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 7)

#### <a name="recommended-action"></a>Acción recomendada

Si el código se ve afectado por estos cambios, puede hacer lo siguiente:

- No hay ninguna API de reemplazo para las sobrecargas de `WriteProperty` en <xref:System.Text.Json.JsonElement>. En su lugar, puede llamar a una de las sobrecargas de <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> junto con el método <xref:System.Text.Json.JsonElement.WriteTo%2A> para lograr el mismo resultado. Por ejemplo:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- Cambie el nombre del método `WriteValue` a <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>. El parámetro de método permanece sin cambios. Por ejemplo, el código anterior debe cambiarse por el siguiente:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- Controle la <xref:System.ArgumentNullException> en llamadas al método <xref:System.Text.Json.JsonElement.WriteTo%2A>.

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
