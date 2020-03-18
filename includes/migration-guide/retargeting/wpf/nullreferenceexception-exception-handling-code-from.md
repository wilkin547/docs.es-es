---
ms.openlocfilehash: 824d75585efd40937c1a48376ec7862cba1a8fa3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235593"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>Excepción NullReferenceException en el código de control de excepciones de ImageSourceConverter.ConvertFrom

|   |   |
|---|---|
|Detalles|Un error en el código de control de excepciones <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> ha hecho que se produjese una excepción <xref:System.NullReferenceException?displayProperty=name> incorrecta en lugar de la excepción prevista (<xref:System.IO.DirectoryNotFoundException?displayProperty=name> o <xref:System.IO.FileNotFoundException?displayProperty=name>). Este cambio corrige el error para que el método produzca la excepción correcta. <p/>De forma predeterminada, todas las aplicaciones destinadas a .NET Framework 4.6.2 y versiones anteriores continuarán iniciando la excepción <xref:System.NullReferenceException?displayProperty=name> por motivos de compatibilidad. Los desarrolladores que seleccionen como destino .NET Framework 4.7 y versiones posteriores debería ver las excepciones correctas.|
|Sugerencia|Los desarrolladores que quieran seguir obteniendo una excepción <xref:System.NullReferenceException?displayProperty=name> cuando el destino sea .NET Framework 4.7 o versiones posteriores, pueden agregar o combinar lo siguiente en el archivo App.config de la aplicación:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.7|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType></li></ul>|
