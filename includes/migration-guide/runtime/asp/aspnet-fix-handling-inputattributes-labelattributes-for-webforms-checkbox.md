---
ms.openlocfilehash: ea0e1583cd611a624cf2d2edf9defb2294eb89d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802703"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>Se ha corregido el procesamiento de ASP.NET en InputAttributes y LabelAttributes para el control de casilla de WebForms

|   |   |
|---|---|
|Detalles|Para las aplicaciones que tienen como destino .NET Framework 4.7.2 y versiones anteriores, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> y <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> que se agregan mediante programación a un control <xref:System.Web.UI.WebControls.CheckBox> de WebForms se pierden después del postback. Para las aplicaciones que tienen como destino .NET Framework 4.8 o versiones posteriores, se mantienen después del postback.|
|Sugerencia|Para obtener el comportamiento correcto para restaurar los atributos en el postback, establezca <code>targetFrameworkVersion</code> en 4.8 o posterior. Por ejemplo:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Si se establece en una versión inferior, o en ninguna, se conserva el antiguo comportamiento incorrecto.|
|Ámbito|Desconocido|
|Versión|4.8|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
