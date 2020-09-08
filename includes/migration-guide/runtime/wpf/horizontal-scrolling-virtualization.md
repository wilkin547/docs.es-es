---
ms.openlocfilehash: 2ae17e0823ec2fa064c948d9ea7bd19cbd34cb6a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496899"
---
### <a name="horizontal-scrolling-and-virtualization"></a>Desplazamiento horizontal y virtualización

#### <a name="details"></a>Detalles

Este cambio se aplica a un elemento <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> que realiza su propia virtualización en la dirección ortogonal hacia la dirección de desplazamiento principal (el ejemplo principal es <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> con EnableColumnVirtualization=&quot;True&quot;).  Se cambió el resultado de determinadas operaciones de desplazamiento horizontal para producir resultados más intuitivos y más parecidos a los de las operaciones verticales comparables.<p/>Las operaciones incluyen &quot;Desplazar aquí&quot; y &quot;Borde derecho&quot;, para usar los nombres del menú que se obtiene al hacer clic con el botón derecho en una barra de desplazamiento horizontal.  En ambos casos se calcula un desplazamiento posible y se llama a <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>.<p/>Tras desplazarse hasta el desplazamiento nuevo, puede haber cambiado la definición de &quot;aquí&quot; o &quot;borde derecho&quot; porque el contenido recién desvirtualizado haya cambiado el valor de <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName>.<p/>Antes de .NET Framework 4.6.2, la operación de desplazamiento simplemente usa el desplazamiento posible, aunque puede que ya no sea &quot;aquí&quot; o en el &quot;borde derecho&quot;.  Esto produce efectos como el &quot;rebote&quot; de la miniatura de desplazamiento, que se muestra mejor con un ejemplo. Suponga que un control <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> tiene ExtentWidth=1000 y Width=200.  Un desplazamiento de &quot;Borde derecho&quot; usa el desplazamiento posible de 1000 - 200 = 800.  Al dirigirse al desplazamiento, las columnas nuevas se desvirtualizan; supongamos que son muy amplias, por lo que <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName> cambia a 2000.  El desplazamiento termina con HorizontalOffset=800, y la miniatura &quot;rebota&quot; de nuevo casi a la mitad de la barra de desplazamiento; precisamente a 800/2000 = 40 %.<p/>El cambio es para volver a calcular un nuevo desplazamiento posible cuando se produce esta situación y volver a intentarlo. (Así es cómo funciona ya el desplazamiento vertical). <p/>El cambio produce una experiencia más predecible e intuitiva para el usuario final, pero también podría afectar a cualquier aplicación que dependa del valor exacto de <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=fullName> después de un desplazamiento horizontal, independientemente de que la invocación la realice el usuario final o una llamada explícita a <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>.

#### <a name="suggestion"></a>Sugerencia

Una aplicación que use un valor de predicción para <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=fullName> se debe cambiar para recuperar el valor real (y el valor de <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName>) después de cualquier desplazamiento horizontal que pudiera cambiar <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName> debido a la desvirtualización.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Controls.Primitives.IScrollInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.Primitives.IScrollInfo`

-->
