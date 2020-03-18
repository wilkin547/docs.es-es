---
ms.openlocfilehash: 72f907c117748fb19ca0663f24445a8c978afd32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235521"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle espera ahora el valor HWND

|   |   |
|---|---|
|Detalles|El valor <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>, introducido en .NET Framework 2.0, permite que una aplicación registre un valor de identificador de ventana principal, de modo que cualquier interfaz de usuario necesaria para tener acceso a la clave (por ejemplo, una solicitud del PIN o un cuadro de diálogo de consentimiento) se abra como elemento secundario modal de la ventana especificada. A partir de las aplicaciones destinadas a .NET Framework 4.7, una aplicación de Windows Forms puede establecer la propiedad <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> con código similar al siguiente:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>En versiones anteriores de .NET Framework, se esperaba que el valor fuera un <xref:System.IntPtr?displayProperty=name> que representara una ubicación en memoria donde se encontraba el valor [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND). Establecer la propiedad en form.Handle no tenía ningún efecto en Windows 7 y versiones anteriores, pero en Windows 8 y versiones posteriores, da como resultado &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=name>: El parámetro no es correcto&quot;.|
|Sugerencia|Para las aplicaciones destinadas a .NET Framework 4.7 o versiones posteriores que quieran registrar una relación de ventana principal, se recomienda usar la forma simplificada:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>Los usuarios que hayan identificado que el valor correcto para pasar era la dirección de una ubicación de memoria que contenía el valor <code>form.Handle</code>, pueden rechazar este cambio de comportamiento si establecen el modificador de AppContext <code>Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle</code> en <code>true</code>:<ol><li>Configurando mediante programación los modificadores de compatibilidad en AppContext, como se explica [aquí](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</li><li>Agregando la siguiente línea a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>En cambio, los usuarios que quieran incluir el comportamiento nuevo en el entorno de ejecución de .NET Framework 4.7 cuando la aplicación se carga bajo versiones anteriores de .NET Framework, pueden establecer el modificador de AppContext en <code>false</code>.|
|Ámbito|Secundaria|
|Versión|4.7|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType></li></ul>|
