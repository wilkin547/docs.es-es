---
title: Actualizar el servicio de datos (Servicios de datos de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
- WCF Data Services, client library
ms.assetid: 00d993be-ffed-4dea-baf7-6eea982cdb54
ms.openlocfilehash: 42980aa4691d8ecb9868336ecb270c9ad937b5a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876114"
---
# <a name="updating-the-data-service-wcf-data-services"></a>Actualizar el servicio de datos (Servicios de datos de WCF)
Cuando se usa el [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] biblioteca de cliente para consumir un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuente, la biblioteca traduce las entradas de la fuente en instancias de clases de servicio de datos de cliente. La instancia de <xref:System.Data.Services.Client.DataServiceContext> a la que pertenece la instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> realiza el seguimiento de estas clases del servicio de datos. El cliente realiza el seguimiento de los cambios en las entidades que se notifican utilizando métodos de <xref:System.Data.Services.Client.DataServiceContext>. Estos métodos permiten al cliente realizar el seguimiento de las entidades agregadas y eliminadas y también de los cambios que se realizan en los valores de propiedad o en las relaciones entre instancias de entidad. Estos cambios se devuelven al servicio de datos como operaciones basadas en REST al llamar al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
> [!NOTE]
>  Al utilizar una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> para enlazar los datos a los controles, los cambios realizados en los datos del control enlazado se notifican automáticamente a <xref:System.Data.Services.Client.DataServiceContext>. Para obtener más información, consulte [enlazar datos a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
## <a name="adding-modifying-and-changing-entities"></a>Agregar, modificar y cambiar entidades  
 Cuando se usa el **Add Service Reference** cuadro de diálogo de Visual Studio para agregar una referencia a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente, el resultante datos servicio las clases cliente cada tiene estático *Create* método que toma uno parámetro para cada propiedad de entidad que no aceptan valores NULL. Puede usar este método para crear instancias de clases de tipos de entidad, como en el ejemplo siguiente:  
  
 [!code-csharp[Astoria Northwind Client#CreateNewProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#createnewproduct)]
 [!code-vb[Astoria Northwind Client#CreateNewProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#createnewproduct)]  
  
 Para agregar una instancia de entidad, llame al *AddTo* método en el <xref:System.Data.Services.Client.DataServiceContext> clase generada por el **Add Service Reference** cuadro de diálogo, como en el ejemplo siguiente:  
  
 [!code-csharp[Astoria Northwind Client#AddProductSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addproductspecific)]
 [!code-vb[Astoria Northwind Client#AddProductSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addproductspecific)]  
  
 Esto agrega el objeto al contexto y al conjunto de entidades correcto. También puede llamar al método <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>, pero, en ese caso, debe proporcionar el nombre del conjunto de entidades. Si la entidad agregada tiene una o varias relaciones con otras entidades, puede usar el método <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> o bien uno de los métodos anteriores y también definir esos vínculos explícitamente. Estas operaciones se explican más adelante en este tema.  
  
 Para modificar una instancia de una entidad existente, primero ejecute una consulta para esa entidad, efectúe los cambios deseados en sus propiedades y, a continuación, llame al método <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> de la instancia de <xref:System.Data.Services.Client.DataServiceContext> para indicar a la biblioteca cliente que debe enviar una actualización para ese objeto, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[Astoria Northwind Client#ModifyCustomerSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#modifycustomerspecific)]
 [!code-vb[Astoria Northwind Client#ModifyCustomerSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#modifycustomerspecific)]  
  
 Para eliminar una instancia de una entidad, llame al método <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> de la instancia de la clase <xref:System.Data.Services.Client.DataServiceContext>, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[Astoria Northwind Client#DeleteProductSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#deleteproductspecific)]
 [!code-vb[Astoria Northwind Client#DeleteProductSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#deleteproductspecific)]  
  
 Para obtener más información, vea [Cómo: Agregar, modificar y eliminar entidades](../../../../docs/framework/data/wcf/how-to-add-modify-and-delete-entities-wcf-data-services.md).  
  
## <a name="attaching-entities"></a>Adjuntar entidades  
 La biblioteca de clientes le permite guardar las actualizaciones que realizó en una entidad sin ejecutar primero ninguna consulta para cargar la entidad en la instancia de la clase <xref:System.Data.Services.Client.DataServiceContext>. Use el método <xref:System.Data.Services.Client.DataServiceContext.AttachTo%2A> para adjuntar un objeto existente a un conjunto de entidades concreto de la instancia de <xref:System.Data.Services.Client.DataServiceContext>. Después puede modificar el objeto y guardar los cambios en el servicio de datos. En el ejemplo siguiente, se adjunta al contexto un objeto de cliente que se ha cambiado y, a continuación, se llama a <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> para marcar el objeto adjunto como <xref:System.Data.Services.Client.EntityStates.Modified> antes de llamar a <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>:  
  
 [!code-csharp[Astoria Northwind Client#AttachObjectSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobjectspecific)]
 [!code-vb[Astoria Northwind Client#AttachObjectSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobjectspecific)]  
  
 Al asociar objetos deben tenerse en cuenta las consideraciones siguientes:  
  
-   Un objeto se adjunta con el estado <xref:System.Data.Services.Client.EntityStates.Unchanged>.  
  
-   Cuando se adjunta un objeto, no se adjuntan los objetos relacionados con el objeto adjunto.  
  
-   No se puede adjuntar un objeto si el contexto ya está realizando el seguimiento de la entidad.  
  
-   Se usa la sobrecarga del método <xref:System.Data.Services.Client.DataServiceContext.AttachTo%28System.String%2CSystem.Object%2CSystem.String%29> que toma un parámetro `etag` cuando se adjunta un objeto entidad que se recibió junto con un valor de eTag. Este valor de eTag se usa después para comprobar la simultaneidad cuando se guardan los cambios realizados en el objeto adjunto.  
  
 Para obtener más información, vea [Cómo: Asociar una entidad existente a DataServiceContext](../../../../docs/framework/data/wcf/attach-an-existing-entity-to-dc-wcf-data.md).  
  
## <a name="creating-and-modifying-relationship-links"></a>Crear y modificar vínculos de relación  
 Cuando agrega una nueva entidad mediante el uso la <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> adecuado o método *AddTo* método de la <xref:System.Data.Services.Client.DataServiceContext> clase que la **Add Service Reference** genera el cuadro de diálogo, las relaciones entre la nueva entidad y las entidades relacionadas no se definen automáticamente.  
  
 Puede crear y cambiar las relaciones entre las instancias de las entidades y hacer que la biblioteca de cliente refleje esos cambios en el servicio de datos. Las relaciones entre las entidades se definen como asociaciones en el modelo y la clase <xref:System.Data.Services.Client.DataServiceContext> realiza el seguimiento de cada relación como objeto de vínculo en el contexto. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Proporciona los métodos siguientes en el <xref:System.Data.Services.Client.DataServiceContext> clase para crear, modificar y eliminar estos vínculos:  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>|Crea un nuevo vínculo entre dos objetos entidad relacionados. Llamar a este método es equivalente a llamar a los métodos <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> y <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> tanto para crear el nuevo objeto como para definir la relación en un objeto existente.|  
|<xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>|Crea un nuevo vínculo entre dos objetos entidad relacionados.|  
|<xref:System.Data.Services.Client.DataServiceContext.SetLink%2A>|Actualiza un vínculo existente entre dos objetos de entidad relacionados. <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> también se usa para eliminar los vínculos con una cardinalidad de cero o uno a uno (`0..1:1`) y de uno a uno (`1:1`). Para ello, puede establecer el objeto relacionado en `null`.|  
|<xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A>|Marca para su eliminación un vínculo cuyo seguimiento lo está realizando el contexto cuando se llame al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>. Use este método cuando elimine un objeto relacionado o cuando cambie una relación eliminando primero el vínculo a un objeto existente y luego agregando un vínculo al nuevo objeto relacionado.|  
|<xref:System.Data.Services.Client.DataServiceContext.AttachLink%2A>|Notifica al contexto la existencia de un vínculo entre dos objetos entidad. El contexto supone que esta relación ya existe en el servicio de datos y no intenta crear el vínculo cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>. Use este método cuando adjunte objetos a un contexto y también necesite adjuntar el vínculo entre los dos. Si está definiendo una nueva relación, en su lugar debe usar el método <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>.|  
|<xref:System.Data.Services.Client.DataServiceContext.DetachLink%2A>|Deja de realizar el seguimiento del vínculo especificado en el contexto. Este método se usa para eliminar relaciones uno a varios (`*:*`). En vínculos de relación con una cardinalidad de uno, debe usar el método <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> en su lugar.|  
  
 En el ejemplo siguiente se muestra la forma de usar el método <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> para agregar un nuevo `Order_Detail` que se relacione con una entidad `Orders` existente. Dado que el seguimiento del nuevo objeto `Order_Details` lo realiza la clase <xref:System.Data.Services.Client.DataServiceContext>, la relación del objeto `Order_Details` agregado a la entidad `Products` existente se define llamando al método <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>:  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorderspecific)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorderspecific)]  
  
 Mientras que el método <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> definen los vínculos que se deben crear en el servicio de datos, para que estos vínculos se reflejen en los objetos que están en el contexto, también debe establecer las propiedades de navegación en los propios objetos. En el ejemplo anterior, debe establecer las propiedades de navegación de la forma siguiente:  
  
 [!code-csharp[Astoria Northwind Client#SetNavProps](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#setnavprops)]
 [!code-vb[Astoria Northwind Client#SetNavProps](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#setnavprops)]  
  
 Para obtener más información, vea [Cómo: Definir relaciones de entidad](../../../../docs/framework/data/wcf/how-to-define-entity-relationships-wcf-data-services.md).  
  
## <a name="saving-changes"></a>Guardar los cambios  
 El seguimiento de los cambios se realiza en la instancia de la clase <xref:System.Data.Services.Client.DataServiceContext>, pero los cambios no se envían al servidor inmediatamente. Una vez que haya efectuado los cambios necesarios de una actividad determinada, llame al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> para enviar todos los cambios al servicio de datos. Para obtener más información, consulte [administrar el contexto de servicio de datos](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md). También puede guardar cambios de forma asincrónica utilizando los métodos <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A> y <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>. Para obtener más información, consulte [operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
- [Operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)
- [Procesamiento por lotes de operaciones](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)
- [Materialización de objetos](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md)
- [Administración del contexto del servicio de datos](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)
