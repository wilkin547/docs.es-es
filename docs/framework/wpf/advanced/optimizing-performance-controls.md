---
title: 'Optimizar el rendimiento: Controles'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1b414aee19082196ab242706c7730c031cf3a76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="optimizing-performance-controls"></a>Optimizar el rendimiento: Controles
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] incluye muchos de los componentes de interfaz de usuario (UI) comunes que se usan en la mayoría de las aplicaciones Windows. Este tema contiene técnicas para mejorar el rendimiento de la interfaz de usuario.  
  
 
  
<a name="Displaying"></a>   
## <a name="displaying-large-data-sets"></a>Mostrar conjuntos de datos grandes  
 Los controles de WPF como el <xref:System.Windows.Controls.ListView> y <xref:System.Windows.Controls.ComboBox> se utilizan para mostrar listas de elementos en una aplicación. Si la lista para mostrar es grande, el rendimiento de la aplicación puede verse afectado. Esto ocurre porque el sistema de diseño estándar crea un contenedor de diseño para cada elemento asociado al control de lista y calcula el tamaño del diseño y la posición. Normalmente, no es necesario mostrar todos los elementos al mismo tiempo; en su lugar, muestra un subconjunto y el usuario se desplaza por la lista. En este caso, tiene sentido usar la *virtualización* de la interfaz de usuario, que significa que la generación de contenedores de elementos y el cálculo de diseño asociado para un elemento se aplaza hasta que el elemento es visible.  
  
 La virtualización de la interfaz de usuario es un aspecto importante de los controles de lista. No se debe confundir la virtualización de la interfaz de usuario con la virtualización de datos. La virtualización de la interfaz de imagen solo almacena elementos visibles en la memoria, pero, en un escenario de enlace de datos, almacena toda la estructura de datos en la memoria. En cambio, la virtualización de datos solo almacena en la memoria los elementos de datos que están visibles en pantalla.  
  
 De forma predeterminada, está habilitada la virtualización de la interfaz de usuario para la <xref:System.Windows.Controls.ListView> y <xref:System.Windows.Controls.ListBox> controla cuando sus elementos de lista enlazados a datos. <xref:System.Windows.Controls.TreeView>virtualización se puede habilitar estableciendo la <!--zz <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> --> `IsVirtualizing` propiedad adjunta `true`. Si desea habilitar la virtualización de la interfaz de usuario para los controles personalizados que derivan de <xref:System.Windows.Controls.ItemsControl> o controles de elemento existente que usan la <xref:System.Windows.Controls.StackPanel> de la clase, como <xref:System.Windows.Controls.ComboBox>, puede establecer la <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> a <xref:System.Windows.Controls.VirtualizingStackPanel> y establecer <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> a `true`. Desgraciadamente, puede deshabilitar la virtualización de la interfaz de usuario para estos controles sin darse cuenta. En la siguiente lista, se muestran las condiciones que deshabilitan la virtualización de la interfaz de usuario.  
  
-   Contenedores de elementos se agregan directamente a la <xref:System.Windows.Controls.ItemsControl>. Por ejemplo, si una aplicación agrega explícitamente <xref:System.Windows.Controls.ListBoxItem> objetos a un <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListBox> no virtualizar el <xref:System.Windows.Controls.ListBoxItem> objetos.  
  
-   Elementos contenedores en el <xref:System.Windows.Controls.ItemsControl> son de tipos diferentes. Por ejemplo, un <xref:System.Windows.Controls.Menu> que utiliza <xref:System.Windows.Controls.Separator> objetos no pueden implementar el elemento reciclaje porque el <xref:System.Windows.Controls.Menu> contiene objetos de tipo <xref:System.Windows.Controls.Separator> y <xref:System.Windows.Controls.MenuItem>.  
  
-   Establecer <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> a `false`.  
  
-   Establecer <!--zz <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A>--> `IsVirtualizing` a `false`.    
  
 Una consideración importante que se debe tener en cuenta al virtualizar contenedores de elementos es si tiene información adicional de estado asociada a un contenedor de elemento que pertenece al elemento. Si es el caso, debe guardar el estado adicional. Por ejemplo, podría tener un elemento de un <xref:System.Windows.Controls.Expander> control y la <xref:System.Windows.Controls.Expander.IsExpanded%2A> estado enlazado al contenedor del elemento y no el propio elemento. Cuando el contenedor se reutiliza para un nuevo elemento, el valor actual de <xref:System.Windows.Controls.Expander.IsExpanded%2A> se usa para el nuevo elemento. Además, el elemento antiguo pierde el valor correcto <xref:System.Windows.Controls.Expander.IsExpanded%2A> valor.  
  
 Actualmente, ningún control WPF ofrece compatibilidad integrada para la virtualización de datos.  
  
