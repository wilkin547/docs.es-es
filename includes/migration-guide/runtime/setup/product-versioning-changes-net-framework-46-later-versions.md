---
ms.openlocfilehash: 6a79f04af44f78313c4d5bb5c37dfad252d3024b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496293"
---
### <a name="product-versioning-changes-in-the-net-framework-46-and-later-versions"></a>Cambios en las versiones de producto en .NET Framework 4.6 y versiones posteriores

#### <a name="details"></a>Detalles

El control de versiones del producto ha cambiado desde las versiones anteriores de .NET Framework y especialmente .NET Framework 4, 4.5, 4.5.1 y 4.5.2. Estos son los cambios detallados:<ul><li>El valor de la entrada <code>Version</code> en la clave <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full</code> ha cambiado a <code>4.6.xxxxx</code> para .NET Framework 4.6 y sus versiones secundarias, y a <code>4.7.xxxxx</code> para .NET Framework 4.7 y 4.7.1. En .NET Framework 4.5, 4.5.1 y 4.5.2, tenía el formato <code>4.5.xxxxx</code>.</li><li>El control de versiones de producto y archivo para los archivos de .NET Framework ha cambiado con respecto al esquema de control de versiones anterior de 4.0.30319.x a 4.6.X.0 para .NET Framework 4.6 y sus versiones secundarias, y a 4.7.X.0 para .NET Framework 4.7 y 4.7.1. Puede ver estos valores nuevos si examina las Propiedades del archivo después de hacer clic con el botón derecho en un archivo.</li><li>Los atributos <xref:System.Reflection.AssemblyFileVersionAttribute> y <xref:System.Reflection.AssemblyInformationalVersionAttribute> de ensamblados administrados tienen valores Version con el formato 4.6.X.0 para .NET Framework 4.6 y sus versiones puntuales, y 4.7.X.0 para .NET Framework 4.7 y 4.7.1.</li><li>En .NET Framework 4.6, 4.6.1, 4.6.2, 4.7 y 4.7.1, la propiedad <xref:System.Environment.Version?displayProperty=nameWithType> devuelve la cadena de versión no editable <code>4.0.30319.42000</code>. En .NET Framework 4, 4.5, 4.5.1 y 4.5.2, devuelve cadenas de versión con el formato <code>4.0.30319.xxxxx</code> (por ejemplo, &quot;4.0.30319.18010&quot;). Tenga en cuenta que no se recomienda que el código de la aplicación tome nuevas dependencias en la propiedad Environment.Version.</li></ul>Para obtener más información, vea [Cómo: Determinar qué versiones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).

#### <a name="suggestion"></a>Sugerencia

En general, las aplicaciones deben depender de las técnicas recomendadas para detectar elementos como la versión del tiempo de ejecución de .NET Framework y el directorio de instalación:<ul><li>Para detectar la versión de tiempo de ejecución de .NET Framework, vea [Cómo: Determinar qué versiones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</li><li>Para determinar la ruta de instalación de .NET Framework, utilice el valor de la entrada <code>InstallPath</code> en la clave <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full</code>.</li></ul> <blockquote> [!IMPORTANT] El nombre de la subclave es <code>NET Framework Setup</code>, no <code>.NET Framework Setup</code>.</blockquote> <ul><li>Para determinar la ruta de acceso de directorio a Common Language Runtime de .NET Framework, llame al método <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory?displayProperty=nameWithType>.</li><li>Para obtener la versión de CLR, llame al método <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion?displayProperty=nameWithType>. Para .NET Framework 4 y sus versiones secundarias (.NET Framework 4.5, 4.5.1, 4.5.2 y .NET Framework 4.6, 4.6.1, 4.6.2, 4.7 y 4.7.1), devuelve la cadena v4.0.30319.</li></ul>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
