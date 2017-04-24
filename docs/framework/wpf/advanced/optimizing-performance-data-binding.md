---
title: "Optimizar el rendimiento: Enlace de datos | Microsoft Docs"
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
  - "enlazar datos, rendimiento"
  - "enlace de datos, rendimiento"
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Optimizar el rendimiento: Enlace de datos
El enlace de datos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un método simple y coherente para que las aplicaciones presenten e interactúen con datos.  Los elementos se pueden enlazar a los datos de diversos orígenes de datos en forma de objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 En este tema se proporcionan recomendaciones sobre el rendimiento del enlace de datos.  
  
   
  
<a name="HowDataBindingReferencesAreResolved"></a>   
## Cómo se resuelven las referencias de enlace de datos  
 Antes de explicar los problemas de rendimiento de enlace de datos, vale la pena explorar cómo el motor de enlace de datos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] resuelve las referencias de objeto para el enlace.  
  
 El origen de un enlace de datos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede ser cualquier objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Es posible enlazar a propiedades, subpropiedades o indizadores de un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Las referencias de enlace se resuelven utilizando reflexión [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] o una interfaz <xref:System.ComponentModel.ICustomTypeDescriptor>.  Estos son tres métodos para resolver referencias de objeto para el enlace.  
  
 El primer método implica el uso de la reflexión.  En este caso, el objeto <xref:System.Reflection.PropertyInfo> se utiliza para detectar los atributos de la propiedad y proporcionar acceso a los metadatos de propiedad.  Cuando se utiliza la interfaz <xref:System.ComponentModel.ICustomTypeDescriptor>, el motor de enlace de datos utiliza esta interfaz para tener acceso a los valores de propiedad.  La interfaz <xref:System.ComponentModel.ICustomTypeDescriptor> es especialmente útil en aquellos casos en los que el objeto no tiene un conjunto estático de propiedades.  
  
 Las notificaciones de cambios de propiedad se pueden proporcionar implementando la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> o utilizando las notificaciones de cambios asociadas al objeto <xref:System.ComponentModel.TypeDescriptor>.  Sin embargo, la estrategia preferida para implementar notificaciones de cambios de propiedades es utilizar <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Si el objeto de origen es un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y la propiedad de origen es una propiedad [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], el motor de enlace de datos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] tiene que utilizar primero la reflexión en el objeto de origen para obtener el objeto <xref:System.ComponentModel.TypeDescriptor>y, a continuación, consultar un objeto <xref:System.ComponentModel.PropertyDescriptor>.  Esta secuencia de operaciones de reflexión puede necesitar mucho tiempo, desde la perspectiva del rendimiento.  
  
 El segundo método para resolver referencias a objetos implica un objeto de origen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] que implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> y una propiedad de origen que es una propiedad [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  En este caso, el motor de enlace de datos utiliza directamente la reflexión en el tipo de origen y obtiene la propiedad necesaria.  Este método continúa sin ser el óptimo, pero sus requisitos de espacio de trabajo son menores que los del primer método.  
  
 El tercer método para resolver referencias de objeto implica un objeto de origen que es un objeto <xref:System.Windows.DependencyObject> y una propiedad que es un objeto <xref:System.Windows.DependencyProperty>.  En este caso, el motor de enlace de datos no necesita utilizar la reflexión.  En su lugar, el motor de propiedad y el motor de enlace de datos resuelven juntos la referencia de propiedad de manera independiente.  Éste es el método óptimo para resolver referencias de objeto utilizadas para el enlace de datos.  
  
 La tabla siguiente compara la velocidad de enlace de datos de la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> de mil elementos <xref:System.Windows.Controls.TextBlock> utilizando estos tres métodos.  
  
|**Enlazar la propiedad Text de un TextBlock**|**Tiempo de enlace \(ms\)**|**Tiempo de representación, incluido el enlace \(ms\)**|  
|---------------------------------------------------|---------------------------------|-------------------------------------------------------------|  
|A una propiedad de un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]|115|314|  
|A una propiedad de un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] que implementa <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|A un objeto <xref:System.Windows.DependencyProperty> de un objeto <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## Enlazar a objetos CLR grandes  
 Hay un impacto significativo sobre el rendimiento cuando se realiza el enlace de datos a un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] único con miles de propiedades.  Puede minimizar este impacto dividiendo el objeto único en varios objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con menos propiedades.  La tabla muestra los tiempos de enlace y representación para el enlace de datos a un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] grande único frente a varios objetos menores.  
  