<a name="Container"></a>   
## <a name="container-recycling"></a>Reciclaje de contenedores  
 Una optimización a la virtualización de la interfaz de usuario agregada en .NET Framework 3.5 SP1 para los controles que heredan de <xref:System.Windows.Controls.ItemsControl> es *el reciclaje de contenedores,* que también puede mejorar el rendimiento del desplazamiento.  Cuando un <xref:System.Windows.Controls.ItemsControl> que utiliza virtualización de interfaz de usuario se llena, crea un contenedor de elementos para cada elemento que se desplaza en la vista y se destruye el contenedor de elementos para cada elemento que se desplaza fuera de la vista. *Reciclaje de contenedores* habilita el control de reutilizar los contenedores de elementos existentes para los elementos de datos diferentes, por lo que los contenedores de elementos no constantemente se crean y destruyen como el usuario se desplaza el <xref:System.Windows.Controls.ItemsControl>. Puede optar por habilitar elemento reciclaje estableciendo la <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling>.  
  
 Cualquier <xref:System.Windows.Controls.ItemsControl> compatible con la virtualización puede utilizar el reciclaje de contenedores.  Para obtener un ejemplo de cómo habilitar el reciclaje de contenedores en un <xref:System.Windows.Controls.ListBox>, consulte [mejorar el rendimiento de desplazamiento de un control ListBox](../../../../docs/framework/wpf/controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).  
  
<a name="Supporting"></a>   
## <a name="supporting-bidirectional-virtualization"></a>Compatibilidad con la virtualización bidireccional  
 <xref:System.Windows.Controls.VirtualizingStackPanel>ofrece compatibilidad integrada para la virtualización de la interfaz de usuario en una dirección, horizontal o verticalmente. Si desea utilizar la virtualización bidireccional para sus controles, debe implementar un panel personalizado que extiende el <xref:System.Windows.Controls.VirtualizingStackPanel> clase. El <xref:System.Windows.Controls.VirtualizingStackPanel> clase expone métodos virtuales como <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A>, y <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>. Estos métodos virtuales permiten detectar un cambio en la parte visible de una lista y administrarlo en consecuencia.  
  
<a name="Optimizing"></a>   
## <a name="optimizing-templates"></a>Optimizar plantillas  
 El árbol visual contiene todos los elementos visuales de una aplicación.  Además de los objetos que se crean directamente, también contiene objetos debidos a la expansión de plantilla.  Por ejemplo, cuando se crea un <xref:System.Windows.Controls.Button>, también obtendrá <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> y <xref:System.Windows.Controls.ContentPresenter> objetos en el árbol visual.  Si no ha optimizado las plantillas de control, puede crear una gran cantidad de objetos innecesarios adicionales en el árbol visual.   Para obtener más información sobre el árbol visual, consulte [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
<a name="Deferred"></a>   
## <a name="deferred-scrolling"></a>Desplazamiento diferido  
 De forma predeterminada, cuando el usuario arrastra el control de posición en una barra de desplazamiento, la vista de contenido se actualiza continuamente.  Si el desplazamiento es lento en el control, considere la posibilidad de usar el desplazamiento diferido.  En el desplazamiento diferido, el contenido se actualiza solo cuando el usuario suelta el control de posición.  
  
 Para implementar el desplazamiento diferido, establezca el <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> propiedad `true`.  <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A>es una propiedad adjunta y se puede establecer en <xref:System.Windows.Controls.ScrollViewer> y cualquier control que tenga un <xref:System.Windows.Controls.ScrollViewer> en su plantilla de control.  
  
<a name="Controls"></a>   
## <a name="controls-that-implement-performance-features"></a>Controles que implementan características de rendimiento  
 En la tabla siguiente, se enumeran los controles comunes para mostrar datos y su compatibilidad con las características de rendimiento.  Consulte las secciones anteriores para obtener información sobre cómo habilitar estas características.  
  
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
>  Para obtener un ejemplo de cómo habilitar virtualización y reciclaje del contenedores en un <xref:System.Windows.Controls.TreeView>, consulte [mejorar el rendimiento de una vista de árbol](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md).  
  
## <a name="see-also"></a>Vea también  
 [Diseño](../../../../docs/framework/wpf/advanced/layout.md)  
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Controles](../../../../docs/framework/wpf/controls/index.md)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Tutorial: Almacenar en caché datos de la aplicación en una aplicación WPF](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
