---
ms.openlocfilehash: 0036fc2b03dde64d24d883e55b9f00c931f0c218
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997716"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a>La interoperabilidad de .NET se ejecutará ahora con QueryInterface para IAgileObject (una interfaz de WinRT)

|   |   |
|---|---|
|Detalles|Cuando se usa un evento de WinRT con un delegado de .NET, Windows se ejecutará con QI para IAgileObject a partir de .NET Framework 4.8.  En versiones anteriores de .NET Framework, el tiempo de ejecución producía un error en el QI y el evento no se podrá suscribir.<ul><li>[x] Anómalo</li></ul>|
|Sugerencia|Si habilitar el QI para IAgileObject interrumpe la ejecución, puede deshabilitar este código estableciendo la configuración siguiente. <h4>Método 1: Variable de entorno</h4> Establezca la siguiente variable de entorno: COMPLUS_DisableCCWSupportIAgileObject = 1Este método afecta a cualquier entorno que herede esta variable de entorno. Podría tratarse simplemente de una sesión de consola única, o podría afectar a toda la máquina si establece la variable de entorno global. El nombre de la variable de entorno no distingue mayúsculas de minúsculas. <h4>Método 2: Registro</h4> Con el Editor del registro (regedit.exe), busque cualquiera de las siguientes subclaves:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkA continuación, agregue la siguiente: Nombre de valor: DisableCCWSupportIAgileObject Tipo: DWORD (32 bits) Valor (también denominado REG_WORD) Valor: 1Puede usar la herramienta de Windows REG.EXE para agregar este valor desde una línea de comandos o un entorno de scripting. Por ejemplo:<pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre>En este caso, se usa <code>HKLM</code> en lugar de <code>HKEY_LOCAL_MACHINE</code>. Use <code>reg add /?</code> para ver la ayuda sobre esta sintaxis. El nombre del valor de registro no distingue mayúsculas de minúsculas.|
|Ámbito|Borde|
|Versión|4.8|
|Tipo|Tiempo de ejecución|
