---
ms.openlocfilehash: b92dc8a1c48e83846c3d9a1d86e66629f31b7722
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622121"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>Incapacidad intermitente para desplazarse hasta el último elemento de instancias ItemsControl (como ListBox y DataGrid) al usar elementos DataTemplate personalizados

#### <a name="details"></a>Detalles

En algunos casos, un error de .NET Framework 4.5 impide que las instancias de ItemsControl (como <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) se desplacen hasta su último elemento cuando se usan elementos DataTemplate personalizados. Si se trata de efectuar el desplazamiento una segunda vez (después de haber vuelto arriba), sí funciona.

#### <a name="suggestion"></a>Sugerencia

Este problema se resolvió en .NET Framework 4.5.2, por lo que otra posible solución es actualizar a esta versión (u otra posterior) de .NET Framework. Los usuarios también pueden arrastrar las barras de desplazamiento hasta los últimos elementos de estas colecciones, pero puede ser posible que tengan que hacerlo dos veces para conseguirlo.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
