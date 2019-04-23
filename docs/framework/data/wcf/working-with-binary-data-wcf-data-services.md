---
title: Trabajar con datos binarios (Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, binary data
- WCF Data Services, streams
ms.assetid: aeccc45c-d5c5-4671-ad63-a492ac8043ac
ms.openlocfilehash: de85a3aca629582e79712b71ae2e3413b919ab28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517244"
---
# <a name="working-with-binary-data-wcf-data-services"></a>Trabajar con datos binarios (Data Services de WCF)
El [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] biblioteca de cliente le permite recuperar y actualizar los datos binarios desde un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] la fuente en una de las maneras siguientes:  
  
-   Como una propiedad del tipo primitivo de una entidad. Este es el método recomendado para trabajar con objetos de datos binarios pequeños que se pueden cargar con facilidad en la memoria. En este caso, la propiedad binaria es una propiedad de entidad expuesta por el modelo de datos y el servicio de datos serializa los datos binarios como XML codificado binario de base 64 en el mensaje de respuesta.  
  
-   Como flujo de recursos binarios independiente. Este es el método recomendado para obtener acceso y cambiar datos de objetos binarios grandes (BLOB) que pueden representar una foto, un vídeo o cualquier otro tipo de datos codificados binarios.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] implementa la transmisión por secuencias de datos binarios mediante HTTP, como se define en el [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. En este mecanismo, datos binarios se tratan como un recurso multimedia independiente pero relacionados con una entidad, que se denomina una entrada de vínculo multimedia. Para obtener más información, consulte [proveedor de transmisión](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).  
  
> [!TIP]
>  Para obtener un ejemplo paso a paso de cómo crear una aplicación de cliente de Windows Presentation Foundation (WPF) que descarga los archivos de imagen binarios un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] service que almacene fotos, vea la entrada [datos de servicios de Streaming proveedor serie partes 2: Acceso a un Stream de recursos multimedia desde el cliente](https://go.microsoft.com/fwlink/?LinkId=201637). Para descargar el código de ejemplo para el servicio de datos de photo stream destacado en la entrada de blog, vea la [ejemplo de servicio de datos de fotografía de transmisión por secuencias](https://go.microsoft.com/fwlink/?LinkId=198988) en MSDN Code Gallery.  
  
## <a name="entity-metadata"></a>Metadatos de entidad  
 Una entidad que tenga un flujo de recursos multimedia relacionado se indica en los metadatos del servicio de datos mediante el atributo `HasStream` aplicado a un tipo de entidad que sea la entrada de vínculo multimedia. En el ejemplo siguiente, la `PhotoInfo` entidad es una entrada de vínculo multimedia que tiene un recurso multimedia relacionado, indicado por el `HasStream` atributo.  
  
 [!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_photo_streaming_service/xml/photodata.edmx#hasstream)]  
  
 En el resto de los ejemplos de este tema se muestra cómo acceder y cambiar el flujo de recursos multimedia. Para obtener un ejemplo completo de cómo consumir un flujo de recursos multimedia en una aplicación de cliente de .NET Framework mediante la [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] biblioteca de cliente, consulte la publicación [acceso a un Stream de recursos multimedia desde el cliente](https://go.microsoft.com/fwlink/?LinkID=201637).  
  
## <a name="accessing-the-binary-resource-stream"></a>Acceder al flujo de recursos binarios  
 La biblioteca cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] proporciona métodos para acceder a flujos de recursos binarios desde un servicio de datos basado en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Cuando se descarga un recurso multimedia, puede usar el URI de dicho recurso u obtener un flujo binario que contenga los datos del propio recurso multimedia. También puede cargar los datos del recurso multimedia como flujo binario.  
  
> [!TIP]
>  Para obtener un ejemplo paso a paso de cómo crear una aplicación de cliente de Windows Presentation Foundation (WPF) que descarga los archivos de imagen binarios un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] service que almacene fotos, vea la entrada [datos de servicios de Streaming proveedor serie partes 2: Acceso a un Stream de recursos multimedia desde el cliente](https://go.microsoft.com/fwlink/?LinkId=201637). Para descargar el código de ejemplo para el servicio de datos de photo stream destacado en la entrada de blog, vea la [ejemplo de servicio de datos de fotografía de transmisión por secuencias](https://go.microsoft.com/fwlink/?LinkId=198988) en MSDN Code Gallery.  
  
### <a name="getting-the-uri-of-the-binary-stream"></a>Obtener el URI del flujo binario  
 Cuando se recuperan ciertos tipos de recursos multimedia, como imágenes y otros archivos multimedia, suele ser más fácil usar el URI del recurso multimedia de la aplicación que administrar el propio flujo de datos binarios. Para obtener el URI de un flujo de recursos asociado con una entrada de vínculo multimedia determinada, debe llamar al método <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A> de la instancia de la clase <xref:System.Data.Services.Client.DataServiceContext> que esté realizando el seguimiento de la entidad. En el ejemplo siguiente se muestra cómo llamar al método <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A> para obtener el URI de un flujo de recursos multimedia que se use con el fin de crear una nueva imagen en el cliente:  
  
 [!code-csharp[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_client/cs/photowindow.xaml.cs#getreadstreamuri)]
 [!code-vb[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_client/vb/photowindow.xaml.vb#getreadstreamuri)]  
  
### <a name="downloading-the-binary-resource-stream"></a>Descargar el flujo de recursos binarios  
 Al recuperar un flujo de recursos multimedia, es necesario llamar al método <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> de la instancia de la clase <xref:System.Data.Services.Client.DataServiceContext> que esté realizando el seguimiento de la entrada de vínculo multimedia. Este método envía una solicitud al servicio de datos que devuelve un objeto <xref:System.Data.Services.Client.DataServiceStreamResponse>, que tiene una referencia al flujo que contiene el recurso. Use este método cuando la aplicación necesite el recurso binario como clase <xref:System.IO.Stream>. En el ejemplo siguiente se muestra cómo llamar al método <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> para recuperar un flujo que se use con el fin de crear una nueva imagen en el cliente:  
  
 [!code-csharp[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_streaming_client/cs/customerphotowindow.xaml.cs#getreadstreamclient)]
 [!code-vb[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_streaming_client/vb/customerphotowindow.xaml.vb#getreadstreamclient)]  
  
> [!NOTE]
>  El servicio de datos no establece el encabezado de longitud de contenido del mensaje de respuesta que contiene el flujo binario. Este valor puede no reflejar la longitud real del flujo de datos binarios.  
  
### <a name="uploading-a-media-resource-as-a-stream"></a>Cargar un recurso multimedia como flujo  
 Para insertar o actualizar un recurso multimedia, llame al método <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> de la instancia de la clase <xref:System.Data.Services.Client.DataServiceContext> que esté realizando el seguimiento de la entidad. Este método envía una solicitud al servicio de datos que contiene el recurso multimedia leído desde el flujo proporcionado. En el siguiente ejemplo se muestra cómo llamar al método <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> para enviar una imagen al servicio de datos:  
  
 [!code-csharp[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_client/cs/photodetailswindow.xaml.cs#setsavestream)]
 [!code-vb[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_client/vb/photodetailswindow.xaml.vb#setsavestream)]  
  
 En este ejemplo, se llama al método <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> proporcionando un valor `true` para el parámetro `closeStream`. De esta forma, se garantiza que la clase <xref:System.Data.Services.Client.DataServiceContext> cierre el flujo una vez cargados los datos binarios en el servicio de datos.  
  
> [!NOTE]
>  Cuando llame al método <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>, el flujo no se envía al servicio de datos hasta que se llame al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Enlace de datos a los controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)
