---
title: Información general sobre el uso del diseño automático
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 0253c57f080705b648d9f416368d0fe974ac83ab
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834665"
---
# <a name="use-automatic-layout-overview"></a>Información general sobre el uso del diseño automático

En este tema se presentan instrucciones para desarrolladores sobre cómo escribir aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] con @no__t localizable-1. En el pasado, la localización de una interfaz de usuario era un proceso que consume mucho tiempo. Cada idioma al que se adapta la interfaz de usuario requiere un ajuste de píxel por píxel. En la actualidad, con el diseño correcto y los estándares de codificación correctos, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] se pueden construir para que los localizadores tengan menos cambio de tamaño y reposición. El método para escribir aplicaciones a las que se puede cambiar el tamaño y la posición de forma más sencilla se denomina diseño automático y se puede lograr mediante el diseño de la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a>Ventajas de usar el diseño automático

Dado que el sistema de presentación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es eficaz y flexible, proporciona la capacidad de diseñar elementos en una aplicación que se puede ajustar para ajustarse a los requisitos de distintos lenguajes. En la lista siguiente se indican algunas de las ventajas del diseño automático.

- La interfaz de usuario se muestra bien en cualquier lenguaje.

- Reduce la necesidad de reajustar la posición y el tamaño de los controles una vez traducido el texto.

- Reduce la necesidad de reajustar el tamaño de la ventana.

- El diseño de la interfaz de usuario se representa correctamente en cualquier lenguaje.

- La localización se puede reducir hasta el punto de que es poco más que la traducción de cadenas.

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a>Diseño automático y controles

El diseño automático permite que una aplicación ajuste automáticamente el tamaño de un control. Por ejemplo, un control puede cambiar para adaptarse a la longitud de una cadena. Esta capacidad permite a los localizadores traducir la cadena sin necesidad de cambiar el tamaño del control para que se ajuste al texto traducido. En el ejemplo siguiente se crea un botón con contenido en inglés.

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

En el ejemplo, lo único que debe hacer para crear un botón en español es cambiar el texto. Por ejemplo,

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

En el gráfico siguiente se muestra la salida de los ejemplos de código:

![El mismo botón con texto en diferentes idiomas](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a>Diseño automático y estándares de codificación

El uso del enfoque de diseño automático requiere un conjunto de reglas y estándares de diseño y codificación para generar una interfaz de usuario totalmente localizable. Las instrucciones siguientes le ayudarán en la codificación del diseño automático.

**No usar posiciones absolutas**

- No utilice <xref:System.Windows.Controls.Canvas> porque coloca los elementos de forma absoluta.

- Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> y <xref:System.Windows.Controls.Grid> para colocar los controles.

Para obtener una explicación sobre los distintos tipos de paneles, consulte [información general](../controls/panels-overview.md)de los paneles.

**No establecer un tamaño fijo para una ventana**

- Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>. Por ejemplo:

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

**Agregar un <xref:System.Windows.FrameworkElement.FlowDirection%2A>**

- Agregue un <xref:System.Windows.FrameworkElement.FlowDirection%2A> al elemento raíz de la aplicación.

  WPF proporciona una manera cómoda de admitir diseños horizontales, bidireccionales y verticales. En el marco de presentación, se puede usar la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> para definir el diseño. Los patrones de dirección de flujo son:

  - <xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb): diseño horizontal para latín, Asia oriental, etc.

  - <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb): bidireccional para árabe, hebreo, etc.

**Usar fuentes compuestas en lugar de fuentes físicas**

- Con las fuentes compuestas, no es necesario localizar la propiedad <xref:System.Windows.Controls.Control.FontFamily%2A>.

- Los desarrolladores pueden usar una de las fuentes siguientes o crear sus propias fuentes.

  - Interfaz de usuario global
  - Global San Serif
  - Global Serif

**Agregar XML: lang**

- Agregue el atributo `xml:lang` en el elemento raíz de la interfaz de usuario, como `xml:lang="en-US"` para una aplicación en inglés.

- Dado que las fuentes compuestas usan `xml:lang` para determinar qué fuente usar, establezca esta propiedad para admitir escenarios multilingües.

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a>Diseño automático y cuadrículas

El elemento <xref:System.Windows.Controls.Grid>, es útil para el diseño automático porque permite a un desarrollador colocar los elementos. Un control <xref:System.Windows.Controls.Grid> es capaz de distribuir el espacio disponible entre sus elementos secundarios, utilizando una organización de columnas y filas. Los elementos de la interfaz de usuario pueden abarcar varias celdas y es posible tener cuadrículas dentro de las cuadrículas. Las cuadrículas son útiles porque permiten crear y colocar la interfaz de usuario compleja. En el ejemplo siguiente se muestra cómo se usa una cuadrícula para colocar algunos botones y texto. Observe que el alto y el ancho de las celdas están establecidos en <xref:System.Windows.GridUnitType.Auto>; por lo tanto, la celda que contiene el botón con una imagen se ajusta para ajustarse a la imagen.

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

En el gráfico siguiente se muestra la cuadrícula que ha producido el código anterior.

![Ejemplo de cuadrícula](./media/glob-grid.png "glob_grid") Grid

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Diseño automático y cuadrículas mediante el uso de la propiedad IsSharedSizeScope

Un elemento <xref:System.Windows.Controls.Grid> resulta útil en las aplicaciones localizables para crear controles que se ajusten para ajustarse al contenido. Pero en ocasiones le interesará que los controles conserven un tamaño determinado independientemente del contenido. Por ejemplo, si tiene los botones "Aceptar", "Cancelar" y "Examinar", probablemente no le interesará que su tamaño se ajuste el contenido. En este caso, la propiedad adjunta <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> resulta útil para compartir el mismo tamaño entre varios elementos de la cuadrícula. En el ejemplo siguiente se muestra cómo compartir datos de tamaño de columnas y filas entre varios elementos <xref:System.Windows.Controls.Grid>.

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> Para obtener el ejemplo de código completo, vea [compartir propiedades de ajuste de tamaño entre cuadrículas](../controls/how-to-share-sizing-properties-between-grids.md).

## <a name="see-also"></a>Vea también

- [Globalización de WPF](globalization-for-wpf.md)
- [Usar el diseño automático para crear un botón](how-to-use-automatic-layout-to-create-a-button.md)
- [Usar una cuadrícula para el diseño automático](how-to-use-a-grid-for-automatic-layout.md)
