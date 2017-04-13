---
title: "Optimizar el rendimiento: Controles | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "reciclaje de contenedores"
  - "controles [WPF], mejorar el rendimiento"
  - "virtualización de la interfaz de usuario"
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Optimizar el rendimiento: Controles
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] incluye muchos de los componentes comunes de interfaz de usuario que se utilizan en la mayoría de las aplicaciones Windows.  Este tema contiene técnicas para mejorar el rendimiento de la interfaz de usuario.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Displaying"></a>   
## Mostrar conjuntos de datos de gran tamaño  
 Los controles de WPF como <xref:System.Windows.Controls.ListView> y <xref:System.Windows.Controls.ComboBox> se utilizan para mostrar listas de elementos en una aplicación.  Si la lista que se va a mostrar es grande, puede afectar al rendimiento de la aplicación.  Esto es porque el sistema de diseño estándar crea un contenedor de diseño para cada elemento asociado al control de lista, y calcula su tamaño y posición de diseño.  Normalmente, no es necesario mostrar al mismo tiempo todos los elementos; en lugar de ello se muestra un subconjunto y el usuario se va desplazando por la lista.  En este caso, es razonable utilizar la *virtualización* de la interfaz de usuario, que consiste en diferir la generación de contenedor de elemento y los cálculos de diseño asociados hasta que el elemento esté visible.  
  
 La virtualización de la interfaz de usuario es un aspecto importante de los controles de lista.  Es importante no confundir la virtualización de la interfaz de usuario con la virtualización de datos.  La virtualización de la interfaz de usuario almacena en la memoria únicamente los elementos visibles; pero en un escenario de enlace de datos almacena en la memoria la estructura de datos completa.  En cambio, la virtualización de datos almacena en la memoria solamente los elementos de datos que están visibles en la pantalla.  
  
 De forma predeterminada, la virtualización de la interfaz de usuario está habilitada para los controles <xref:System.Windows.Controls.ListView> y <xref:System.Windows.Controls.ListBox> cuando sus elementos de lista están enlazados a datos.  La virtualización de <xref:System.Windows.Controls.TreeView> puede habilitarse estableciendo la propiedad adjunta <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> en `true`.  Si desea habilitar la virtualización de la interfaz de usuario para los controles personalizados derivados de <xref:System.Windows.Controls.ItemsControl> o de controles de elementos existentes que utilizan la clase <xref:System.Windows.Controls.StackPanel>, como <xref:System.Windows.Controls.ComboBox>, puede establecer <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> en <xref:System.Windows.Controls.VirtualizingStackPanel> y establecer <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> en `true`.  Desgraciadamente, puede suceder que deshabilite la virtualización de la interfaz de usuario para estos controles sin darse cuenta.  A continuación se facilita una lista de condiciones que deshabilitan la virtualización de la interfaz de usuario.  
  
-   Se agregan contenedores de elementos directamente a <xref:System.Windows.Controls.ItemsControl>.  Por ejemplo, si una aplicación agrega explícitamente objetos <xref:System.Windows.Controls.ListBoxItem> a <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListBox> no virtualiza los objetos <xref:System.Windows.Controls.ListBoxItem>.  
  
-   Los contenedores de elementos de <xref:System.Windows.Controls.ItemsControl> son de tipos diferentes.  Por ejemplo, un control <xref:System.Windows.Controls.Menu> que utiliza los objetos <xref:System.Windows.Controls.Separator> no puede implementar el reciclaje de elementos porque <xref:System.Windows.Controls.Menu> contiene objetos de tipo <xref:System.Windows.Controls.Separator> y de tipo <xref:System.Windows.Controls.MenuItem>.  
  
-   Se establece <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> en `false`.  
  
-   Se establece <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> en `false`.  
  
 Una consideración importante cuando se virtualiza los contenedores de elementos es si tiene información de estado adicional asociado con un contenedor de elemento que está asociada al.  En este caso, deberá guardar el estado adicional.  Por ejemplo, supongamos que hay un elemento incluido en un control <xref:System.Windows.Controls.Expander> y que el estado <xref:System.Windows.Controls.Expander.IsExpanded%2A> está enlazado al contenedor del elemento, no al propio elemento.  Cuando el contenedor se reutiliza para un nuevo elemento, el valor actual de <xref:System.Windows.Controls.Expander.IsExpanded%2A> se utiliza para el nuevo elemento.  Además, el elemento antiguo pierde el valor de <xref:System.Windows.Controls.Expander.IsExpanded%2A> correcto.  
  
 Actualmente, ningún control de WPF proporciona compatibilidad integrada con la virtualización de datos.  
  
