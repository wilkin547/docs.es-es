---
ms.openlocfilehash: f5b0064f9f01923c6353fd8e2b274bd7407ccbd8
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237465"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a>Ha cambiado la firma de JsonFactoryConverter.CreateConverter

Para facilitar la composición de las clases <xref:System.Text.Json.Serialization.JsonConverterFactory>, se ha hecho público el método <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> y se le ha dado un segundo argumento de tipo <xref:System.Text.Json.JsonSerializerOptions>.

#### <a name="change-description"></a>Descripción del cambio

La firma del método `CreateConverter` en .NET Core antes de la versión 3.0 (versión preliminar 8) era la siguiente: 

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

En .NET Core 3.0 (versión preliminar 8) y en versiones posteriores es la siguiente:

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

Antes de este cambio, era difícil crear convertidores de generadores sellados, ya que no había ninguna manera fácil de obtener la clase <xref:System.Text.Json.Serialization.JsonConverter%601>. Hacer público el patrón de diseño Factory Method y pasar la clase <xref:System.Text.Json.JsonSerializerOptions> actual permiten una composición mucho más flexible.

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

Es necesario actualizar y volver a compilar las clases derivadas.

#### <a name="affected-apis"></a>API afectadas

<xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
