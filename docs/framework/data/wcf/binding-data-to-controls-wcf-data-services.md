---
title: Enlazar datos a controles (Servicios de datos de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- data binding, WCF Data Services
ms.assetid: b32e1d49-c214-4cb1-867e-88fbb3d08c8d
ms.openlocfilehash: 178d77c225144497982487afa00f4493e17d1744
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805218"
---
# <a name="binding-data-to-controls-wcf-data-services"></a>Enlazar datos a controles (Servicios de datos de WCF)

Con WCF Data Services, puede enlazar controles como los `ComboBox` controles y `ListView` a una instancia de la <xref:System.Data.Services.Client.DataServiceCollection%601> clase. Esta colección, que hereda de la <xref:System.Collections.ObjectModel.ObservableCollection%601> clase, contiene los datos de una fuente Open Data Protocol (OData). Esta clase representa una colección de datos dinámicos que proporciona notificaciones si se agregan o se quitan elementos. Cuando se usa una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> para el enlace de datos, las bibliotecas de cliente de WCF Data Services controlan estos eventos para garantizar que los objetos a los que hace seguimiento <xref:System.Data.Services.Client.DataServiceContext> permanecen sincronizados con los datos del elemento de la interfaz de usuario enlazado.  
  
 La clase <xref:System.Data.Services.Client.DataServiceCollection%601>(indirectamente) implementa la interfaz <xref:System.Collections.Specialized.INotifyCollectionChanged> para avisar al contexto en el momento en el que se agreguen o quiten objetos de la colección. Los objetos de tipo de servicio de datos usados con una clase <xref:System.Data.Services.Client.DataServiceCollection%601> también deben implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> para avisar a la clase <xref:System.Data.Services.Client.DataServiceCollection%601> en el momento en el que cambien las propiedades de los objetos en la colección de enlaces.  
  
> [!NOTE]
> Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** o la herramienta de [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) con la `/dataservicecollection` opción de generar las clases de servicio de datos de cliente, las clases de datos generadas implementan la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz. Para obtener más información, vea [Cómo: generar manualmente clases del servicio de datos del cliente](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="creating-the-binding-collection"></a>Crear la colección de enlaces  

 Cree una nueva instancia de la clase <xref:System.Data.Services.Client.DataServiceCollection%601> llamando a uno de los métodos de constructor de clase con una instancia <xref:System.Data.Services.Client.DataServiceContext> proporcionada y, opcionalmente, una consulta <xref:System.Data.Services.Client.DataServiceQuery%601> o LINQ que, cuando se ejecuta, devuelve una instancia <xref:System.Collections.Generic.IEnumerable%601>. Esto <xref:System.Collections.Generic.IEnumerable%601> proporciona el origen de objetos para la colección de enlaces, que se materializan a partir de una fuente de oData. Para obtener más información, consulte [materialización de objetos](object-materialization-wcf-data-services.md). De manera predeterminada, <xref:System.Data.Services.Client.DataServiceContext> realiza automáticamente el seguimiento de los cambios realizados en los objetos enlazados y elementos insertados en la colección. Si necesita realizar un seguimiento de estos cambios manualmente, llame a uno de los métodos de constructor que toma un `trackingMode` parámetro y especifique un valor de <xref:System.Data.Services.Client.TrackingMode.None> .  
  
 En el siguiente ejemplo se muestra cómo crear una instancia de la clase <xref:System.Data.Services.Client.DataServiceCollection%601> basada en un <xref:System.Data.Services.Client.DataServiceContext> proporcionado y una <xref:System.Data.Services.Client.DataServiceQuery%601> que devuelve todos los clientes con pedidos (en el ejemplo, Orders) relacionados:  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders2.cs#customersorders2binding)]
 [!code-vb[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders2.vb#customersorders2binding)]  
  
## <a name="binding-data-to-windows-presentation-foundation-elements"></a>Enlazar datos a elementos de Windows Presentation Foundation  

 Dado que la clase <xref:System.Data.Services.Client.DataServiceCollection%601> se hereda de la clase <xref:System.Collections.ObjectModel.ObservableCollection%601>, puede enlazar los objetos a un elemento o control en una aplicación Windows Presentation Foundation (WPF) tal como lo haría si usara la clase <xref:System.Collections.ObjectModel.ObservableCollection%601> para el enlace. Para obtener más información, consulte [enlace de datos (Windows Presentation Foundation)](/dotnet/desktop/wpf/data/data-binding-overview). Una manera de enlazar los datos del servicio de datos a controles WPF es establecer la propiedad `DataContext` del elemento para la instancia de la clase <xref:System.Data.Services.Client.DataServiceCollection%601> que contiene el resultado de la consulta. En este caso, usted utiliza la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para establecer el origen del objeto para el control. Utilice la propiedad <xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A> para especificar qué propiedad mostrar del objeto enlazado. Si está enlazando un elemento a un objeto relacionado que devuelve una propiedad de navegación, incluya la ruta de acceso en el enlace definido para la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Esta ruta de acceso es relativa al objeto raíz establecido por la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> del control primario. En el siguiente ejemplo se establece la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de un elemento <xref:System.Windows.Controls.StackPanel> para enlazar el control primario a una clase <xref:System.Data.Services.Client.DataServiceCollection%601> de objetos de cliente:  
  
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#masterdetailbinding)]
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#masterdetailbinding)]  
  
 En el ejemplo siguiente se muestra la definición de enlace XAML de los controles <xref:System.Windows.Controls.DataGrid> y <xref:System.Windows.Controls.ComboBox> secundarios:  
  
 [!code-xaml[Astoria Northwind Client#MasterDetailXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#masterdetailxaml)]  
  
 Para obtener más información, vea [Cómo: enlazar datos a elementos de Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md).  
  
 Cuando una entidad participa en una relación de uno a varios o de varios a varios, la propiedad de navegación para la relación devuelve una colección de objetos relacionados. Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** o la herramienta DataSvcUtil.exe para generar las clases del servicio de datos del cliente, la propiedad de navegación devuelve una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> . Esto le permite enlazar objetos relacionados a un control, así como admitir escenarios de enlace de WPF comunes, como el patrón de enlace principal-detalle para entidades relacionadas. En el ejemplo XAML anterior, el código XAML enlaza la clase principal <xref:System.Data.Services.Client.DataServiceCollection%601> al elemento de datos de raíz. El pedido <xref:System.Windows.Controls.DataGrid> se enlaza a la clase <xref:System.Data.Services.Client.DataServiceCollection%601> de pedidos devueltos desde el objeto Customers seleccionado, que se enlaza a su vez al elemento de datos de raíz de <xref:System.Windows.Window>.  
  
## <a name="binding-data-to-windows-forms-controls"></a>Enlazar datos a controles de Windows Forms  

 Para enlazar objetos a un control de Windows Form, establezca la propiedad `DataSource` del control en la instancia de la clase <xref:System.Data.Services.Client.DataServiceCollection%601> que contiene el resultado de la consulta.  
  
> [!NOTE]
> El enlace de datos solo se admite para los controles que realizan escuchas de los eventos de cambio mediante la implementación de las interfaces <xref:System.Collections.Specialized.INotifyCollectionChanged> y <xref:System.ComponentModel.INotifyPropertyChanged>. Cuando un control no admite este tipo de notificación de cambios, los cambios que se realizan en la clase <xref:System.Data.Services.Client.DataServiceCollection%601> subyacente no se reflejan en el control enlazado.  
  
 En el siguiente ejemplo <xref:System.Data.Services.Client.DataServiceCollection%601> se enlaza a <xref:System.Windows.Forms.ComboBox>:  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdatabindingspecific)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdatabindingspecific)]  
  
 Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** para generar las clases del servicio de datos del cliente, también se crea un origen de datos del proyecto que se basa en el generado <xref:System.Data.Services.Client.DataServiceContext> . Con este origen de datos, puede crear elementos de interfaz de usuario o controles que muestren los datos del servicio de datos simplemente arrastrando elementos desde la ventana **orígenes de datos** hasta el diseñador. Estos elementos aparecen en la interfaz de usuario de la aplicación y se enlazan al origen de datos. Para obtener más información, vea [Cómo: enlazar datos mediante un origen de datos de proyecto](how-to-bind-data-using-a-project-data-source-wcf-data-services.md).  
  
## <a name="binding-paged-data"></a>Enlazar datos paginados  

 Un servicio de datos se puede configurar para limitar la cantidad de datos consultados que se devuelven en un único mensaje de respuesta. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md). Cuando el servicio de datos está paginando los datos de respuesta, cada respuesta contiene un vínculo que se utiliza para devolver la página siguiente de resultados. Para obtener más información, vea [cargar contenido diferido](loading-deferred-content-wcf-data-services.md). En este caso, debe cargar las páginas explícitamente llamando al método <xref:System.Data.Services.Client.DataServiceCollection%601.Load%2A> en la clase <xref:System.Data.Services.Client.DataServiceCollection%601>, especificando el URI obtenido de la propiedad <xref:System.Data.Services.Client.DataServiceQueryContinuation.NextLinkUri%2A>, como en el siguiente ejemplo:  
  
 [!code-csharp[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddataspecific)]
 [!code-vb[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddataspecific)]  
  
 Los objetos relacionados se cargan de una manera similar. Para obtener más información, vea [Cómo: enlazar datos a elementos de Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md).  
  
## <a name="customizing-data-binding-behaviors"></a>Personalizar comportamientos de enlace de datos  

 La clase <xref:System.Data.Services.Client.DataServiceCollection%601> le permite interceptar los eventos que se provocan al realizar cambios en la colección (como agregar o quitar un objeto) o en las propiedades de objeto en una colección. Puede modificar los eventos de enlace de datos para reemplazar el comportamiento predeterminado, que incluye las siguientes restricciones:  
  
- No se realiza ninguna validación dentro de los delegados.  
  
- Al agregar una entidad, se agregan automáticamente las entidades relacionadas.  
  
- Al eliminar una entidad, no se eliminan las entidades relacionadas.  
  
 Al crear una nueva instancia de <xref:System.Data.Services.Client.DataServiceCollection%601>, tiene la opción de especificar los siguientes parámetros, que definen los delegados para los métodos que administran los eventos provocados cuando se cambian los objetos enlazados:  
  
- `entityChanged`: método al que se llama cuando cambia la propiedad de un objeto enlazado. Este delegado <xref:System.Func%602> acepta un objeto <xref:System.Data.Services.Client.EntityChangedParams> y devuelve un valor booleano que indica si el comportamiento predeterminado, que consiste en llamar a <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> en <xref:System.Data.Services.Client.DataServiceContext>, todavía se debería producir.  
  
- `entityCollectionChanged`: método al que se llama cuando un objeto se agrega o se quita de la colección de enlaces. Este delegado <xref:System.Func%602> acepta un objeto <xref:System.Data.Services.Client.EntityCollectionChangedParams> y devuelve un valor booleano que indica si el comportamiento predeterminado, que consiste en llamar a <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> para una acción <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Add> o a <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> para una acción <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove> en <xref:System.Data.Services.Client.DataServiceContext>, aún se debe producir.  
  
> [!NOTE]
> WCF Data Services no realiza ninguna validación de los comportamientos personalizados que se implementan en estos delegados.  
  
 En el siguiente ejemplo, la acción <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove> está personalizada para llamar al método <xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A> y <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> con el fin de quitar las entidades `Orders_Details` que pertenecen a una entidad `Orders` eliminada. Esta acción personalizada se realiza porque las entidades dependientes no se eliminan automáticamente cuando se elimina la entidad primaria.  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#customersordersdeleterelated)]  
  
 Para obtener más información, vea [Cómo: personalizar comportamientos de enlace de datos](how-to-customize-data-binding-behaviors-wcf-data-services.md).  
  
 El comportamiento predeterminado cuando un objeto se quita de una clase <xref:System.Data.Services.Client.DataServiceCollection%601> utilizando el método <xref:System.Collections.ObjectModel.Collection%601.Remove%2A> es que el objeto también se marca como eliminado en <xref:System.Data.Services.Client.DataServiceContext>. Para cambiar este comportamiento puede especificar un delegado para un método en el parámetro `entityCollectionChanged` al que se llama cuando se produce el evento <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged>.  
  
## <a name="data-binding-with-custom-client-data-classes"></a>Enlazar datos con clases de datos de cliente personalizadas  

 Para poder cargar los objetos en la clase <xref:System.Data.Services.Client.DataServiceCollection%601>, los objetos deben implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>. Las clases de cliente de servicio de datos que se generan cuando se usa el cuadro de diálogo **Agregar referencia de servicio** o la herramienta de [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) implementan esta interfaz. Si proporciona sus propias clases de datos de cliente, debe utilizar otro tipo de colección para el enlace de datos. Cuando los objetos cambian, debe administrar los eventos en los controles enlazados a datos para que llamen a los siguientes métodos de la clase <xref:System.Data.Services.Client.DataServiceContext>:  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>: cuando se agrega un nuevo objeto a la colección.  
  
- <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A>: cuando se elimina un objeto de la colección.  
  
- <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>: cuando se cambia una propiedad en un objeto de la colección.  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>: cuando se agrega un objeto a una colección del objeto relacionado.  
  
- <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A>: cuando se agrega un objeto a una colección de objetos relacionados.  
  
 Para obtener más información, vea [actualizar el servicio de datos](updating-the-data-service-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para generar manualmente clases del servicio de datos cliente](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)
- [Procedimiento para agregar una referencia a un servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md)
