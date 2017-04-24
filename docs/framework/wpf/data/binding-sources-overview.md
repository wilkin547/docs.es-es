---
title: "Informaci&#243;n general sobre or&#237;genes de enlaces | Microsoft Docs"
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
  - "enlazar datos, orígenes de enlace"
  - "orígenes de enlace"
  - "enlace de datos, origen de enlace"
ms.assetid: 2df2cd11-6aac-4bdf-ab7b-ea5f464cd5ca
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Informaci&#243;n general sobre or&#237;genes de enlaces
En el enlace de datos, el objeto de [origen de enlace](GTMT) hace referencia al objeto del que se obtienen los datos.  En este tema se describen los tipos de objetos que pueden utilizarse como origen de enlace.  
  
   
  
<a name="binding_sources"></a>   
## Tipos de origen de enlace  
 El enlace de datos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] admite los siguientes tipos de [origen de enlace](GTMT):  
  
|Origen de enlace|Descripción|  
|----------------------|-----------------|  
|Objetos [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]|Puede enlazar a propiedades públicas, subpropiedades e indizadores de cualquier objeto [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  El motor de enlace utiliza la reflexión [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] para obtener los valores de las propiedades.  Como alternativa, también funcionan con el motor de enlace los objetos que implementan <xref:System.ComponentModel.ICustomTypeDescriptor> o que tienen un <xref:System.ComponentModel.TypeDescriptionProvider> registrado.<br /><br /> Para obtener más información sobre cómo implementar una clase que sirva como un origen de enlace, vea [Implementar una clase para el origen de enlace](#classes) posterior en este tema.|  
|objetos dinámicos|Puede enlazar a las propiedades e indizadores disponibles de un objeto que implemente la interfaz <xref:System.Dynamic.IDynamicMetaObjectProvider>.  Si puede tener acceso al miembro en código, puede llevar a cabo el enlace.  Por ejemplo, si un objeto dinámico permite tener acceso a un miembro en el código a través de `someObjet.AProperty`, puede enlazar a él estableciendo la ruta de acceso de enlace en `AProperty`.|  
|Objetos [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)]|Puede enlazar a objetos de [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)], como <xref:System.Data.DataTable>. [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)] <xref:System.Data.DataView> implementa la interfaz <xref:System.ComponentModel.IBindingList>, que proporciona notificaciones de cambios para las que el motor de enlace realiza escuchas.|  
|Objetos [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]|Puede enlazar a y ejecutar consultas `XPath` en <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlDocument> o <xref:System.Xml.XmlElement>.  Una manera cómoda de tener acceso a los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] que constituyen el [origen de enlace](GTMT) en el marcado es utilizar un objeto <xref:System.Windows.Data.XmlDataProvider>.  Para obtener más información, vea [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).<br /><br /> También puede enlazar a <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o bien enlazar a los resultados de consultas ejecutadas en objetos de estos tipos mediante LINQ to XML.  Una manera cómoda de usar LINQ to XML para tener acceso a los datos XML que son el origen de enlace en el marcado es utilizar un objeto <xref:System.Windows.Data.ObjectDataProvider>.  Para obtener más información, vea [Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).|  
|Objetos <xref:System.Windows.DependencyObject>|Puede enlazar a [propiedades de dependencia](GTMT) de cualquier objeto <xref:System.Windows.DependencyObject>.  Para obtener un ejemplo, vea [Enlazar las propiedades de dos controles](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md).|  
  
<a name="classes"></a>   
## Implementar una clase para el origen de enlace  
 Puede crear orígenes de enlace propios.  En esta sección se explica lo que debe saber para implementar una clase para que actúe como un origen de enlace.  
  
