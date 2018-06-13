---
title: 'Optimizar el rendimiento: Enlace de datos'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: da870e9459ee2cbe0384c146546c378fb7247f03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548785"
---
# <a name="optimizing-performance-data-binding"></a>Optimizar el rendimiento: Enlace de datos
El enlace de datos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una manera sencilla y coherente para que las aplicaciones presenten datos e interactúen con ellos. Los elementos se pueden enlazar a datos desde una variedad de orígenes de datos en forma de objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 En este tema se proporcionan recomendaciones de rendimiento del enlace de datos.  
  

  
<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>Cómo se resuelven las referencias de enlace de datos  
 Antes de tratar los problemas de rendimiento del enlace de datos, vale la pena explorar cómo el motor de enlace de datos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] resuelve las referencias de objeto para el enlace.  
  
 El origen de un enlace de datos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede ser cualquier objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Puede enlazar a propiedades, subpropiedades o indizadores de un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Las referencias de enlace se resuelven utilizando cualquier reflexión de Microsoft .NET Framework o un <xref:System.ComponentModel.ICustomTypeDescriptor>. Estos son tres métodos para resolver las referencias de objeto para el enlace.  
  
 El primer método implica el uso de reflexión. En este caso, el <xref:System.Reflection.PropertyInfo> objeto se usa para detectar los atributos de la propiedad y proporciona acceso a sus metadatos. Cuando se usa el <xref:System.ComponentModel.ICustomTypeDescriptor> interfaz, el motor de enlace de datos usa esta interfaz para tener acceso a los valores de propiedad. La <xref:System.ComponentModel.ICustomTypeDescriptor> interfaz es especialmente útil en casos donde el objeto no tiene un conjunto estático de propiedades.  
  
 Las notificaciones de cambio de propiedad pueden proporcionarse mediante la implementación de la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz o usando las notificaciones de cambio asociadas a la <xref:System.ComponentModel.TypeDescriptor>. Sin embargo, es usar la estrategia preferida para implementar notificaciones de cambio de propiedad <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Si el objeto de origen es un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] objeto y la propiedad de origen es un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] propiedad, el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] motor de enlace de datos debe usar primero la reflexión en el objeto de origen para obtener la <xref:System.ComponentModel.TypeDescriptor>y, a continuación, consultar una <xref:System.ComponentModel.PropertyDescriptor>. Esta secuencia de operaciones de reflexión es potencialmente muy lenta, desde una perspectiva de rendimiento.  
  
 El segundo método para resolver las referencias de objeto implica un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] objeto de origen que implementa el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz y una propiedad de origen que es una [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] propiedad. En este caso, el motor de enlace de datos usa la reflexión directamente en el tipo de origen y obtiene la propiedad necesaria. No es el método óptimo, pero tendrá un costo menor en los requisitos del conjunto de trabajo comparado con el primer método.  
  
 El tercer método para resolver las referencias de objeto implica un objeto de origen es un <xref:System.Windows.DependencyObject> y una propiedad de origen es un <xref:System.Windows.DependencyProperty>. En este caso, el motor de enlace de datos no necesita usar la reflexión. En su lugar, el motor de propiedad y el motor de enlace de datos resuelven juntos la referencia de propiedad por separado. Este es el método óptimo para resolver las referencias de objeto que se usa para el enlace de datos.  
  
 En la tabla siguiente compara la velocidad de enlace de datos el <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad de un factor de mil <xref:System.Windows.Controls.TextBlock> elementos con estos tres métodos.  
  
|**Enlazar la propiedad de texto de TextBlock**|**Tiempo de enlace (ms)**|**Tiempo de representación, incluido el enlace (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|Para una propiedad de un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]|115|314|  
|Para una propiedad de un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] objeto que implementa <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|Para una <xref:System.Windows.DependencyProperty> de un <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>Enlazar a objetos CLR grandes  
 Hay un impacto significativo en el rendimiento al enlazar datos a un único objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con miles de propiedades. Puede minimizar este impacto si divide el objeto único en varios objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con menos propiedades. En la tabla se muestran los tiempos de enlace y representación para el enlace de datos de un único objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] grande frente a varios objetos más pequeños.  
  