|**Enlace de datos de 1000 objetos TextBlock**|**Tiempo de enlace \(ms\)**|**Tiempo de representación, incluido el enlace \(ms\)**|  
|---------------------------------------------------|---------------------------------|-------------------------------------------------------------|  
|A un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con 1000 propiedades|950|1200|  
|A 1000 objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con una propiedad|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## Enlazar a una propiedad ItemsSource  
 Considere un escenario en el que tiene un objeto <xref:System.Collections.Generic.List%601> de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] que contiene una lista de empleados que desea mostrar en un control <xref:System.Windows.Controls.ListBox>.  Para crear una correspondencia entre estos dos objetos, enlazaría la lista de empleados a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del control <xref:System.Windows.Controls.ListBox>.  No obstante, suponga que tiene un nuevo empleado que se incorpora al grupo.  Podría pensar que, para insertar esta nueva persona en los valores <xref:System.Windows.Controls.ListBox> enlazados, agregaría simplemente esta persona a la lista de empleados y esperaría que el cambio fuera reconocido automáticamente por el motor de enlace de datos.  Esa suposición se demostraría falsa; en realidad, el cambio no se reflejaría automáticamente en <xref:System.Windows.Controls.ListBox>.  Esto se debe a que el objeto <xref:System.Collections.Generic.List%601> de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] no genera automáticamente un evento de cambio de colección.  Para que el control <xref:System.Windows.Controls.ListBox> captara los cambios, tendría que volver a crear la lista de empleados y asociarla de nuevo a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del control <xref:System.Windows.Controls.ListBox>.  Aunque esta solución funciona, introduce un impacto enorme sobre el rendimiento.  Cada vez que se reasigna la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del control <xref:System.Windows.Controls.ListBox> a un nuevo objeto, el control <xref:System.Windows.Controls.ListBox> desecha primero sus elementos anteriores y regenera la lista completa.  El impacto sobre el rendimiento se magnifica si el control <xref:System.Windows.Controls.ListBox> se asigna a un objeto <xref:System.Windows.DataTemplate> complejo.  
  
 Una solución muy eficaz a este problema es convertir la lista de empleados en una colección <xref:System.Collections.ObjectModel.ObservableCollection%601>.  Un objeto <xref:System.Collections.ObjectModel.ObservableCollection%601> provoca una notificación de cambios que el motor de enlace de datos puede recibir.  El evento agrega o quita un elemento de un control <xref:System.Windows.Controls.ItemsControl> sin necesidad de regenerar la lista completa.  
  
 La tabla siguiente muestra el tiempo necesario para actualizar el control <xref:System.Windows.Controls.ListBox> \(con virtualización de la interfaz de usuario desactivada\) cuando se agrega un elemento.  El número de la primera fila representa el tiempo transcurrido cuando el objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]<xref:System.Collections.Generic.List%601> se enlaza a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de un elemento <xref:System.Windows.Controls.ListBox>.  El número en la segunda fila representa el tiempo transcurrido cuando una colección <xref:System.Collections.ObjectModel.ObservableCollection%601> se enlaza a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de un elemento <xref:System.Windows.Controls.ListBox>.  Observe los significativos ahorros de tiempo mediante la estrategia de enlace de datos de <xref:System.Collections.ObjectModel.ObservableCollection%601>.  
  
|**Enlace de datos de ItemsSource**|**Tiempo de actualización para 1 elemento \(ms\)**|  
|----------------------------------------|--------------------------------------------------------|  
|A un objeto <xref:System.Collections.Generic.List%601> de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]|1656|  
|A una colección <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## Enlazar IList a ItemsControl no IEnumerable  
 Si puede elegir entre enlazar un objeto <xref:System.Collections.Generic.IList%601> o una interfaz <xref:System.Collections.IEnumerable> a un objeto <xref:System.Windows.Controls.ItemsControl>, elija el objeto <xref:System.Collections.Generic.IList%601>.  Enlazar la interfaz <xref:System.Collections.IEnumerable> a un control <xref:System.Windows.Controls.ItemsControl> obliga a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a crear un objeto <xref:System.Collections.Generic.IList%601> contenedor, lo que significa que el rendimiento se ve afectado por la sobrecarga innecesaria de un segundo objeto.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## No convierta objetos CLR en XML solamente para el enlace de datos.  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite enlazar datos a contenido [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]; no obstante, en enlace de datos a contenido [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] es más lento que el enlace de datos a objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  No convierta datos de objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] en XML si su único propósito es el enlace de datos.  
  
## Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Recursos de aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)