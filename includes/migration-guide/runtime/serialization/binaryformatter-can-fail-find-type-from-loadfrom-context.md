---
ms.openlocfilehash: ccba3cf98a1ca9e199d9a48f00e254bf34b93f72
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497130"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a>BinaryFormatter no puede encontrar el tipo en el contexto LoadFrom

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, un número de cambios en <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> pueden provocar diferencias en la deserialización al usar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> para deserializar los tipos que se han cargado en el contexto LoadFrom. Estos cambios se deben a las nuevas formas en las que <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> carga ahora un tipo que provoca otro comportamiento cuando un <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> intenta deserializar en ese tipo más adelante. El enlazador de serialización predeterminado no busca automáticamente en el contexto LoadFrom, aunque es posible que haya funcionado en algunas circunstancias según el comportamiento anterior de XmlSerializer. Debido a los cambios, cuando se carga un tipo desde un ensamblado cargado en un otro contexto, se puede iniciar una excepción <xref:System.IO.FileNotFoundException?displayProperty=fullName>.

#### <a name="suggestion"></a>Sugerencia

Si esta excepción aparece, la propiedad <code>Binder</code> del <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> se puede establecer en un enlazador predeterminado que encontrará el tipo correcto.<pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre>Y, después, el enlazador predeterminado:<pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
