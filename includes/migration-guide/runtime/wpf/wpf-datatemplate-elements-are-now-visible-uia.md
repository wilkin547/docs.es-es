---
ms.openlocfilehash: 06c699281c8890ac65be1d282b72b54774acc280
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620710"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a>Los elementos DataTemplate de WPF ahora son visibles en la UIA

#### <a name="details"></a>Detalles

Anteriormente, los elementos <xref:System.Windows.DataTemplate?displayProperty=fullName> no eran visibles para la automatización de la interfaz de usuario. A partir de la versión 4.5, la automatización de la IU detectará estos elementos. Esto resulta útil en muchos casos, pero puede interrumpir las pruebas que dependan de árboles de la UIA que no contengan elementos <xref:System.Windows.DataTemplate?displayProperty=fullName>.

#### <a name="suggestion"></a>Sugerencia

Puede ser necesario actualizar las pruebas de automatización de la interfaz de usuario para esta aplicación con el fin de procesar el árbol de la UIA que ahora incluye elementos <xref:System.Windows.DataTemplate?displayProperty=fullName> que antes no eran visibles. Por ejemplo, en aquellas pruebas en las que se espere que haya ciertos elementos contiguos entre sí, ahora puede ser necesario esperar ciertos elementos intermedios de la UIA que antes no eran visibles. También puede ser necesario actualizar con nuevos valores pruebas que dependan de ciertos recuentos o índices para elementos de la UIA.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.DataTemplate.%23ctor></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)></li></ul>|
