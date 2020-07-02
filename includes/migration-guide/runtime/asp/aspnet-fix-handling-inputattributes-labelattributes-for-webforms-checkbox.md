---
ms.openlocfilehash: ae557ce57557d027dba35b7da213c08aee85f2c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622074"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>Se ha corregido el procesamiento de ASP.NET en InputAttributes y LabelAttributes para el control de casilla de WebForms

#### <a name="details"></a>Detalles

Para las aplicaciones que tienen como destino .NET Framework 4.7.2 y versiones anteriores, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> y <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> que se agregan mediante programación a un control <xref:System.Web.UI.WebControls.CheckBox> de WebForms se pierden después del postback. Para las aplicaciones que tienen como destino .NET Framework 4.8 o versiones posteriores, se mantienen después del postback.

#### <a name="suggestion"></a>Sugerencia

Para obtener el comportamiento correcto para restaurar los atributos en el postback, establezca <code>targetFrameworkVersion</code> en 4.8 o posterior. Por ejemplo:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Si se establece en una versión inferior, o en ninguna, se conserva el antiguo comportamiento incorrecto.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Desconocido|
|Versión|4.8|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
