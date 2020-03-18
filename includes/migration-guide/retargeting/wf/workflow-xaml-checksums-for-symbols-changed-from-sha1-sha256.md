---
ms.openlocfilehash: f814703e187726d3988787fac52e5049988fd4d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803531"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Sumas de comprobación de flujo de trabajo XAML para los símbolos que se han cambiado de SHA1 a SHA256

|   |   |
|---|---|
|Detalles|Para admitir la depuración con Visual Studio, el tiempo de ejecución de flujo de trabajo genera una suma de comprobación para un archivo XAML de flujo de trabajo mediante un algoritmo de hash. En .NET Framework 4.6.2 y versiones anteriores, el hash de suma de comprobación de flujo de trabajo usaba el algoritmo MD5, que causaba problemas en sistemas compatibles con FIPS. A partir de .NET Framework 4.7, el algoritmo predeterminado se ha cambiado a SHA1. A partir de .NET Framework 4.8, el algoritmo predeterminado se ha cambiado a SHA256.|
|Sugerencia|Si el código no puede cargar las instancias de flujo de trabajo o no puede buscar símbolos adecuados debido a un error de suma de comprobación, pruebe a establecer el valor <code>AppContext</code>Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot; del modificador &quot; en true. En el código:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot;, true);&#13;&#10;</code></pre>O bien, en la configuración:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.8|
|Tipo|Redestinación|
