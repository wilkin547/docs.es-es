---
ms.openlocfilehash: 7cb146d19486618a4cee9976abe2220ea4b72790
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "88204092"
---
### <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a>Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET

Los métodos `Serialize` y `Deserialize` en <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter> y <xref:System.Runtime.Serialization.IFormatter> ahora están obsoletos. Además, la serialización de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> está prohibida de forma predeterminada en aplicaciones de ASP.NET.

#### <a name="change-description"></a>Descripción del cambio

Debido a las [vulnerabilidades de seguridad](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, los siguientes métodos ahora están obsoletos. Además, en las aplicaciones ASP.NET Core 5.0 y versiones posteriores, iniciarán una excepción <xref:System.NotSupportedException>, a menos que la aplicación web haya vuelto a habilitar la funcionalidad <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

En un esfuerzo por poner fin al uso de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> dentro del ecosistema de .NET, estos métodos están marcados como obsoletos.

Los siguientes métodos de serialización también están ya obsoletos, pero no presentan cambios de comportamiento:

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

- Deje de usar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> en el código. Considere mejor el uso de <xref:System.Text.Json.JsonSerializer> o <xref:System.Xml.Serialization.XmlSerializer>. Para más información, consulte [Guía de seguridad de BinaryFormatter](../../../../docs/standard/serialization/binaryformatter-security-guide.md).

- Puede suprimir temporalmente la advertencia en tiempo de compilación de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, que es `SYSLIB0011`. Le recomendamos que evalúe detenidamente el código para detectar los riesgos antes de elegir esta opción. La manera más fácil de suprimir las advertencias es colocar directivas `#pragma` en torno al sitio de llamada individual.

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  También puede suprimir la advertencia en el archivo del proyecto.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  Si suprime la advertencia en el archivo del proyecto, se suprime la advertencia para todos los archivos de código del proyecto. La supresión de SYSLIB0011 no suprime las advertencias causadas por el uso de otras API obsoletas.

- Para seguir usando <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> en aplicaciones ASP.NET, puede volver a habilitarlo en el archivo del proyecto. Sin embargo, se recomienda encarecidamente no hacerlo. Para más información, consulte [Guía de seguridad de BinaryFormatter](../../../../docs/standard/serialization/binaryformatter-security-guide.md).

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

Para más información sobre las acciones recomendadas, consulte [Resolución de errores de desactivación y deshabilitación de BinaryFormatter](https://aka.ms/binaryformatter).

#### <a name="category"></a>Categoría

- Bibliotecas de Core .NET
- ASP.NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
