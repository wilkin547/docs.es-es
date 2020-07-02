---
title: Información general sobre orígenes de enlaces
description: Descubra los tipos de objetos que puede usar como origen de enlace para las aplicaciones en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 2df2cd11-6aac-4bdf-ab7b-ea5f464cd5ca
ms.openlocfilehash: 11d19d904e632ca2c7c7795946d350d078c38e70
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619629"
---
# <a name="binding-sources-overview"></a>Información general sobre orígenes de enlaces
En el enlace de datos, el objeto de origen de enlace hace referencia al objeto de que se obtienen los datos. En este tema se describen los tipos de objetos que se pueden usar como origen de enlace.

<a name="binding_sources"></a>
## <a name="binding-source-types"></a>Tipos de orígenes de enlace
 El enlace de datos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] admite los siguientes tipos de orígenes de enlace:

|Origen de enlace|Descripción|
|--------------------|-----------------|
|objetos Common Language Runtime (CLR)|Puede enlazar a propiedades públicas, subpropiedades, así como indizadores, de cualquier objeto Common Language Runtime (CLR). El motor de enlace utiliza la reflexión de CLR para obtener los valores de las propiedades. Como alternativa, los objetos que implementan <xref:System.ComponentModel.ICustomTypeDescriptor> o tienen un registrado <xref:System.ComponentModel.TypeDescriptionProvider> también funcionan con el motor de enlace.<br /><br /> Para más información acerca de cómo implementar una clase que puede actuar como un origen de enlace, consulte [Implementar una clase para el origen de enlace](#classes) más adelante en este tema.|
|objetos dinámicos|Puede enlazar a las propiedades y los indizadores disponibles de un objeto que implementa la <xref:System.Dynamic.IDynamicMetaObjectProvider> interfaz. Si se puede acceder al miembro en código, puede enlazar a él. Por ejemplo, si un objeto dinámico permite acceder a un miembro en código mediante `someObjet.AProperty`, puede enlazar a él estableciendo el trazado de enlace en `AProperty`.|
|Objetos ADO.NET|Puede enlazar a objetos ADO.NET, como <xref:System.Data.DataTable> . ADO.NET <xref:System.Data.DataView> implementa la <xref:System.ComponentModel.IBindingList> interfaz, que proporciona notificaciones de cambios que el motor de enlace escucha.|
|Objetos XML|Puede enlazar y ejecutar `XPath` consultas en <xref:System.Xml.XmlNode> , <xref:System.Xml.XmlDocument> o <xref:System.Xml.XmlElement> . Una manera cómoda de acceder a los datos XML que es el origen de enlace en el marcado es usar un <xref:System.Windows.Data.XmlDataProvider> objeto. Para más información, consulte [Cómo: Enlazar a datos XML mediante XMLDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).<br /><br /> También puede enlazar a un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> , o enlazar con los resultados de las consultas que se ejecutan en objetos de estos tipos mediante LINQ to XML. Una manera cómoda de utilizar LINQ to XML para tener acceso a los datos XML que es el origen de enlace en el marcado es usar un <xref:System.Windows.Data.ObjectDataProvider> objeto. Para más información, consulte [Cómo: Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).|
|Objetos <xref:System.Windows.DependencyObject>.|Puede enlazar a las propiedades de dependencia de cualquier <xref:System.Windows.DependencyObject> . Para ver un ejemplo, consulte [Cómo: Enlazar las propiedades de dos controles](how-to-bind-the-properties-of-two-controls.md).|

<a name="classes"></a>
## <a name="implementing-a-class-for-the-binding-source"></a>Implementar una clase para el origen de enlace
 Puede crear sus propios orígenes de enlace. En esta sección se explica lo que necesita saber si está implementando una clase para que actúe como un origen de enlace.

### <a name="providing-change-notifications"></a>Proporcionar notificaciones de cambios
 Si usa <xref:System.Windows.Data.BindingMode.OneWay> <xref:System.Windows.Data.BindingMode.TwoWay> el enlace o (porque desea [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se actualice cuando las propiedades de origen de enlace cambian dinámicamente), debe implementar un mecanismo de notificación de cambio de propiedad adecuado. El mecanismo recomendado es que el CLR o la clase dinámica implementen la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz. Para más información, consulte [Cómo: Implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md).

 Si crea un objeto CLR que no implementa <xref:System.ComponentModel.INotifyPropertyChanged> , debe organizar su propio sistema de notificación para asegurarse de que los datos usados en un enlace permanecen actualizados. Puede proporcionar notificaciones de cambio admitiendo el patrón `PropertyChanged` para cada propiedad para la que desee cambiar las notificaciones. Para admitir este patrón, defina un evento *PropertyName* cambiado para cada propiedad, donde *PropertyName* es el nombre de la propiedad. Se genera el evento cada vez que cambia la propiedad.

 Si el origen de enlace implementa uno de estos mecanismos de notificación, se producen automáticamente las actualizaciones de destino. Si por alguna razón el origen de enlace no proporciona las notificaciones de cambio de propiedad apropiadas, tiene la opción de usar el <xref:System.Windows.Data.BindingExpression.UpdateTarget%2A> método para actualizar la propiedad de destino explícitamente.

### <a name="other-characteristics"></a>Otras características
 En la lista siguiente se proporcionan otros puntos importantes a tener en cuenta:

- Si desea crear el objeto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , la clase debe tener un constructor sin parámetros. En algunos lenguajes .NET, como C#, se podría crear el constructor sin parámetros.

- Las propiedades que se utilizan como propiedades de origen de enlace para un enlace deben ser propiedades públicas de la clase. No se puede acceder a las propiedades de interfaz definidas explícitamente con fines de enlace, ni tampoco las propiedades protegidas, privadas, internas o virtuales que no tengan ninguna implementación base.

- No se puede enlazar a campos públicos.

- El tipo de la propiedad declarada en la clase es el tipo que se pasa al enlace. Sin embargo, el tipo utilizado en última instancia por el enlace depende del tipo de la propiedad de destino de enlace, no de la propiedad de origen de enlace. Si hay una diferencia en el tipo, puede escribir un convertidor para controlar cómo la propiedad personalizada se pasa inicialmente al enlace. Para obtener más información, vea <xref:System.Windows.Data.IValueConverter>.

<a name="objects"></a>
## <a name="using-entire-objects-as-a-binding-source"></a>Utilizar objetos completos como origen de enlace
 Puede utilizar objetos completos como origen de enlace. Puede especificar un origen de enlace mediante la <xref:System.Windows.Data.Binding.Source%2A> <xref:System.Windows.FrameworkElement.DataContext%2A> propiedad o y, a continuación, proporcionar una declaración de enlace en blanco: `{Binding}` . Los escenarios en los que esto resulta útil incluyen enlaces a objetos que son del tipo cadena, enlaces a objetos con varias propiedades en las que esté interesado o el enlace a objetos de la colección. Para obtener un ejemplo de enlace a un objeto de la colección completo, consulte [Cómo: Usar el patrón principal-detalle con datos jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).

 Observe que puede ser necesario aplicar lógica personalizada para que los datos sean significativos para la propiedad de destino enlazada. La lógica personalizada puede tener el formato de un convertidor personalizado (si no existe la conversión de tipos predeterminada) o <xref:System.Windows.DataTemplate> . Para más información sobre los convertidores, consulte la sección de conversión de datos de [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md). Para obtener más información acerca de las plantillas de datos, vea [información general sobre plantillas de datos](data-templating-overview.md).

<a name="collections"></a>
## <a name="using-collection-objects-as-a-binding-source"></a>Utilizar objetos de colección como origen de enlace
 A menudo, el objeto que desea utilizar como origen de enlace es una colección de objetos personalizados. Cada objeto actúa como el origen para una instancia de un enlace repetido. Por ejemplo, podría tener una colección de `CustomerOrders` formada por objetos `CustomerOrder`, donde la aplicación itera en la colección para determinar cuántas órdenes hay y los datos contenidos en cada uno.

 Puede enumerar en cualquier colección que implemente la interfaz <xref:System.Collections.IEnumerable>. Sin embargo, para configurar enlaces dinámicos para que las inserciones o eliminaciones de la colección actualicen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] automáticamente, la colección debe implementar la <xref:System.Collections.Specialized.INotifyCollectionChanged> interfaz. Esta interfaz expone un evento que debe provocarse siempre que se realicen cambios en la colección subyacente.

 La <xref:System.Collections.ObjectModel.ObservableCollection%601> clase es una implementación integrada de una colección de datos que expone la <xref:System.Collections.Specialized.INotifyCollectionChanged> interfaz. Los objetos de datos individuales dentro de la colección deben cumplir los requisitos descritos en las secciones anteriores. Para ver un ejemplo, consulte [Cómo: Crear y enlazar a una colección ObservableCollection](how-to-create-and-bind-to-an-observablecollection.md). Antes de implementar su propia colección, considere la posibilidad de usar <xref:System.Collections.ObjectModel.ObservableCollection%601> o una de las clases de colección existentes, como <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601> y <xref:System.ComponentModel.BindingList%601>, entre muchas otras.

 WPF nunca se enlaza directamente a una colección. Si especifica una colección como origen de enlace, WPF se enlaza en realidad a la vista predeterminada de la colección. Para más información sobre las vistas predeterminadas, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).

 Si tiene un escenario avanzado y desea implementar su propia colección, considere la posibilidad de usar la <xref:System.Collections.IList> interfaz. <xref:System.Collections.IList>proporciona una colección no genérica de objetos a los que se puede tener acceso individualmente por índice, lo que puede mejorar el rendimiento.

