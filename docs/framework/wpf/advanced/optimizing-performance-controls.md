---
title: 'Optimizar el rendimiento: -Controles de WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
ms.openlocfilehash: 20b2b20c2f7f37b4ae01159e70bc8c0945777152
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961400"
---
# <a name="optimizing-performance-controls"></a>Optimizar el rendimiento: Controles

Windows Presentation Foundation (WPF) incluye muchos de los componentes de interfaz de usuario (UI) comunes que se usan en la mayoría de las aplicaciones de Windows. Este tema contiene técnicas para mejorar el rendimiento de la interfaz de usuario.

## <a name="displaying-large-data-sets"></a>Mostrar grandes conjuntos de datos

Los controles de WPF, como el <xref:System.Windows.Controls.ListView> y <xref:System.Windows.Controls.ComboBox> se usan para mostrar listas de elementos en una aplicación. Si la lista para mostrar es grande, el rendimiento de la aplicación puede verse afectado. Esto ocurre porque el sistema de diseño estándar crea un contenedor de diseño para cada elemento asociado al control de lista y calcula el tamaño del diseño y la posición. Normalmente, no es necesario mostrar todos los elementos al mismo tiempo; en su lugar, muestra un subconjunto y el usuario se desplaza por la lista. En este caso, tiene sentido usar la *virtualización* de la interfaz de usuario, que significa que la generación de contenedores de elementos y el cálculo de diseño asociado para un elemento se aplaza hasta que el elemento es visible.

La virtualización de la interfaz de usuario es un aspecto importante de los controles de lista. No se debe confundir la virtualización de la interfaz de usuario con la virtualización de datos. La virtualización de la interfaz de imagen solo almacena elementos visibles en la memoria, pero, en un escenario de enlace de datos, almacena toda la estructura de datos en la memoria. En cambio, la virtualización de datos solo almacena en la memoria los elementos de datos que están visibles en pantalla.

De forma predeterminada, está habilitada la virtualización de interfaz de usuario para el <xref:System.Windows.Controls.ListView> y <xref:System.Windows.Controls.ListBox> controla cuando sus elementos de lista están enlazados a datos. <xref:System.Windows.Controls.TreeView> la virtualización puede ser habilitada configurando el <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> propiedad adjunta `true`. Si desea habilitar la virtualización de interfaz de usuario para controles personalizados que derivan de <xref:System.Windows.Controls.ItemsControl> o controles de elementos existentes que usan el <xref:System.Windows.Controls.StackPanel> clase, como <xref:System.Windows.Controls.ComboBox>, puede establecer el <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> a <xref:System.Windows.Controls.VirtualizingStackPanel> y establecer <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> a `true`. Desgraciadamente, puede deshabilitar la virtualización de la interfaz de usuario para estos controles sin darse cuenta. En la siguiente lista, se muestran las condiciones que deshabilitan la virtualización de la interfaz de usuario.

- Contenedores de elementos se agregan directamente a la <xref:System.Windows.Controls.ItemsControl>. Por ejemplo, si una aplicación agrega explícitamente <xref:System.Windows.Controls.ListBoxItem> objetos a un <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListBox> no virtualiza el <xref:System.Windows.Controls.ListBoxItem> objetos.

- Elementos contenedores en el <xref:System.Windows.Controls.ItemsControl> son de tipos diferentes. Por ejemplo, un <xref:System.Windows.Controls.Menu> que usa <xref:System.Windows.Controls.Separator> objetos no pueden implementar el reciclaje de elementos porque el <xref:System.Windows.Controls.Menu> contiene objetos de tipo <xref:System.Windows.Controls.Separator> y <xref:System.Windows.Controls.MenuItem>.

- Establecer <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> a `false`.

- Establecer <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> a `false`.

Una consideración importante que se debe tener en cuenta al virtualizar contenedores de elementos es si tiene información adicional de estado asociada a un contenedor de elemento que pertenece al elemento. Si es el caso, debe guardar el estado adicional. Por ejemplo, podría tener un elemento de un <xref:System.Windows.Controls.Expander> control y el <xref:System.Windows.Controls.Expander.IsExpanded%2A> estado está enlazado al contenedor del elemento y no al propio elemento. Cuando se vuelve a usar el contenedor para un elemento nuevo, el valor actual de <xref:System.Windows.Controls.Expander.IsExpanded%2A> se usa para el nuevo elemento. Además, el elemento antiguo perderá el valor correcto <xref:System.Windows.Controls.Expander.IsExpanded%2A> valor.

Actualmente, ningún control WPF ofrece compatibilidad integrada para la virtualización de datos.

## <a name="container-recycling"></a>Reciclaje de contenedores

