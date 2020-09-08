---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497780"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF ahora serializa el valor Expressions.Literal&lt;T&gt; DateTimes de forma diferente (interrumpe los analizadores de XAML personalizados)

#### <a name="details"></a>Detalles

El objeto <xref:System.Windows.Markup.ValueSerializer> asociado convertirá un objeto <xref:System.DateTime?displayProperty=fullName> o <xref:System.DateTimeOffset?displayProperty=fullName> cuyos componentes Second y <xref:System.DateTime.Millisecond?displayProperty=fullName> sean distintos de cero y (para un valor <xref:System.DateTime?displayProperty=fullName>) cuya propiedad <xref:System.DateTime.Kind> no sea Unspecified en la sintaxis del elemento de propiedad en lugar de en una cadena. Este cambio permite realizar un recorrido de ida y vuelta por los valores <xref:System.DateTime?displayProperty=fullName> y <xref:System.DateTimeOffset?displayProperty=fullName>. Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.

#### <a name="suggestion"></a>Sugerencia

Este cambio permite realizar un recorrido de ida y vuelta por los valores <xref:System.DateTime?displayProperty=fullName> y <xref:System.DateTimeOffset?displayProperty=fullName>. Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
