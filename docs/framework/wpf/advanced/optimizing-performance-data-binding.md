---
title: 'Optimizar el rendimiento: Enlace de datos'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 3128f453378f9d74f867b571e30f2be4e8add8a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186759"
---
# <a name="optimizing-performance-data-binding"></a>Optimizar el rendimiento: Enlace de datos
El enlace de datos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una manera sencilla y coherente para que las aplicaciones presenten datos e interactúen con ellos. Los elementos se pueden enlazar a datos de una variedad de orígenes de datos en forma de objetos CLR y XML.  
  
 En este tema se proporcionan recomendaciones de rendimiento del enlace de datos.  

<a name="HowDataBindingReferencesAreResolved"></a>
## <a name="how-data-binding-references-are-resolved"></a>Cómo se resuelven las referencias de enlace de datos  
 Antes de tratar los problemas de rendimiento del enlace de datos, vale la pena explorar cómo el motor de enlace de datos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] resuelve las referencias de objeto para el enlace.  
  
 El origen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] de un enlace de datos puede ser cualquier objeto CLR. Puede enlazar a propiedades, subpropiedades o indizadores de un objeto CLR. Las referencias de enlace se resuelven mediante <xref:System.ComponentModel.ICustomTypeDescriptor>la reflexión de Microsoft .NET Framework o un archivo . Estos son tres métodos para resolver las referencias de objeto para el enlace.  
  
 El primer método implica el uso de reflexión. En este caso, el <xref:System.Reflection.PropertyInfo> objeto se utiliza para detectar los atributos de la propiedad y proporciona acceso a los metadatos de propiedad. Cuando se <xref:System.ComponentModel.ICustomTypeDescriptor> usa la interfaz, el motor de enlace de datos utiliza esta interfaz para tener acceso a los valores de propiedad. La <xref:System.ComponentModel.ICustomTypeDescriptor> interfaz es especialmente útil en casos donde el objeto no tiene un conjunto estático de propiedades.  
  
 Las notificaciones de cambio de <xref:System.ComponentModel.INotifyPropertyChanged> propiedad se pueden proporcionar mediante la <xref:System.ComponentModel.TypeDescriptor>implementación de la interfaz o mediante las notificaciones de cambio asociadas con el archivo . Sin embargo, la estrategia preferida para <xref:System.ComponentModel.INotifyPropertyChanged>implementar notificaciones de cambio de propiedad es usar .  
  
 Si el objeto de origen es un objeto CLR [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y la propiedad source es una propiedad CLR, el motor de enlace de datos tiene que usar primero la reflexión en el objeto de origen para obtener el <xref:System.ComponentModel.TypeDescriptor>archivo , y, a continuación, consultar un <xref:System.ComponentModel.PropertyDescriptor>archivo . Esta secuencia de operaciones de reflexión es potencialmente muy lenta, desde una perspectiva de rendimiento.  
  
 El segundo método para resolver referencias a objetos implica <xref:System.ComponentModel.INotifyPropertyChanged> un objeto de origen CLR que implementa la interfaz y una propiedad de origen que es una propiedad CLR. En este caso, el motor de enlace de datos usa la reflexión directamente en el tipo de origen y obtiene la propiedad necesaria. No es el método óptimo, pero tendrá un costo menor en los requisitos del conjunto de trabajo comparado con el primer método.  
  
 El tercer método para resolver referencias a objetos <xref:System.Windows.DependencyObject> implica un objeto <xref:System.Windows.DependencyProperty>de origen que es a y una propiedad de origen que es un archivo . En este caso, el motor de enlace de datos no necesita usar la reflexión. En su lugar, el motor de propiedad y el motor de enlace de datos resuelven juntos la referencia de propiedad por separado. Este es el método óptimo para resolver las referencias de objeto que se usa para el enlace de datos.  
  
 La tabla siguiente compara la velocidad <xref:System.Windows.Controls.TextBlock.Text%2A> del enlace <xref:System.Windows.Controls.TextBlock> de datos de la propiedad de mil elementos mediante estos tres métodos.  
  
|**Enlazar la propiedad de texto de TextBlock**|**Tiempo de enlace (ms)**|**Tiempo de representación, incluido el enlace (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|A una propiedad de un objeto CLR|115|314|  
|A una propiedad de un objeto CLR que implementa<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|A <xref:System.Windows.DependencyProperty> un <xref:System.Windows.DependencyObject>de un .|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>
## <a name="binding-to-large-clr-objects"></a>Enlazar a objetos CLR grandes  
 Hay un impacto significativo en el rendimiento cuando los datos se enlazan a un único objeto CLR con miles de propiedades. Puede minimizar este impacto dividiendo el único objeto en varios objetos CLR con menos propiedades. La tabla muestra los tiempos de enlace y representación para el enlace de datos a un único objeto CLR grande frente a varios objetos más pequeños.  
  
|**Enlace de datos de 1000 objetos TextBlock**|**Tiempo de enlace (ms)**|**Tiempo de representación, incluido el enlace (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|A un objeto CLR con 1000 propiedades|950|1200|  
|A 1000 objetos CLR con una propiedad|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>
## <a name="binding-to-an-itemssource"></a>Enlazar a ItemsSource  
 Considere un escenario en el <xref:System.Collections.Generic.List%601> que tiene un objeto CLR que contiene <xref:System.Windows.Controls.ListBox>una lista de empleados que desea mostrar en un archivo . Para crear una correspondencia entre estos dos objetos, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> enlazaría <xref:System.Windows.Controls.ListBox>la lista de empleados a la propiedad del archivo . Sin embargo, suponga que tiene un nuevo empleado que se incorpora al grupo. Podría pensar que para insertar esta nueva <xref:System.Windows.Controls.ListBox> persona en sus valores enlazados, simplemente agregaría esta persona a su lista de empleados y esperaría que este cambio sea reconocido por el motor de enlace de datos automáticamente. Esa suposición resultaría falsa; en realidad, el cambio no se reflejará <xref:System.Windows.Controls.ListBox> automáticamente. Esto se debe <xref:System.Collections.Generic.List%601> a que el objeto CLR no genera automáticamente un evento de cambio de colección. Con el fin <xref:System.Windows.Controls.ListBox> de obtener el para recoger los cambios, tendría que volver <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> a crear <xref:System.Windows.Controls.ListBox>su lista de empleados y volver a adjuntarlo a la propiedad de la . Aunque esta solución funciona, supone un impacto enorme en el rendimiento. Cada vez que <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> se <xref:System.Windows.Controls.ListBox> reasigna el <xref:System.Windows.Controls.ListBox> de a un nuevo objeto, el primero descarta sus elementos anteriores y regenera toda su lista. El impacto en el <xref:System.Windows.Controls.ListBox> rendimiento se <xref:System.Windows.DataTemplate>amplía si los mapas se asignan a un archivo .  
  
 Una solución muy eficiente a este problema <xref:System.Collections.ObjectModel.ObservableCollection%601>es hacer que su lista de empleados sea un archivo . Un <xref:System.Collections.ObjectModel.ObservableCollection%601> objeto genera una notificación de cambio que puede recibir el motor de enlace de datos. El evento agrega o quita un <xref:System.Windows.Controls.ItemsControl> elemento de un sin necesidad de regenerar toda la lista.  
  
 La tabla siguiente muestra el tiempo <xref:System.Windows.Controls.ListBox> que se tarda en actualizar (con la virtualización de la interfaz de usuario desactivada) cuando se agrega un elemento. El número de la primera fila representa el <xref:System.Collections.Generic.List%601> tiempo transcurrido <xref:System.Windows.Controls.ListBox> cuando <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>el objeto CLR está enlazado a elementos . El número de la segunda fila representa <xref:System.Collections.ObjectModel.ObservableCollection%601> el tiempo <xref:System.Windows.Controls.ListBox> transcurrido cuando <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>se enlaza un al elemento . Tenga en cuenta el <xref:System.Collections.ObjectModel.ObservableCollection%601> ahorro significativo de tiempo mediante la estrategia de enlace de datos.  
  
|**Enlace de datos de ItemsSource**|**Tiempo de actualización para 1 elemento (ms)**|  
|--------------------------------------|---------------------------------------|  
|A un <xref:System.Collections.Generic.List%601> objeto CLR|1656|  
|A un<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Enlazar IList a ItemsControl no IEnumerable  
 Si tiene la opción <xref:System.Collections.Generic.IList%601> de <xref:System.Collections.IEnumerable> enlazar <xref:System.Windows.Controls.ItemsControl> un objeto <xref:System.Collections.Generic.IList%601> o un a uno, elija el objeto. Enlazar <xref:System.Collections.IEnumerable> a <xref:System.Windows.Controls.ItemsControl> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] una fuerza <xref:System.Collections.Generic.IList%601> para crear un objeto contenedor, lo que significa que el rendimiento se ve afectado por la sobrecarga innecesaria de un segundo objeto.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>No convierta objetos CLR a XML solamente para enlazar datos.  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le permite enlazar datos a contenido XML; sin embargo, el enlace de datos al contenido XML es más lento que el enlace de datos a objetos CLR. No convierta los datos de objeto CLR a XML si el único propósito es el enlace de datos.  
  
## <a name="see-also"></a>Consulte también

- [Optimizar WPF: Rendimiento de aplicaciones](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamiento de objetos](optimizing-performance-object-behavior.md)
- [Recursos de aplicación](optimizing-performance-application-resources.md)
- [Texto](optimizing-performance-text.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
- [Descripción general del enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Walkthrough: Caching Application Data in a WPF Application (Tutorial: almacenamiento en caché de datos de aplicación en una aplicación WPF)](walkthrough-caching-application-data-in-a-wpf-application.md)
