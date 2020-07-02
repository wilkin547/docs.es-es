---
ms.openlocfilehash: 135d59de135c8416d384b221379f912c8a9172ad
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622071"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a>El control incorrecto de varias partes de ASP.NET puede dar lugar a que se pierdan datos de formularios.

#### <a name="details"></a>Detalles

En las aplicaciones que tienen como destino .NET Framework 4.7.2 y versiones anteriores, ASP.Net podría analizar incorrectamente valores de límite de varias partes, lo que da lugar a que los datos de formulario no estén disponibles durante la ejecución de la solicitud. Las aplicaciones que tienen como destino .NET Framework 4.8 o versiones posteriores analizan correctamente datos de varias partes, por lo que los valores del formulario están disponibles durante la ejecución de la solicitud.

#### <a name="suggestion"></a>Sugerencia

A partir de las aplicaciones que se ejecutan en .NET Framework 4.8, cuando el destino sea .NET Framework 4.8 o posterior mediante el uso del elemento <code>targetFrameworkVersion</code>, el comportamiento predeterminado cambia para quitar delimitadores. Cuando se usan versiones anteriores de Framework o no se usa <code>targetFrameworkVersion</code>, los delimitadores finales de algunos valores todavía se devuelven.Este comportamiento también se puede controlar explícitamente con <code>appSetting</code>:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Desconocido|
|Versión|4.8|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Web.HttpRequest.Form?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.Files?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
