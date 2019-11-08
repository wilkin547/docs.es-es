---
title: 'Optimizar el rendimiento: Enlace de datos'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 9b302be3ed9f01ccd27470063f49966dc7d74708
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740798"
---
# <a name="optimizing-performance-data-binding"></a>Optimizar el rendimiento: Enlace de datos
El enlace de datos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una manera sencilla y coherente para que las aplicaciones presenten datos e interactúen con ellos. Los elementos se pueden enlazar a datos de una variedad de orígenes de datos en forma de objetos CLR y XML.  
  
 En este tema se proporcionan recomendaciones de rendimiento del enlace de datos.  

<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>Cómo se resuelven las referencias de enlace de datos  
 Antes de tratar los problemas de rendimiento del enlace de datos, vale la pena explorar cómo el motor de enlace de datos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] resuelve las referencias de objeto para el enlace.  
  
 El origen de un enlace de datos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede ser cualquier objeto CLR. Puede enlazar a propiedades, subpropiedades o indizadores de un objeto CLR. Las referencias de enlace se resuelven utilizando Microsoft .NET reflexión del marco de trabajo o un <xref:System.ComponentModel.ICustomTypeDescriptor>. Estos son tres métodos para resolver las referencias de objeto para el enlace.  
  
 El primer método implica el uso de reflexión. En este caso, el objeto de <xref:System.Reflection.PropertyInfo> se utiliza para detectar los atributos de la propiedad y proporciona acceso a los metadatos de la propiedad. Al utilizar la interfaz <xref:System.ComponentModel.ICustomTypeDescriptor>, el motor de enlace de datos utiliza esta interfaz para tener acceso a los valores de propiedad. La interfaz <xref:System.ComponentModel.ICustomTypeDescriptor> es especialmente útil en los casos en los que el objeto no tiene un conjunto estático de propiedades.  
  
 Las notificaciones de cambio de propiedad se pueden proporcionar mediante la implementación de la interfaz de <xref:System.ComponentModel.INotifyPropertyChanged> o mediante las notificaciones de cambio asociadas a la <xref:System.ComponentModel.TypeDescriptor>. Sin embargo, la estrategia preferida para implementar notificaciones de cambios de propiedades es usar <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Si el objeto de origen es un objeto CLR y la propiedad de origen es una propiedad de CLR, el motor de enlace de datos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] tiene que usar primero la reflexión en el objeto de origen para obtener la <xref:System.ComponentModel.TypeDescriptor>y, a continuación, consultar un <xref:System.ComponentModel.PropertyDescriptor>. Esta secuencia de operaciones de reflexión es potencialmente muy lenta, desde una perspectiva de rendimiento.  
  
 El segundo método para resolver las referencias de objeto implica un objeto de origen de CLR que implementa la interfaz de <xref:System.ComponentModel.INotifyPropertyChanged> y una propiedad de origen que es una propiedad de CLR. En este caso, el motor de enlace de datos usa la reflexión directamente en el tipo de origen y obtiene la propiedad necesaria. No es el método óptimo, pero tendrá un costo menor en los requisitos del conjunto de trabajo comparado con el primer método.  
  
 El tercer método para resolver las referencias de objeto implica un objeto de origen que es un <xref:System.Windows.DependencyObject> y una propiedad de origen que es un <xref:System.Windows.DependencyProperty>. En este caso, el motor de enlace de datos no necesita usar la reflexión. En su lugar, el motor de propiedad y el motor de enlace de datos resuelven juntos la referencia de propiedad por separado. Este es el método óptimo para resolver las referencias de objeto que se usa para el enlace de datos.  
  
 En la tabla siguiente se compara la velocidad del enlace de datos de la <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad de los elementos 1000 <xref:System.Windows.Controls.TextBlock> con estos tres métodos.  
  