### Proporcionar notificaciones de cambio  
 Si utiliza el enlace <xref:System.Windows.Data.BindingMode> o <xref:System.Windows.Data.BindingMode> \(porque desea que la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se actualice cuando cambien dinámicamente las propiedades del origen de enlace\), debe implementar un mecanismo apropiado de notificación de cambio de propiedad.  El mecanismo recomendado es que [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] o la clase dinámica implemente la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.  Para obtener más información, consulte [Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 Si crea un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] que no implementa <xref:System.ComponentModel.INotifyPropertyChanged>, deberá utilizar su propio sistema de notificación para asegurarse de que los datos utilizados en un enlace estén siempre actualizados.  Puede proporcionar notificaciones de cambio admitiendo el modelo `PropertyChanged` para cada propiedad cuyas notificaciones de cambio desea obtener.  Para admitir este modelo, se define un evento *nombreDePropiedad*Changed para cada propiedad, donde *nombreDePropiedad* es el nombre de la propiedad.  El evento se provoca cada vez que cambia la propiedad.  
  
 Si el origen de enlace implementa uno de estos mecanismo de notificación, el destino se actualiza automáticamente.  Si por cualquier motivo el origen de enlace no proporciona notificaciones de cambio de propiedad correctas, puede utilizar el método <xref:System.Windows.Data.BindingExpression.UpdateTarget%2A> para actualizar explícitamente la propiedad de destino.  
  
### Otras características  
 En la lista siguiente se proporcionan otros puntos importantes que tener en cuenta:  
  
