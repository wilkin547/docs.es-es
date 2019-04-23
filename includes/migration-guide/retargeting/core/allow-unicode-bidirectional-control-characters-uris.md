---
ms.openlocfilehash: 3e9a1009167d8a765bc401d64a574bd123736ccd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774063"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a>Permitir caracteres de control bidireccional de Unicode en los URI

|   |   |
|---|---|
|Detalles|Unicode especifica varios caracteres de control especiales que se usan para especificar la orientación del texto. En versiones anteriores de .NET Framework, estos caracteres se quitaban incorrectamente de todos los URI, incluso si ya estaban presentes en su forma codificada por porcentaje. Para seguir [RFC 3987](https://tools.ietf.org/html/rfc3987) mejor, ahora se permiten estos caracteres en los URI. Cuando se encuentran sin codificar en un URI, se codifican por porcentaje. Cuando se encuentran codificados por porcentaje, se dejan como están.|
|Sugerencia|Para las aplicaciones destinadas a versiones de .NET Framework a partir de la 4.7.2, la compatibilidad con los caracteres bidireccionales de Unicode está habilitada de forma predeterminada. Si no quiere este cambio, puede deshabilitarlo mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección <code>&lt;runtime&gt;</code> del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Para las aplicaciones destinadas a versiones anteriores de .NET Framework pero que se ejecutan en versiones a partir de .NET Framework 4.7.2, la compatibilidad con los caracteres bidireccionales de Unicode está deshabilitada de forma predeterminada. Puede habilitarla mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección <code>&lt;runtime&gt;</code> del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