Una optimización a la virtualización de la interfaz de usuario que agregó en .NET Framework 3.5 SP1 para los controles que heredan de <xref:System.Windows.Controls.ItemsControl> es *reciclaje de contenedores,* también que puede mejorar el rendimiento del desplazamiento. Cuando un <xref:System.Windows.Controls.ItemsControl> que utiliza virtualización de interfaz de usuario se rellena, crea un contenedor de elementos para cada elemento que se desplaza en la vista y destruye el contenedor de elementos para cada elemento que se desplaza fuera de la vista. *Reciclaje de contenedores* permite reutilizar los contenedores de elementos existentes para elementos de datos diferentes, por lo que los contenedores de elementos no constantemente se crean y destruyen como el usuario se desplaza al control el <xref:System.Windows.Controls.ItemsControl>. Puede elegir habilitar el elemento reciclaje estableciendo el <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling>.

Cualquier <xref:System.Windows.Controls.ItemsControl> que admite la virtualización puede usar el reciclaje de contenedores. Para obtener un ejemplo de cómo habilitar el reciclaje de contenedores en un <xref:System.Windows.Controls.ListBox>, consulte [mejorar el rendimiento del desplazamiento de un control ListBox](../controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).

## <a name="supporting-bidirectional-virtualization"></a>Compatibilidad con la virtualización bidireccional

<xref:System.Windows.Controls.VirtualizingStackPanel> ofrece compatibilidad integrada para la virtualización de interfaz de usuario en una dirección, ya sea horizontal o verticalmente. Si desea usar la virtualización bidireccional para sus controles, debe implementar un panel personalizado que extiende el <xref:System.Windows.Controls.VirtualizingStackPanel> clase. El <xref:System.Windows.Controls.VirtualizingStackPanel> clase expone los métodos virtuales como <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A>, y <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>. Estos métodos virtuales permiten detectar un cambio en la parte visible de una lista y controlarlo en consecuencia.

## <a name="optimizing-templates"></a>Optimizar plantillas

El árbol visual contiene todos los elementos visuales de una aplicación. Además de los objetos que se crean directamente, también contiene objetos debidos a la expansión de plantilla. Por ejemplo, cuando se crea un <xref:System.Windows.Controls.Button>, también obtendrá <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> y <xref:System.Windows.Controls.ContentPresenter> objetos en el árbol visual. Si no ha optimizado las plantillas de control, puede crear una gran cantidad de objetos innecesarios adicionales en el árbol visual. Para obtener más información sobre el árbol visual, consulte [Información general sobre la representación de gráficos en WPF](../graphics-multimedia/wpf-graphics-rendering-overview.md).

## <a name="deferred-scrolling"></a>Desplazamiento diferido

De forma predeterminada, cuando el usuario arrastra el control de posición en una barra de desplazamiento, la vista de contenido se actualiza continuamente. Si el desplazamiento es lento en el control, considere la posibilidad de usar el desplazamiento diferido. En el desplazamiento diferido, el contenido se actualiza solo cuando el usuario suelta el control de posición.

Para implementar el desplazamiento diferido, establezca el <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> propiedad `true`. <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> es una propiedad adjunta y se puede establecer en <xref:System.Windows.Controls.ScrollViewer> y cualquier control que tenga un <xref:System.Windows.Controls.ScrollViewer> en su plantilla de control.

## <a name="controls-that-implement-performance-features"></a>Controles que implementan características de rendimiento

En la tabla siguiente, se enumeran los controles comunes para mostrar datos y su compatibilidad con las características de rendimiento. Consulte las secciones anteriores para obtener información sobre cómo habilitar estas características.

|Control|Virtualización|Reciclaje de contenedores|Desplazamiento diferido|
|-------------|--------------------|-------------------------|------------------------|
|<xref:System.Windows.Controls.ComboBox>|Se puede habilitar.|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.ContextMenu>|Se puede habilitar.|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.DocumentViewer>|No disponible|No disponible|Se puede habilitar.|
|<xref:System.Windows.Controls.ListBox>|Default|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.ListView>|Default|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.TreeView>|Se puede habilitar.|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.ToolBar>|No disponible|No disponible|Se puede habilitar.|

> [!NOTE]
> Para obtener un ejemplo de cómo habilitar la virtualización y reciclaje de contenedores en un <xref:System.Windows.Controls.TreeView>, consulte [mejorar el rendimiento de un control TreeView](../controls/how-to-improve-the-performance-of-a-treeview.md).

## <a name="see-also"></a>Vea también

- [Diseño](layout.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Controles](../controls/index.md)
- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
- [Tutorial: Almacenamiento en caché datos de la aplicación en una aplicación WPF](walkthrough-caching-application-data-in-a-wpf-application.md)