<a name="permissions"></a>
## <a name="permission-requirements-in-data-binding"></a>Requisitos de permisos en el enlace de datos
 Cuando se enlazan los datos, debe tener en cuenta el nivel de confianza de la aplicación. La tabla siguiente resume qué tipos de propiedad se pueden enlazar en una aplicación que se ejecuta en plena confianza o en confianza parcial:

|Tipo de propiedad<br /><br /> (todos los modificadores de acceso)|Propiedad de objeto dinámico|Propiedad de objeto dinámico|Propiedad CLR|Propiedad CLR|Propiedad de dependencia|Propiedad de dependencia|
|------------------------------------------------|-----------------------------|-----------------------------|------------------|------------------|-------------------------|-------------------------|
|**Nivel de confianza**|**Plena confianza**|**Confianza parcial**|**Plena confianza**|**Confianza parcial**|**Plena confianza**|**Confianza parcial**|
|Clase pública|Sí|Sí|Sí|Sí|Sí|Sí|
|Clase no pública|Sí|No|Sí|No|Sí|Sí|

 En esta tabla se describen los siguientes puntos importantes acerca de los requisitos de permisos en el enlace de datos:

- En el caso de las propiedades CLR, el enlace de datos funciona siempre que el motor de enlace pueda acceder a la propiedad de origen de enlace mediante la reflexión. De lo contrario, el motor de enlace emite una advertencia que indica que no se encuentra la propiedad y utiliza el valor de reserva o el valor predeterminado, si está disponible.

- Puede enlazar a propiedades en objetos dinámicos que se definen en tiempo de compilación o tiempo de ejecución.

- Siempre puede enlazar a propiedades de dependencia.

 El requisito de permiso para el enlace XML es similar. En un espacio aislado de confianza parcial, <xref:System.Windows.Data.XmlDataProvider> produce un error cuando no tiene permisos para obtener acceso a los datos especificados.

 Los objetos con un tipo anónimo son internos. Puede enlazar a propiedades de tipos anónimos solo cuando se ejecutan en plena confianza. Para más información acerca de los tipos anónimos, consulte [Tipos anónimos (Guía de programación de C#)](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) o [Tipos anónimos (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) (Visual Basic).

 Para más información sobre la seguridad de confianza parcial, consulte [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.ObjectDataProvider>
- <xref:System.Windows.Data.XmlDataProvider>
- [Especificar el origen de enlace](how-to-specify-the-binding-source.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre el enlace de datos de WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Optimizar el rendimiento del enlace de datos](../advanced/optimizing-performance-data-binding.md)
