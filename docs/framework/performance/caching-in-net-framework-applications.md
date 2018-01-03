---
title: "Almacenamiento en caché en aplicaciones .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ASP.NET caching
- caching [.NET Framework]
- caching [ASP.NET]
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
caps.latest.revision: "26"
author: tdykstra
ms.author: tdykstra
manager: wpickett
ms.workload: tdykstra
ms.openlocfilehash: d72099543292a89f930135689358b37f87aac44f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="caching-in-net-framework-applications"></a>Almacenamiento en caché en aplicaciones .NET Framework
El almacenamiento en caché permite almacenar datos en memoria para un acceso rápido. Cuando se vuelve a acceder a los datos, las aplicaciones pueden obtenerlos de la memoria caché en lugar de recuperarlos de la fuente original. Esto puede mejorar el rendimiento y la escalabilidad. Además, el almacenamiento en caché permite que los datos estén disponibles cuando el origen de datos no está disponible temporalmente.  
  
 .NET Framework proporciona la funcionalidad de almacenamiento en caché que puede usar para mejorar el rendimiento y la escalabilidad de las aplicaciones de cliente y servidor de Windows, incluido ASP.NET.  
  
> [!NOTE]
>  En [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] y versiones anteriores, ASP.NET proporciona una implementación de caché en memoria en el espacio de nombres <xref:System.Web.Caching>. En versiones anteriores de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], el almacenamiento en caché solo estaba disponible en el espacio de nombres <xref:System.Web> y, por tanto, exigía una dependencia en las clases de ASP.NET. En .NET Framework 4, el espacio de nombres <xref:System.Runtime.Caching> contiene API diseñadas para aplicaciones web y no web.  
  
## <a name="caching-data"></a>Almacenar datos en caché  
 Puede almacenar información en caché mediante clases del espacio de nombres <xref:System.Runtime.Caching>. Las clases de almacenamiento en caché de este espacio de nombres proporcionan las siguientes características:  
  
-   Tipos abstractos que proporcionan la base para crear implementaciones de caché personalizadas.  
  
-   Una implementación de caché de objetos en memoria concreta.  
  
 La clase de almacenamiento en caché base abstracta (<xref:System.Runtime.Caching.ObjectCache>) define las siguientes tareas de almacenamiento en caché:  
  
-   Creación y administración de entradas de caché.  
  
-   Especificación de información de expiración y expulsión.  
  
-   Desencadenamiento de eventos producidos en respuesta a cambios en las entradas de caché.  
  
 La clase <xref:System.Runtime.Caching.MemoryCache> es una implementación de caché de objetos en memoria de la clase <xref:System.Runtime.Caching.ObjectCache>. Puede usar la clase <xref:System.Runtime.Caching.MemoryCache> para la mayoría de las tareas de almacenamiento en caché.  
  
> [!NOTE]
>  La clase <xref:System.Runtime.Caching.MemoryCache> se ha basado en el objeto de caché ASP.NET definido en el espacio de nombres <xref:System.Web.Caching>. Por lo tanto, la lógica interna de almacenamiento en caché es similar a la lógica proporcionada en versiones anteriores de ASP.NET.  
  
 Para obtener un ejemplo de uso del almacenamiento en caché en una aplicación WPF, vea [Walkthrough: Caching Application Data in a WPF Application (Tutorial: almacenamiento en caché de datos de aplicación en una aplicación WPF)](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md).  
  
## <a name="caching-in-aspnet-applications"></a>Almacenamiento en caché de aplicaciones ASP.NET  
 Las clases de almacenamiento en caché del espacio de nombres <xref:System.Runtime.Caching> proporcionan funcionalidad para almacenar en caché datos en ASP.NET.  
  
