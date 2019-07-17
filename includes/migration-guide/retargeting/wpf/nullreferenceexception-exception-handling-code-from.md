---
ms.openlocfilehash: 122741d13294c8b137ce48e28f0aa39c6e36265a
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859071"
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