|**Enlazar la propiedad de texto de TextBlock**|**Tiempo de enlace (ms)**|**Tiempo de representación, incluido el enlace (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|A una propiedad de un objeto CLR|115|314|  
|A una propiedad de un objeto CLR que implementa <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|En una <xref:System.Windows.DependencyProperty> de un <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>Enlazar a objetos CLR grandes  
 Hay un impacto significativo en el rendimiento cuando se enlazan datos a un solo objeto CLR con miles de propiedades. Puede minimizar este impacto dividiendo el objeto único en varios objetos CLR con menos propiedades. En la tabla se muestran los tiempos de enlace y representación para el enlace de datos a un solo objeto CLR grande en comparación con varios objetos más pequeños.  
  
|**Enlace de datos de 1000 objetos TextBlock**|**Tiempo de enlace (ms)**|**Tiempo de representación, incluido el enlace (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|A un objeto CLR con propiedades 1000|950|1200|  
|A 1000 objetos CLR con una propiedad|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>Enlazar a ItemsSource  
 Considere un escenario en el que tiene un objeto de <xref:System.Collections.Generic.List%601> de CLR que contiene una lista de empleados que desea mostrar en un <xref:System.Windows.Controls.ListBox>. Para crear una correspondencia entre estos dos objetos, debe enlazar la lista de empleados a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de la <xref:System.Windows.Controls.ListBox>. Sin embargo, suponga que tiene un nuevo empleado que se incorpora al grupo. Podría pensar que, para insertar esta nueva persona en los valores de <xref:System.Windows.Controls.ListBox> enlazados, solo tendría que agregar esta persona a la lista de empleados y esperar que el motor de enlace de datos reconozca este cambio automáticamente. Esa hipótesis sería falsa. en realidad, el cambio no se reflejará automáticamente en el <xref:System.Windows.Controls.ListBox>. Esto se debe a que el objeto CLR <xref:System.Collections.Generic.List%601> no genera automáticamente un evento de cambio de colección. Con el fin de obtener el <xref:System.Windows.Controls.ListBox> para recoger los cambios, tendría que volver a crear la lista de empleados y volver a adjuntarlo a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de la <xref:System.Windows.Controls.ListBox>. Aunque esta solución funciona, supone un impacto enorme en el rendimiento. Cada vez que se reasigna el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de <xref:System.Windows.Controls.ListBox> a un nuevo objeto, el <xref:System.Windows.Controls.ListBox> primero elimina los elementos anteriores y vuelve a generar toda la lista. El impacto en el rendimiento aumenta si el <xref:System.Windows.Controls.ListBox> se asigna a un <xref:System.Windows.DataTemplate>complejo.  
  
 Una solución muy eficaz para este problema consiste en convertir la lista de empleados en una <xref:System.Collections.ObjectModel.ObservableCollection%601>. Un objeto <xref:System.Collections.ObjectModel.ObservableCollection%601> genera una notificación de cambio que el motor de enlace de datos puede recibir. El evento agrega o quita un elemento de una <xref:System.Windows.Controls.ItemsControl> sin necesidad de volver a generar la lista completa.  
  
 En la tabla siguiente se muestra el tiempo que se tarda en actualizar el <xref:System.Windows.Controls.ListBox> (con la virtualización de la interfaz de usuario desactivada) cuando se agrega un elemento. El número de la primera fila representa el tiempo transcurrido cuando el objeto CLR <xref:System.Collections.Generic.List%601> se enlaza al <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>del elemento <xref:System.Windows.Controls.ListBox>. El número de la segunda fila representa el tiempo transcurrido cuando un <xref:System.Collections.ObjectModel.ObservableCollection%601> se enlaza a la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>del elemento de <xref:System.Windows.Controls.ListBox>. Tenga en cuenta el importante ahorro de tiempo con la estrategia de enlace de datos de <xref:System.Collections.ObjectModel.ObservableCollection%601>.  
  
|**Enlace de datos de ItemsSource**|**Tiempo de actualización para 1 elemento (ms)**|  
|--------------------------------------|---------------------------------------|  
|A un objeto <xref:System.Collections.Generic.List%601> de CLR|1656|  
|A un <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Enlazar IList a ItemsControl no IEnumerable  
 Si tiene la opción de enlazar un <xref:System.Collections.Generic.IList%601> o un <xref:System.Collections.IEnumerable> a un objeto de <xref:System.Windows.Controls.ItemsControl>, elija el objeto de <xref:System.Collections.Generic.IList%601>. Enlazar <xref:System.Collections.IEnumerable> a un <xref:System.Windows.Controls.ItemsControl> obliga a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a crear un contenedor <xref:System.Collections.Generic.IList%601> objeto, lo que significa que el rendimiento se ve afectado por la sobrecarga innecesaria de un segundo objeto.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>No convierta objetos CLR a XML solamente para enlazar datos.  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite enlazar datos al contenido XML; sin embargo, el enlace de datos a contenido XML es más lento que el enlace de datos a objetos CLR. No convierta los datos de objetos de CLR a XML si el único propósito es el enlace de datos.  
  
## <a name="see-also"></a>Vea también

- [Optimizar el rendimiento de la aplicación WPF](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamiento de objetos](optimizing-performance-object-behavior.md)
- [Recursos de la aplicación](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Tutorial: Almacenar en caché datos de la aplicación en una aplicación WPF](walkthrough-caching-application-data-in-a-wpf-application.md)
