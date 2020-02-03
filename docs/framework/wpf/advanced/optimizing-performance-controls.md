---
title: Optimizar el rendimiento del control
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
ms.openlocfilehash: d02fde7076cd6a24fdfb171ed54161b20f3d465e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746728"
---
# <a name="optimizing-performance-controls"></a>Optimizar el rendimiento: controles

Windows Presentation Foundation (WPF) incluye muchos de los componentes comunes de la interfaz de usuario (UI) que se usan en la mayoría de las aplicaciones Windows. Este tema contiene técnicas para mejorar el rendimiento de la interfaz de usuario.

## <a name="displaying-large-data-sets"></a>Mostrar conjuntos de datos grandes

Los controles de WPF, como el <xref:System.Windows.Controls.ListView> y el <xref:System.Windows.Controls.ComboBox>, se usan para mostrar listas de elementos en una aplicación. Si la lista para mostrar es grande, el rendimiento de la aplicación puede verse afectado. Esto ocurre porque el sistema de diseño estándar crea un contenedor de diseño para cada elemento asociado al control de lista y calcula el tamaño del diseño y la posición. Normalmente, no es necesario mostrar todos los elementos al mismo tiempo; en su lugar, muestra un subconjunto y el usuario se desplaza por la lista. En este caso, tiene sentido usar la *virtualización* de la interfaz de usuario, que significa que la generación de contenedores de elementos y el cálculo de diseño asociado para un elemento se aplaza hasta que el elemento es visible.

La virtualización de la interfaz de usuario es un aspecto importante de los controles de lista. No se debe confundir la virtualización de la interfaz de usuario con la virtualización de datos. La virtualización de la interfaz de imagen solo almacena elementos visibles en la memoria, pero, en un escenario de enlace de datos, almacena toda la estructura de datos en la memoria. En cambio, la virtualización de datos solo almacena en la memoria los elementos de datos que están visibles en pantalla.

De forma predeterminada, la virtualización de la interfaz de usuario está habilitada para los controles <xref:System.Windows.Controls.ListView> y <xref:System.Windows.Controls.ListBox> cuando sus elementos de lista están enlazados a datos. <xref:System.Windows.Controls.TreeView> virtualización se puede habilitar estableciendo la propiedad <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> adjunta en `true`. Si desea habilitar la virtualización de la interfaz de usuario para controles personalizados que se derivan de <xref:System.Windows.Controls.ItemsControl> o de controles de elementos existentes que usan la clase <xref:System.Windows.Controls.StackPanel>, como <xref:System.Windows.Controls.ComboBox>, puede establecer el <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> en <xref:System.Windows.Controls.VirtualizingStackPanel> y establecer <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> en `true`. Desgraciadamente, puede deshabilitar la virtualización de la interfaz de usuario para estos controles sin darse cuenta. En la siguiente lista, se muestran las condiciones que deshabilitan la virtualización de la interfaz de usuario.

- Los contenedores de elementos se agregan directamente a la <xref:System.Windows.Controls.ItemsControl>. Por ejemplo, si una aplicación agrega explícitamente <xref:System.Windows.Controls.ListBoxItem> objetos a un <xref:System.Windows.Controls.ListBox>, el <xref:System.Windows.Controls.ListBox> no Virtualiza los objetos <xref:System.Windows.Controls.ListBoxItem>.

- Los contenedores de elementos de la <xref:System.Windows.Controls.ItemsControl> son de tipos diferentes. Por ejemplo, un <xref:System.Windows.Controls.Menu> que usa objetos <xref:System.Windows.Controls.Separator> no puede implementar el reciclaje de elementos porque el <xref:System.Windows.Controls.Menu> contiene objetos de tipo <xref:System.Windows.Controls.Separator> y <xref:System.Windows.Controls.MenuItem>.

- Estableciendo <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> en `false`.

- Estableciendo <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> en `false`.

Una consideración importante que se debe tener en cuenta al virtualizar contenedores de elementos es si tiene información adicional de estado asociada a un contenedor de elemento que pertenece al elemento. Si es el caso, debe guardar el estado adicional. Por ejemplo, podría tener un elemento incluido en un control de <xref:System.Windows.Controls.Expander> y el estado de la <xref:System.Windows.Controls.Expander.IsExpanded%2A> se enlaza al contenedor del elemento, y no al elemento en sí. Cuando el contenedor se reutiliza para un nuevo elemento, se utiliza el valor actual de <xref:System.Windows.Controls.Expander.IsExpanded%2A> para el nuevo elemento. Además, el elemento antiguo pierde el valor de <xref:System.Windows.Controls.Expander.IsExpanded%2A> correcto.

Actualmente, ningún control WPF ofrece compatibilidad integrada para la virtualización de datos.

## <a name="container-recycling"></a>Reciclaje de contenedores