<a name="Container"></a>   
## Reciclaje de contenedores  
 Una optimización a la virtualización de la interfaz de usuario que se ha agregado a .NET Framework 3.5 SP1 para los controles que heredan de <xref:System.Windows.Controls.ItemsControl> es el *reciclaje de contenedores*, que también puede mejorar el rendimiento del desplazamiento.  Cuando se rellena un objeto <xref:System.Windows.Controls.ItemsControl> que utiliza la virtualización de la interfaz de usuario, crea un contenedor de elemento para cada elemento que queda visible al desplazarse, y destruye el contenedor de elemento correspondiente a cada elemento que deja de estar visible al desplazarse.  El *reciclaje de contenedores* permite que el control reutilice los contenedores de elemento existentes para distintos elementos de datos, de tal forma que evita tener que crear y destruir continuamente los contenedores de elementos a medida que usuario se desplaza por <xref:System.Windows.Controls.ItemsControl>.  Puede habilitar el reciclaje estableciendo la propiedad adjunta <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> a <xref:System.Windows.Controls.VirtualizationMode>.  
  
 Cualquier objeto <xref:System.Windows.Controls.ItemsControl> que admita la virtualización puede utilizar el reciclaje de contenedores.  Para obtener un ejemplo de cómo habilitar el reciclaje de contenedores en un control <xref:System.Windows.Controls.ListBox>, vea [Mejorar el rendimiento del desplazamiento de un control ListBox](../../../../docs/framework/wpf/controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).  
  
<a name="Supporting"></a>   
## Compatibilidad con la virtualización bidireccional  
 <xref:System.Windows.Controls.VirtualizingStackPanel> proporciona compatibilidad integrada con la virtualización de la interfaz de usuario en una dirección, horizontal o vertical.  Si desea utilizar la virtualización bidireccional para sus controles, debe implementar un panel personalizado que extienda la clase <xref:System.Windows.Controls.VirtualizingStackPanel>.  La clase <xref:System.Windows.Controls.VirtualizingStackPanel> expone métodos virtuales como <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A> y <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>. Estos métodos virtuales permiten detectar un cambio en la parte visible de una lista y administrarlo en consecuencia.  
  
<a name="Optimizing"></a>   
## Optimizar plantillas  
 El árbol visual contiene todos los elementos visuales de una aplicación.  Además de los objetos que se han creado directamente, también contiene los que se deben a la expansión de la plantilla.  Por ejemplo, al crear un objeto <xref:System.Windows.Controls.Button>, también se obtienen los objetos <xref:System.Windows.Controls.ContentPresenter> y <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> en el árbol visual.  Si no ha optimizado las plantillas de los controles, puede suceder que cree gran cantidad de objetos innecesarios adicionales en el árbol visual.  Para obtener más información sobre el árbol visual, vea [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
<a name="Deferred"></a>   
## Desplazamiento diferido  
 De forma predeterminada, cuando el usuario arrastra el cuadro de una barra de desplazamiento, la vista de contenido se actualiza continuamente.  Si el desplazamiento dentro del control es lento, puede ser interesante utilizar el desplazamiento diferido.  En el desplazamiento diferido, el contenido se actualiza únicamente cuando el usuario suelta el cuadro de desplazamiento.  
  
 Para implementar el desplazamiento diferido, establezca la propiedad <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> en `true`.  <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> es una propiedad adjunta y se puede establecer para <xref:System.Windows.Controls.ScrollViewer> y para cualquier control que contenga <xref:System.Windows.Controls.ScrollViewer> en su plantilla de control.  
  
<a name="Controls"></a>   
## Controles que implementan características de rendimiento  
 En la tabla siguiente se muestra una lista de controles que se suelen usar para mostrar datos y su compatibilidad con las características de rendimiento.  Vea las secciones anteriores para obtener información sobre cómo habilitar estas características.  
  
|Control|Virtualización|Reciclaje de contenedores|Desplazamiento diferido|  
|-------------|--------------------|-------------------------------|-----------------------------|  
|<xref:System.Windows.Controls.ComboBox>|Se puede habilitar|Se puede habilitar|Se puede habilitar|  
|<xref:System.Windows.Controls.ContextMenu>|Se puede habilitar|Se puede habilitar|Se puede habilitar|  
|<xref:System.Windows.Controls.DocumentViewer>|No está disponible|No está disponible|Se puede habilitar|  
|<xref:System.Windows.Controls.ListBox>|Default|Se puede habilitar|Se puede habilitar|  
|<xref:System.Windows.Controls.ListView>|Default|Se puede habilitar|Se puede habilitar|  
|<xref:System.Windows.Controls.TreeView>|Se puede habilitar|Se puede habilitar|Se puede habilitar|  
|<xref:System.Windows.Controls.ToolBar>|No está disponible|No está disponible|Se puede habilitar|  
  
> [!NOTE]
>  Para obtener un ejemplo de cómo habilitar virtualización y reciclaje del contenedores en un objeto <xref:System.Windows.Controls.TreeView>, vea [Mejorar el rendimiento de un control TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md).  
  
## Vea también  
 [Diseño](../../../../docs/framework/wpf/advanced/layout.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Controles](../../../../docs/framework/wpf/controls/index.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)