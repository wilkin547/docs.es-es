---
title: Información general sobre el uso del diseño automático
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: d4a0fd819d08fdd936dd1ef35e8cd8c00947f9e0
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662681"
---
# <a name="use-automatic-layout-overview"></a>Información general sobre el uso del diseño automático

Este tema presentan las directrices para desarrolladores sobre cómo escribir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones con localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]. En el pasado, la localización de una interfaz de usuario era un proceso lento. Todos los idiomas que se adaptaba la interfaz de usuario requiere un ajuste píxel a píxel. Hoy en día con el diseño correcto y derecha estándares de codificación, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] puede crearse para que los localizadores deban realizar menos el cambio de tamaño y posición. El enfoque para escribir aplicaciones que pueden ser más fácil cambiar el tamaño y la posición se denomina diseño automático y se puede lograr mediante el uso de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño de la aplicación.

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a>Ventajas de usar el diseño automático

Dado que el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de presentación es eficaz y flexible, proporciona la capacidad de diseñar elementos en una aplicación que se pueden ajustar para ajustarse a los requisitos de idiomas diferentes. En la lista siguiente se indican algunas de las ventajas del diseño automático.

- Interfaz de usuario se muestra correctamente en cualquier idioma.

- Reduce la necesidad de reajustar la posición y el tamaño de los controles una vez traducido el texto.

- Reduce la necesidad de reajustar el tamaño de la ventana.

- Diseño de interfaz de usuario se representa correctamente en cualquier lenguaje.

- La localización se puede reducir hasta el punto de que es poco más que la traducción de cadenas.

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a>Diseño automático y controles

El diseño automático permite que una aplicación ajuste automáticamente el tamaño de un control. Por ejemplo, un control puede cambiar para adaptarse a la longitud de una cadena. Esta capacidad permite a los localizadores traducir la cadena sin necesidad de cambiar el tamaño del control para que se ajuste al texto traducido. En el ejemplo siguiente se crea un botón con contenido en inglés.

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

En el ejemplo, lo único que debe hacer para crear un botón en español es cambiar el texto. Por ejemplo,

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

El gráfico siguiente muestra la salida de los ejemplos de código:

![El mismo botón con texto en diferentes idiomas](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a>Diseño automático y estándares de codificación

Con el enfoque de diseño automático requiere un conjunto de código y los estándares de diseño y las reglas para generar una interfaz de usuario totalmente localizable. Las instrucciones siguientes le ayudarán en la codificación del diseño automático.

**No use posiciones absolutas**

- No utilice <xref:System.Windows.Controls.Canvas> porque absolutamente coloca los elementos.

- Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, y <xref:System.Windows.Controls.Grid> para colocar los controles.

Para obtener información sobre los distintos tipos de paneles, consulte [información general sobre](../controls/panels-overview.md).

**No establezca un tamaño fijo para una ventana**

- Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>. Por ejemplo:

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

**Agregar un <xref:System.Windows.FrameworkElement.FlowDirection%2A>**

- Agregar un <xref:System.Windows.FrameworkElement.FlowDirection%2A> al elemento raíz de la aplicación.

  WPF proporciona una manera cómoda de admitir horizontales, bidireccionales y diseños verticales. En el marco de presentación, el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad puede usarse para definir el diseño. Los patrones de dirección de flujo son:

  - <xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb): diseño horizontal para latín, Asia oriental y así sucesivamente.

  - <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb): bidireccional para árabe, hebreo y así sucesivamente.

**Use fuentes compuestas en lugar de fuentes físicas**

- Con las fuentes compuestas, el <xref:System.Windows.Controls.Control.FontFamily%2A> propiedad no deben localizarse.

- Los desarrolladores pueden usar una de las fuentes siguientes o crear sus propias fuentes.

  - Interfaz de usuario global
  - Global San Serif
  - Global Serif

**Agregue XML: lang**

- Agregar el `xml:lang` atributo en el elemento raíz de la interfaz de usuario, como `xml:lang="en-US"` para una aplicación en inglés.

- Dado que las fuentes compuestas usan `xml:lang` para determinar qué fuente quiere usar, establezca esta propiedad para admitir escenarios multilingües.

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a>Diseño automático y cuadrículas

El <xref:System.Windows.Controls.Grid> elemento, es útil para el diseño automático porque permite al programador colocar los elementos. Un <xref:System.Windows.Controls.Grid> control es capaz de distribuir el espacio disponible entre sus elementos secundarios, en una disposición de columna y fila. Los elementos de interfaz de usuario pueden abarcar varias celdas, y es posible que haya cuadrículas dentro de cuadrículas. Las cuadrículas son útiles porque permiten crear y colocar la IU es compleja. En el ejemplo siguiente se muestra cómo se usa una cuadrícula para colocar algunos botones y texto. Tenga en cuenta que el alto y ancho de las celdas están establecidos en <xref:System.Windows.GridUnitType.Auto>; por lo tanto, la celda que contiene el botón con una imagen se ajusta para que quepa la imagen.

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

En el gráfico siguiente se muestra la cuadrícula que ha producido el código anterior.

![Ejemplo de cuadrícula](./media/glob-grid.png "glob_grid") cuadrícula

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Diseño automático y cuadrículas mediante el uso de la propiedad IsSharedSizeScope

Un <xref:System.Windows.Controls.Grid> elemento es útil en aplicaciones localizables para crear controles que se ajustan al contenido. Pero en ocasiones le interesará que los controles conserven un tamaño determinado independientemente del contenido. Por ejemplo, si tiene los botones "Aceptar", "Cancelar" y "Examinar", probablemente no le interesará que su tamaño se ajuste el contenido. En este caso el <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> propiedad adjunta es útil para compartir el mismo tamaño entre varios elementos de la cuadrícula. En el ejemplo siguiente se muestra cómo compartir datos entre varias de tamaño de fila y columna <xref:System.Windows.Controls.Grid> elementos.

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> El ejemplo de código completo, vea [recurso compartido de las propiedades de ajuste de tamaño entre cuadrículas](../controls/how-to-share-sizing-properties-between-grids.md)

## <a name="see-also"></a>Vea también

- [Globalización de WPF](globalization-for-wpf.md)
- [Usar el diseño automático para crear un botón](how-to-use-automatic-layout-to-create-a-button.md)
- [Usar una cuadrícula para el diseño automático](how-to-use-a-grid-for-automatic-layout.md)
