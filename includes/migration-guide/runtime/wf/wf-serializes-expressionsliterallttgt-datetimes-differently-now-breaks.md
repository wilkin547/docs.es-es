---
ms.openlocfilehash: 335647f899c79eff22e313fa40b2e2a73e7cfff0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379555"
---
### <a name="wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF ahora serializa el valor Expressions.Literal\<T> DateTimes de forma diferente (interrumpe los analizadores de XAML personalizados)

|   |   |
|---|---|
|Detalles|El objeto <xref:System.Windows.Markup.ValueSerializer> asociado convertirá un objeto <xref:System.DateTime?displayProperty=name> o <xref:System.DateTimeOffset?displayProperty=name> cuyos componentes Second y <xref:System.DateTime.Millisecond?displayProperty=name> sean distintos de cero y (para un valor <xref:System.DateTime?displayProperty=name>) cuya propiedad <xref:System.DateTime.Kind> no sea Unspecified en la sintaxis del elemento de propiedad en lugar de en una cadena. Este cambio permite realizar un recorrido de ida y vuelta por los valores <xref:System.DateTime?displayProperty=name> y <xref:System.DateTimeOffset?displayProperty=name>. Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.|
|Sugerencia|Este cambio permite realizar un recorrido de ida y vuelta por los valores <xref:System.DateTime?displayProperty=name> y <xref:System.DateTimeOffset?displayProperty=name>. Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
