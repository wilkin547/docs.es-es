---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614844"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>Excepción NullReferenceException en el código de control de excepciones de ImageSourceConverter.ConvertFrom

#### <a name="details"></a>Detalles

Un error en el código de control de excepciones <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> ha hecho que se produjese una excepción <xref:System.NullReferenceException?displayProperty=fullName> incorrecta en lugar de la excepción prevista (<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> o <xref:System.IO.FileNotFoundException?displayProperty=fullName>). Este cambio corrige el error para que el método produzca la excepción correcta. <p/>De forma predeterminada, todas las aplicaciones destinadas a .NET Framework 4.6.2 y versiones anteriores continuarán iniciando la excepción <xref:System.NullReferenceException?displayProperty=fullName> por motivos de compatibilidad. Los desarrolladores que seleccionen como destino .NET Framework 4.7 y versiones posteriores debería ver las excepciones correctas.

#### <a name="suggestion"></a>Sugerencia

Los desarrolladores que quieran seguir obteniendo una excepción <xref:System.NullReferenceException?displayProperty=fullName> cuando el destino sea .NET Framework 4.7 o versiones posteriores, pueden agregar o combinar lo siguiente en el archivo App.config de la aplicación:

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>
