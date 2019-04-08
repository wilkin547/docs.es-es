---
ms.openlocfilehash: 4f92d773197c914a74dd7e9c18f5aab5309358ae
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760893"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>Asegurarse de que System.Uri usa un juego de caracteres reservados coherente

|   |   |
|---|---|
|Detalles|En <xref:System.Uri?displayProperty=fullName>, algunos caracteres codificados por porcentaje que en ocasiones se descodificaban ahora se dejan sin codificar de manera constante. Esto se produce en las propiedades y métodos que tienen acceso a los componentes de ruta de acceso, consulta, fragmento o información de usuario del URI. El comportamiento solo cambiará cuando se cumplen las dos acciones siguientes:<ul><li>El URI contiene el formato codificado de cualquiera de los caracteres reservados siguientes: <code>:</code>, <code>'</code>, <code>(</code>, <code>)</code>, <code>!</code> o <code>*</code>.</li><li>El URI contiene un carácter no reservado codificado o Unicode. Si se cumplen las dos condiciones anteriores, los caracteres reservados codificados se dejan codificados. En versiones anteriores de .NET Framework se descodificaban.</li></ul>|
|Sugerencia|Para las aplicaciones destinadas a versiones de .NET Framework a partir de 4.7.2, el nuevo comportamiento de descodificación está habilitado de forma predeterminada. Si no quiere este cambio, puede deshabilitarlo mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección <code>&lt;runtime&gt;</code> del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Para las aplicaciones destinadas a versiones anteriores de .NET Framework pero que se ejecutan en versiones a partir de .NET Framework 4.7.2, el comportamiento de descodificación nuevo está deshabilitado de forma predeterminada. Puede habilitarla mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección <code>&lt;runtime&gt;</code> del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|

