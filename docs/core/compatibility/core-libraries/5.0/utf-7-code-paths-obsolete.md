---
title: 'Cambio importante: Las rutas de acceso al código UTF-7 están obsoletas'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde los constructores UTF7 y UTF7Encoding están obsoletos.
ms.date: 11/01/2020
ms.openlocfilehash: d58305f59a30cdf31a525c3789bd6497201c50ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760125"
---
# <a name="utf-7-code-paths-are-obsolete"></a>Las rutas de acceso al código UTF-7 están obsoletas

La codificación UTF-7 ya no se usa de forma generalizada en la mayoría de las aplicaciones, y muchas especificaciones ahora [prohíben su uso](https://security.stackexchange.com/a/68609/3573) en el intercambio. En ocasiones, también se [usa como vector de ataque](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) en aplicaciones que no anticipan el encuentro de datos codificados en UTF-7. Microsoft advierte contra el uso de <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>, porque no proporciona detección de errores.

Por consiguiente, la propiedad <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> y los constructores de <xref:System.Text.UTF7Encoding.%23ctor%2A> ahora están obsoletos. Además, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> y <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> ya no le permiten especificar `UTF-7`.

## <a name="change-description"></a>Descripción del cambio

Anteriormente, podía crear una instancia de la codificación UTF-7 mediante las API de <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>. Por ejemplo:

```csharp
Encoding enc1 = Encoding.GetEncoding("utf-7"); // By name.
Encoding enc2 = Encoding.GetEncoding(65000); // By code page.
```

Además, el método <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> enumera una instancia que representa la codificación UTF-7, que muestra todas las instancias de <xref:System.Text.Encoding> registradas en el sistema.

A partir de .NET 5.0, la propiedad <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> y los constructores <xref:System.Text.UTF7Encoding.%23ctor%2A> están obsoletos y producen la advertencia `SYSLIB0001` (o `MSLIB0001` en versiones preliminares). Sin embargo, para reducir el número de advertencias que reciben los autores de la llamada cuando se usa la clase <xref:System.Text.UTF7Encoding>, el propio tipo <xref:System.Text.UTF7Encoding> no se marca como obsoleto.

```csharp
// The next line generates warning SYSLIB0001.
UTF7Encoding enc = new UTF7Encoding();
// The next line does not generate a warning.
byte[] bytes = enc.GetBytes("Hello world!");
```

Además, los métodos <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> tratan el nombre de la codificación `utf-7` y la página de códigos `65000` como `unknown`. Cuando esto sucede, el método inicia una excepción <xref:System.ArgumentException>.

```csharp
// Throws ArgumentException, same as calling Encoding.GetEncoding("unknown").
Encoding enc = Encoding.GetEncoding("utf-7");
```

Por último, el método <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> no incluye la codificación UTF-7 en la matriz <xref:System.Text.EncodingInfo> que devuelve. La codificación se excluye porque no se puede crear una instancia de ella.

```csharp
foreach (EncodingInfo encInfo in Encoding.GetEncodings())
{
    // The next line would throw if GetEncodings included UTF-7.
    Encoding enc = Encoding.GetEncoding(encInfo.Name);
}
```

## <a name="reason-for-change"></a>Motivo del cambio

Muchas aplicaciones llaman a `Encoding.GetEncoding("encoding-name")` con un valor de nombre de codificación proporcionado por un origen que no es de confianza. Por ejemplo, un cliente o un servidor web podrían tomar la parte `charset` del encabezado `Content-Type` y pasar el valor directamente a `Encoding.GetEncoding` sin validarlo. Como consecuencia, un punto de conexión malintencionado podría especificar `Content-Type: ...; charset=utf-7`, lo que provocaría un error de comportamiento de la aplicación.

Además, la deshabilitación de las rutas de acceso al código UTF-7 permite optimizar los compiladores, como los que usa Blazor, para quitar completamente estas rutas de acceso al código de la aplicación resultante. Como resultado, las aplicaciones compiladas se ejecutan de forma más eficaz y ocupan menos espacio en disco.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

En la mayoría de los casos, no tiene que realizar ninguna acción. Sin embargo, en el caso de las aplicaciones que han activado previamente rutas de acceso al código relacionadas con UTF-7, tenga en cuenta las instrucciones siguientes.

- Si la aplicación llama a <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> con nombres de codificación desconocidos proporcionados por un origen que no es de confianza:

  Compare mejor los nombres de codificación con una lista de permitidos configurable. La lista de permitidos configurable debe incluir, como mínimo, el estándar del sector "UTF-8". En función de los clientes y los requisitos normativos, es posible que también deba permitir codificaciones específicas de la región, como "GB18030".

  Si no implementa una lista de permitidos, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> devolverá cualquier <xref:System.Text.Encoding> que esté integrado en el sistema o que esté registrada a través de un objeto <xref:System.Text.EncodingProvider> personalizado. Audite los requisitos del servicio para validar que este es el comportamiento deseado. UTF-7 sigue deshabilitado de forma predeterminada, a menos que la aplicación vuelva a habilitar el modificador de compatibilidad mencionado más adelante en este artículo.

- Si usa <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> o <xref:System.Text.UTF7Encoding> en su propio protocolo o formato de archivo:

  Cambie al uso de <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> o <xref:System.Text.UTF8Encoding>. UTF-8 es un estándar del sector y es compatible con numerosos lenguajes, sistemas operativos y entornos de ejecución. El uso de UTF-8 facilita el mantenimiento futuro del código y hace que sea más interoperable con el resto del ecosistema.

- Si va a comparar una instancia de <xref:System.Text.Encoding> con <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:

  Considere mejor la posibilidad de realizar una comprobación con la página de códigos UTF-7 conocidos, que es `65000`. De esta manera, evita la advertencia y también se controlan algunos casos extremos, como, por ejemplo, si alguien llamó a `new UTF7Encoding()` o incluyó el tipo en una subclase.

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

- Debe usar <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> o <xref:System.Text.UTF7Encoding>:

  Puede suprimir la advertencia `SYSLIB0001` en el código o en el archivo *.csproj* del proyecto.

  ```csharp
  #pragma warning disable SYSLIB0001 // Disable the warning.
  Encoding enc = Encoding.UTF7;
  #pragma warning restore SYSLIB0001 // Re-enable the warning.
  ```

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > La supresión de `SYSLIB0001` solo deshabilita las advertencias <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> y <xref:System.Text.UTF7Encoding> de elementos obsoletos. No deshabilita ninguna otra advertencia ni cambia el comportamiento de API como <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.

- Si se necesita la compatibilidad con `Encoding.GetEncoding("utf-7", ...)`:

  Puede volver a habilitarla mediante un modificador de compatibilidad. Este modificador de compatibilidad se puede especificar en el archivo *. csproj* de la aplicación o en un [archivo de configuración en tiempo de ejecución](../../../run-time-config/index.md), como se muestra en los ejemplos siguientes.

  En el archivo *.csproj* de la aplicación:

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- Re-enable support for UTF-7 -->
     <EnableUnsafeUTF7Encoding>true</EnableUnsafeUTF7Encoding>
    </PropertyGroup>
  </Project>
  ```

  En el archivo *runtimeConfig.template.json* de la aplicación:

  ```json
  {
    "configProperties": {
      "System.Text.Encoding.EnableUnsafeUTF7Encoding": true
    }
  }
  ```

  > [!TIP]
  > Si vuelve a habilitar la compatibilidad con UTF-7, debe realizar una revisión de seguridad del código que llama a <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Text.Encoding.UTF7?displayProperty=fullName>
- <xref:System.Text.UTF7Encoding.%23ctor>
- <xref:System.Text.UTF7Encoding.%23ctor(System.Boolean)>
- <xref:System.Text.Encoding.GetEncoding(System.Int32)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncodings?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `System.Text.Encoding.UTF7`
- `System.Text.UTF7Encoding.#ctor`
- `System.Text.UTF7Encoding.#ctor(System.Boolean)`
- `System.Text.Encoding.GetEncoding(System.Int32)`
- `System.Text.Encoding.GetEncoding(System.String)`
- `System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncodings`

-->
