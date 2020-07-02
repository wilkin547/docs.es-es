---
ms.openlocfilehash: 4303b177ffe01328965c909a5a3809414fcead91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614928"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a>Ahora el algoritmo hash predeterminado para el compilador de marcado de WPF es SHA256

#### <a name="details"></a>Detalles

MarkupCompiler de WPF proporciona servicios de compilación para los archivos de marcado XAML.  En .NET Framework 4.7.1 y versiones anteriores, el algoritmo hash predeterminado que se usaba para las sumas de comprobación era SHA1. Por motivos de seguridad recientes con SHA1, este valor predeterminado se ha cambiado a SHA256 a partir de .NET Framework 4.7.2.  Este cambio afecta a la generación de todas las sumas de comprobación para los archivos de marcado durante la compilación.

#### <a name="suggestion"></a>Sugerencia

Un desarrollador que tenga como destino .NET Framework 4.7.2 o una versión posterior y quiera revertir al comportamiento de los algoritmos hash SHA1 debe establecer la marca de AppContext siguiente.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Un desarrollador que quiera usar algoritmos hash SHA256, al tiempo que selecciona como destino una versión de .NET Framework inferior a la 4.7.2, debe establecer la marca de AppContext siguiente.  Tenga en cuenta que la versión instalada de .NET Framework debe ser 4.7.2 o posterior.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Transparente |
| Versión | 4.7.2       |
| Tipo    | Redestinación |