-   Si desea crear el objeto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], la clase debe tener un constructor predeterminado.  En algunos lenguajes de [!INCLUDE[TLA2#tla_net](../../../../includes/tla2sharptla-net-md.md)], como [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], el constructor predeterminado puede crearse automáticamente.  
  
-   Las propiedades que se utilizan como propiedades de origen de enlace para un enlace deben ser propiedades públicas de la clase.  Para los enlaces no se puede tener acceso a las propiedades de interfaz definidas explícitamente; ni tampoco a las propiedades protegidas, privadas, internas o virtuales que no tengan una implementación base.  
  
-   No puede enlazar a campos públicos.  
  
-   El tipo de la propiedad declarado en la clase es el tipo que se pasa al enlace.  Sin embargo, el tipo que el enlace utiliza en realidad depende del tipo de la propiedad del [destino del enlace](GTMT), no de la propiedad de origen de enlace.  Si existe alguna diferencia de tipos, puede ser conveniente escribir a un convertidor para administrar la manera de pasar inicialmente la propiedad personalizada al enlace.  Para obtener más información, vea <xref:System.Windows.Data.IValueConverter>.  
  
<a name="objects"></a>   
## Utilizar objetos completos como origen de enlace  
 Puede utilizar un objeto completo como un origen de enlace.  Puede especificar un origen de enlace utilizando la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> o <xref:System.Windows.Data.Binding.Source%2A> y, a continuación, proporcionando una declaración de enlace en blanco: `{Binding}`.  Los escenarios en que puede resultar útil esta posibilidad son el enlace a objetos de tipo String, el enlace a objetos con varias propiedades que le interesan o el enlace a objetos de colección.  Para obtener un ejemplo de enlace a un objeto de colección completo, vea [Usar el patrón principal\-detalle con datos jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Observe que puede ser necesario aplicar lógica personalizada para que los datos sean significativos para la propiedad de destino enlazada.  La lógica personalizada puede consistir en un convertidor personalizado \(si no existe la conversión de tipos predeterminada\) o en un objeto <xref:System.Windows.DataTemplate>.  Para obtener más información sobre convertidores, vea la sección de conversión de datos de [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  Para obtener más información sobre plantillas de datos, vea [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
<a name="collections"></a>   
## Utilizar objetos de colección como origen de enlace  
 A menudo, el objeto que desea utilizar como origen de enlace es una colección de objetos personalizados.  Cada objeto actúa como el origen para una instancia de un enlace repetido.  Por ejemplo, supongamos que tiene una colección `CustomerOrders` compuesta de objetos `CustomerOrder`, y que la aplicación itera en la colección para determinar cuántas órdenes hay y qué datos contiene cada una.  
  
 Es posible enumerar cualquier colección que implementa la interfaz <xref:System.Collections.IEnumerable>.  Sin embargo, para configurar enlaces dinámicos de modo que las inserciones o eliminaciones que se realicen en la colección actualicen la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de forma automática, la colección debe implementar la interfaz <xref:System.Collections.Specialized.INotifyCollectionChanged>.  Esta interfaz expone un evento que debe provocarse siempre que se realicen cambios en la colección subyacente.  
  
 La clase <xref:System.Collections.ObjectModel.ObservableCollection%601> es una implementación integrada de una recolección de datos que expone la interfaz <xref:System.Collections.Specialized.INotifyCollectionChanged>.  Los objetos de datos individuales de la colección deben cumplir los requisitos que se describen en las secciones anteriores.  Para obtener un ejemplo, vea [Crear y enlazar a una colección ObservableCollection](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md).  Antes de implementar su propia colección, considere la posibilidad de utilizar <xref:System.Collections.ObjectModel.ObservableCollection%601> o una de las clases de colección existentes, como <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601> y <xref:System.ComponentModel.BindingList%601>, entre otras muchas.  
  
 WPF nunca se enlaza directamente a una colección.  Si se especifica una colección como origen de enlace, WPF se enlaza en realidad a la vista predeterminada de la colección.  Para obtener información sobre las vistas predeterminadas, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Si tiene un escenario avanzado y desea implementar una colección propia, considere el uso de la interfaz <xref:System.Collections.IList>.  <xref:System.Collections.IList> proporciona una colección no genérica de objetos a los que se puede tener acceso individualmente por índice, lo que puede mejorar el rendimiento.  
  
<a name="permissions"></a>   
## Requisitos de permisos en el enlace de datos  
 Al enlazar datos, debe tener en cuenta el nivel de confianza de la aplicación.  En la tabla siguiente se resume a qué tipos de propiedad se puede enlazar en una aplicación que se ejecuta con permisos de plena confianza o de confianza parcial:  
  
|Tipo de propiedad<br /><br /> \(todos los modificadores de acceso\)|Propiedad de objeto dinámico|Propiedad de objeto dinámico|Propiedad CLR|Propiedad CLR|Propiedad de dependencia|Propiedad de dependencia|  
|-----------------------------------------------------------------|----------------------------------|----------------------------------|-------------------|-------------------|------------------------------|------------------------------|  
|**Nivel de confianza**|**Plena confianza**|**Confianza parcial**|**Plena confianza**|**Confianza parcial**|**Plena confianza**|**Confianza parcial**|  
|Clase pública|Sí|Sí|Sí|Sí|Sí|Sí|  
|Clase no pública|Sí|No|Sí|No|Sí|Sí|  
  
 En esta tabla se describen los puntos importantes siguientes sobre los requisitos de permiso en el enlace de datos:  
  
-   Para las propiedades [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], el enlace de datos funciona siempre que el motor de enlace pueda tener acceso a la propiedad de origen de enlace mediante la reflexión.  De lo contrario, el motor de enlace emite una advertencia que indica que no se puede buscar la propiedad y utiliza el valor de reserva o el valor predeterminado, si está disponible.  
  
-   Puede enlazar a propiedades en objetos dinámicos que se definen en tiempo de compilación o en tiempo de ejecución.  
  
-   Siempre se puede enlazar a [propiedades de dependencia](GTMT).  
  
 El requisito de permisos para el enlace a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] es similar. En un espacio aislado de confianza parcial, <xref:System.Windows.Data.XmlDataProvider> produce un error cuando no tiene permisos para tener acceso a los datos especificados.  
  
 Los objetos con tipo anónimo son internos.  Solo puede enlazar a las propiedades de tipos anónimos cuando se ejecuta con plena confianza.  Para obtener más información sobre los tipos anónimos, vea [Tipos anónimos \(Guía de programación de C\#\)](../Topic/Anonymous%20Types%20\(C%23%20Programming%20Guide\).md) o [Tipos anónimos \(Visual Basic\)](../Topic/Anonymous%20Types%20\(Visual%20Basic\).md) \(Visual Basic\).  
  
 Para obtener más información acerca de la seguridad de confianza parcial, vea [Seguridad de confianza parcial de WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
## Vea también  
 <xref:System.Windows.Data.ObjectDataProvider>   
 <xref:System.Windows.Data.XmlDataProvider>   
 [Especificar el origen de enlace](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Información general sobre el enlace de datos de WPF con LINQ to XML](../Topic/WPF%20Data%20Binding%20with%20LINQ%20to%20XML%20Overview.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)