Una optimización de la virtualización de la interfaz de usuario agregada en .NET Framework 3,5 SP1 para los controles que heredan de <xref:System.Windows.Controls.ItemsControl> es el *reciclaje de contenedores,* que también puede mejorar el rendimiento del desplazamiento. Cuando se rellena una <xref:System.Windows.Controls.ItemsControl> que utiliza la virtualización de la interfaz de usuario, se crea un contenedor de elementos para cada elemento que se desplaza en la vista y se destruye el contenedor de elementos para cada elemento que se desplaza fuera de la vista. El *reciclaje de contenedores* permite que el control reutilice los contenedores de elementos existentes para los distintos elementos de datos, de modo que los contenedores de elementos no se creen y destruyan constantemente cuando el usuario desplace el <xref:System.Windows.Controls.ItemsControl>. Puede optar por habilitar el reciclaje de elementos estableciendo el <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> propiedad adjunta en <xref:System.Windows.Controls.VirtualizationMode.Recycling>.

Cualquier <xref:System.Windows.Controls.ItemsControl> que admita la virtualización puede utilizar el reciclaje de contenedores. Para obtener un ejemplo de cómo habilitar el reciclaje de contenedores en un <xref:System.Windows.Controls.ListBox>, vea [mejorar el rendimiento del desplazamiento de un control ListBox](../controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).

## <a name="supporting-bidirectional-virtualization"></a>Compatibilidad con la virtualización bidireccional

<xref:System.Windows.Controls.VirtualizingStackPanel> ofrece compatibilidad integrada para la virtualización de la interfaz de usuario en una dirección, ya sea horizontal o verticalmente. Si desea utilizar la virtualización bidireccional para los controles, debe implementar un panel personalizado que extienda la clase <xref:System.Windows.Controls.VirtualizingStackPanel>. La clase <xref:System.Windows.Controls.VirtualizingStackPanel> expone métodos virtuales como <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A>y <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>. Estos métodos virtuales permiten detectar un cambio en la parte visible de una lista y controlarlo en consecuencia.

## <a name="optimizing-templates"></a>Optimizar plantillas

El árbol visual contiene todos los elementos visuales de una aplicación. Además de los objetos que se crean directamente, también contiene objetos debidos a la expansión de plantilla. Por ejemplo, al crear un <xref:System.Windows.Controls.Button>, también obtiene <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> y <xref:System.Windows.Controls.ContentPresenter> objetos en el árbol visual. Si no ha optimizado las plantillas de control, puede crear una gran cantidad de objetos innecesarios adicionales en el árbol visual. Para obtener más información sobre el árbol visual, consulte [Información general sobre la representación de gráficos en WPF](../graphics-multimedia/wpf-graphics-rendering-overview.md).

## <a name="deferred-scrolling"></a>Desplazamiento diferido

De forma predeterminada, cuando el usuario arrastra el control de posición en una barra de desplazamiento, la vista de contenido se actualiza continuamente. Si el desplazamiento es lento en el control, considere la posibilidad de usar el desplazamiento diferido. En el desplazamiento diferido, el contenido se actualiza solo cuando el usuario suelta el control de posición.

Para implementar el desplazamiento diferido, establezca la propiedad <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> en `true`. <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> es una propiedad adjunta y se puede establecer en <xref:System.Windows.Controls.ScrollViewer> y en cualquier control que tenga un <xref:System.Windows.Controls.ScrollViewer> en su plantilla de control.

## <a name="controls-that-implement-performance-features"></a>Controles que implementan características de rendimiento

En la tabla siguiente, se enumeran los controles comunes para mostrar datos y su compatibilidad con las características de rendimiento. Consulte las secciones anteriores para obtener información sobre cómo habilitar estas características.

|Control|Virtualización|Reciclaje de contenedores|Desplazamiento diferido|
|-------------|--------------------|-------------------------|------------------------|
|<xref:System.Windows.Controls.ComboBox>|Se puede habilitar.|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.ContextMenu>|Se puede habilitar.|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.DocumentViewer>|No disponible|No disponible|Se puede habilitar.|
|<xref:System.Windows.Controls.ListBox>|Valor predeterminado|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.ListView>|Valor predeterminado|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.TreeView>|Se puede habilitar.|Se puede habilitar.|Se puede habilitar.|
|<xref:System.Windows.Controls.ToolBar>|No disponible|No disponible|Se puede habilitar.|

> [!NOTE]
> Para obtener un ejemplo de cómo habilitar la virtualización y el reciclaje de contenedores en un <xref:System.Windows.Controls.TreeView>, vea [mejorar el rendimiento de una vista de árbol](../controls/how-to-improve-the-performance-of-a-treeview.md).

## <a name="see-also"></a>Consulte también

- [Diseño](layout.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Controles](../controls/index.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF](walkthrough-caching-application-data-in-a-wpf-application.md)