> [!NOTE]
>  Si el destino de la aplicación es [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] o anterior, debe usar las clases de almacenamiento en caché definidas en el espacio de nombres <xref:System.Web.Caching>. Para más información, vea [Información general sobre el almacenamiento en caché en ASP.NET](http://msdn.microsoft.com/library/5ec28012-4972-4dc3-b3e8-9d20401fe11d).  
  
> [!NOTE]
>  Al desarrollar nuevas aplicaciones, se recomienda usar la clase <xref:System.Runtime.Caching.MemoryCache>. La API proporcionada en el espacio de nombres <xref:System.Runtime.Caching> es como la API que se proporciona en el espacio de nombres <xref:System.Web.Caching.Cache>. Por lo tanto, la API le resultará familiar si ha usado el almacenamiento en caché de versiones anteriores de ASP.NET. Para obtener un ejemplo de uso del almacenamiento en caché en aplicaciones ASP.NET, vea [Tutorial: Almacenar en caché datos de la aplicación en ASP.NET](http://msdn.microsoft.com/library/942236f6-0138-4aaf-af71-a5ea451a1e23).  
  
### <a name="output-caching"></a>Almacenamiento en caché de resultados  
 Para almacenar en caché de forma manual datos de aplicación, puede usar la clase <xref:System.Runtime.Caching.MemoryCache> de ASP.NET. ASP.NET también admite el almacenamiento en caché de resultados, lo que almacena el resultado generado de páginas, controles y respuestas HTTP en memoria. Puede configurar el almacenamiento en caché de resultados de forma declarativa en una página web de ASP.NET o mediante los valores del archivo Web.config. Para más información, vea [Elemento outputCache para el almacenamiento en caché (Esquema de configuración de ASP.NET)](http://msdn.microsoft.com/en-us/47cd2b47-316f-4dfd-bbf8-539be3066fee).  
  
 ASP.NET permite extender el almacenamiento en caché de resultados mediante la creación de proveedores de caché de salida personalizados. Con proveedores personalizados, puede almacenar contenido de la caché con otros dispositivos de almacenamiento, como discos, almacenamiento en la nube y motores de caché distribuida. Para crear un proveedor de caché de salida personalizado, cree una clase que derive de la clase <xref:System.Web.Caching.OutputCacheProvider> y configure la aplicación de modo que use el proveedor de caché de salida personalizado.  
  
## <a name="caching-in-wcf-rest-services"></a>Almacenamiento en caché en servicios WCF REST  
 En los servicios WCF REST, .NET Framework permite aprovechar el almacenamiento en caché de resultados declarativo que está disponible en ASP.NET. Esto permite almacenar en caché las respuestas de las operaciones del servicio WCF REST. Cuando un usuario envía una solicitud HTTP GET a un servicio que está configurado para el almacenamiento en caché, ASP.NET devuelve la respuesta almacenada en caché y no se llama al método del servicio. Cuando la memoria caché expira, la siguiente vez que un usuario envía una solicitud HTTP GET, se llama al método del servicio y la respuesta se vuelve a almacenar en caché.  
  
 .NET Framework también permite implementar almacenamiento en caché condicional de HTTP GET. En escenarios REST, los servicios suelen usar una operación condicional HTTP GET para implementar el almacenamiento en caché inteligente de HTTP descrito en la [especificación HTTP](http://go.microsoft.com/fwlink/?LinkId=165800). Para más información, vea [Caching Support for WCF Web HTTP Services (Compatibilidad del almacenamiento en caché con servicios HTTP web WCF)](http://go.microsoft.com/fwlink/?LinkId=184598).  
  
## <a name="extending-caching-in-the-net-framework"></a>Extender el almacenamiento en caché en .NET Framework  
 El almacenamiento en caché en .NET Framework está diseñado para ser extensible. La clase <xref:System.Runtime.Caching.ObjectCache> permite crear una implementación de caché personalizada. Esta clase proporciona miembros que están disponibles para todas las aplicaciones administradas, como Windows Forms, Windows Presentation Foundation (WPF) y Windows Communications Foundation (WCF). Puede hacer esto para crear una clase de caché que use otro mecanismo de almacenamiento o si quiere un control detallado sobre las operaciones de la caché.  
  
 Para extender el almacenamiento en caché, puede hacer lo siguiente:  
  
-   Cree una clase personalizada que derive de la clase <xref:System.Runtime.Caching.ObjectCache> y luego proporcione una implementación de caché personalizada en la clase derivada.  
  
-   Cree una clase que derive de la clase <xref:System.Runtime.Caching.MemoryCache> y personalice o extienda la clase derivada. Para obtener un ejemplo de cómo hacerlo, vea [Caching Application Data by Using Multiple Cache Objects in an ASP.NET Application (Almacenamiento en caché de datos de aplicación mediante varios objetos de caché en una aplicación ASP.NET)](http://blogs.msdn.com/aspnetue/archive/2010/03/22/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application.aspx).  
  
-   Cree una clase que derive de la clase <xref:System.Web.Caching.OutputCacheProvider> y configure la aplicación de modo que use el proveedor de caché de salida personalizado.  
  
 Para más información, vea la entrada [Extensible Output Caching with ASP.NET 4 (VS 2010 and .NET 4.0 Series) (Almacenamiento en caché de resultados extensible con ASP.NET 4 (VS 2010 y serie .NET 4.0))](http://go.microsoft.com/fwlink/?LinkId=185772) del blog de Scott Guthrie.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.Caching.ObjectCache>  
 <xref:System.Runtime.Caching.MemoryCache>  
 [Tutorial: Almacenar en caché datos de la aplicación en una aplicación WPF](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)  
 [Tutorial: Almacenar en caché datos de la aplicación en ASP.NET](http://msdn.microsoft.com/library/942236f6-0138-4aaf-af71-a5ea451a1e23)