|**Enlace de datos de 1000 objetos TextBlock**|**Tiempo de enlace (ms)**|**Tiempo de representación, incluido el enlace (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|Para una objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con 1000 propiedades|950|1200|  
|Para 1000 objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con una propiedad|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>Enlazar a ItemsSource  
 Considere un escenario en el que tenga un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> objeto que contiene una lista de empleados que desea mostrar en un <xref:System.Windows.Controls.ListBox>. Para crear una correspondencia entre estos dos objetos, enlazaría la lista de empleados a la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.ListBox>. Sin embargo, suponga que tiene un nuevo empleado que se incorpora al grupo. Puede pensar que para insertar esta nueva persona en su límite <xref:System.Windows.Controls.ListBox> valores, simplemente podría agregar esta persona a la lista de empleados y espera que este cambio para ser reconocidos por el motor de enlace de datos automáticamente. Esa suposición resultarían false; en realidad, el cambio no se reflejará en la <xref:System.Windows.Controls.ListBox> automáticamente. Esto es porque el [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> objeto no genera un evento de la colección cambia automáticamente. Para obtener la <xref:System.Windows.Controls.ListBox> para recoger los cambios, tendría que volver a la lista de empleados y volver a adjuntarla a la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.ListBox>. Aunque esta solución funciona, supone un impacto enorme en el rendimiento. Cada vez que se reasigna la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de <xref:System.Windows.Controls.ListBox> a un nuevo objeto, el <xref:System.Windows.Controls.ListBox> primero inicia inmediatamente sus elementos anteriores y vuelve a generar la lista completa. Se amplía el impacto en el rendimiento si su <xref:System.Windows.Controls.ListBox> se asigna a un complejo <xref:System.Windows.DataTemplate>.  
  
 Una solución muy eficaz a este problema consiste en realizar la lista de empleados un <xref:System.Collections.ObjectModel.ObservableCollection%601>. Un <xref:System.Collections.ObjectModel.ObservableCollection%601> objeto genera una notificación de cambio que puede recibir el motor de enlace de datos. El evento agrega o quita un elemento de un <xref:System.Windows.Controls.ItemsControl> sin necesidad de volver a generar toda la lista.  
  
 La tabla siguiente muestra el tiempo necesario para actualizar el <xref:System.Windows.Controls.ListBox> (con virtualización de interfaz de usuario que se ha desactivado) cuando se agrega un elemento. El número de la primera fila representa el tiempo transcurrido cuando el [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> objeto está enlazado a <xref:System.Windows.Controls.ListBox> del elemento <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. El número de la segunda fila representa el tiempo transcurrido cuando una <xref:System.Collections.ObjectModel.ObservableCollection%601> está enlazado a la <xref:System.Windows.Controls.ListBox> del elemento <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Tenga en cuenta el ahorro de tiempo considerable utilizando el <xref:System.Collections.ObjectModel.ObservableCollection%601> estrategia de enlace de datos.  
  
|**Enlace de datos de ItemsSource**|**Tiempo de actualización para 1 elemento (ms)**|  
|--------------------------------------|---------------------------------------|  
|Para una [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> objeto|1656|  
|Para un <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Enlazar IList a ItemsControl no IEnumerable  
 Si tiene una opción entre enlace un <xref:System.Collections.Generic.IList%601> o un <xref:System.Collections.IEnumerable> a una <xref:System.Windows.Controls.ItemsControl> de objetos, elija la <xref:System.Collections.Generic.IList%601> objeto. Enlace <xref:System.Collections.IEnumerable> a una <xref:System.Windows.Controls.ItemsControl> fuerza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para crear un contenedor <xref:System.Collections.Generic.IList%601> objeto, lo que significa que el rendimiento se ve afectado por la sobrecarga innecesaria de un segundo objeto.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>No convierta objetos CLR a XML solamente para enlazar datos.  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite enlazar datos a contenido [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]. Sin embargo, el enlace de datos al contenido [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] es más lento que el enlace de datos a objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. No convierta datos de objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] a XML si la única finalidad es el enlace de datos.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Texto](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Tutorial: Almacenar en caché datos de la aplicación en una aplicación WPF](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
