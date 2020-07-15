---
title: Almacenamiento en caché en aplicaciones .NET Framework
description: Usar el almacenamiento en caché en aplicaciones .NET. Obtenga información sobre el almacenamiento en caché de datos, el almacenamiento en caché en aplicaciones ASP.NET o servicios REST de WCF y la ampliación del almacenamiento en caché en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- ASP.NET caching
- caching [.NET Framework]
- caching [ASP.NET]
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
ms.openlocfilehash: 9b08a07e9b446c2998150a327dccdc8d0481722a
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309773"
---
# <a name="caching-in-net-framework-applications"></a>Almacenamiento en caché en aplicaciones .NET Framework
El almacenamiento en caché permite almacenar datos en memoria para un acceso rápido. Cuando se vuelve a acceder a los datos, las aplicaciones pueden obtenerlos de la memoria caché en lugar de recuperarlos de la fuente original. Esto puede mejorar el rendimiento y la escalabilidad. Además, el almacenamiento en caché permite que los datos estén disponibles cuando el origen de datos no está disponible temporalmente.  
  
 .NET Framework proporciona la funcionalidad de almacenamiento en caché que puede usar para mejorar el rendimiento y la escalabilidad de las aplicaciones de cliente y servidor de Windows, incluido ASP.NET.  
  
> [!NOTE]
> En el .NET Framework 3,5 y versiones anteriores, ASP.NET proporcionó una implementación de caché en memoria en el <xref:System.Web.Caching> espacio de nombres. En versiones anteriores del .NET Framework, el almacenamiento en caché solo estaba disponible en el <xref:System.Web> espacio de nombres y, por tanto, requería una dependencia en las clases ASP.net. En .NET Framework 4, el espacio de nombres <xref:System.Runtime.Caching> contiene API diseñadas para aplicaciones web y no web.  
  
## <a name="caching-data"></a>Almacenar datos en caché  
 Puede almacenar información en caché mediante clases del espacio de nombres <xref:System.Runtime.Caching>. Las clases de almacenamiento en caché de este espacio de nombres proporcionan las siguientes características:  
  
- Tipos abstractos que proporcionan la base para crear implementaciones de caché personalizadas.  
  
- Una implementación de caché de objetos en memoria concreta.  
  
 La clase de almacenamiento en caché base abstracta (<xref:System.Runtime.Caching.ObjectCache>) define las siguientes tareas de almacenamiento en caché:  
  
- Creación y administración de entradas de caché.  
  
- Especificación de información de expiración y expulsión.  
  
- Desencadenamiento de eventos producidos en respuesta a cambios en las entradas de caché.  
  
 La clase <xref:System.Runtime.Caching.MemoryCache> es una implementación de caché de objetos en memoria de la clase <xref:System.Runtime.Caching.ObjectCache>. Puede usar la clase <xref:System.Runtime.Caching.MemoryCache> para la mayoría de las tareas de almacenamiento en caché.  
  
> [!NOTE]
> La clase <xref:System.Runtime.Caching.MemoryCache> se ha basado en el objeto de caché ASP.NET definido en el espacio de nombres <xref:System.Web.Caching>. Por lo tanto, la lógica interna de almacenamiento en caché es similar a la lógica proporcionada en versiones anteriores de ASP.NET.  
  
 Para obtener un ejemplo de uso del almacenamiento en caché en una aplicación WPF, vea [Walkthrough: Caching Application Data in a WPF Application (Tutorial: almacenamiento en caché de datos de aplicación en una aplicación WPF)](../wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md).  
  
## <a name="caching-in-aspnet-applications"></a>Almacenamiento en caché de aplicaciones ASP.NET  
 Las clases de almacenamiento en caché del espacio de nombres <xref:System.Runtime.Caching> proporcionan funcionalidad para almacenar en caché datos en ASP.NET.  
  
> [!NOTE]
> Si su aplicación tiene como destino la .NET Framework 3,5 o anterior, debe usar las clases de almacenamiento en caché que se definen en el <xref:System.Web.Caching> espacio de nombres. Para más información, vea [Información general sobre el almacenamiento en caché en ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).  
  
> [!NOTE]
> Al desarrollar nuevas aplicaciones, se recomienda usar la clase <xref:System.Runtime.Caching.MemoryCache>. La API proporcionada en el espacio de nombres <xref:System.Runtime.Caching> es como la API que se proporciona en el espacio de nombres <xref:System.Web.Caching.Cache>. Por lo tanto, la API le resultará familiar si ha usado el almacenamiento en caché de versiones anteriores de ASP.NET. Para obtener un ejemplo de uso del almacenamiento en caché en aplicaciones ASP.NET, vea [Tutorial: Almacenar en caché datos de la aplicación en ASP.NET](https://docs.microsoft.com/previous-versions/ff477235(v=vs.100)).  
  
### <a name="output-caching"></a>Almacenamiento en caché de resultados  
 Para almacenar en caché de forma manual datos de aplicación, puede usar la clase <xref:System.Runtime.Caching.MemoryCache> de ASP.NET. ASP.NET también admite el almacenamiento en caché de resultados, lo que almacena el resultado generado de páginas, controles y respuestas HTTP en memoria. Puede configurar el almacenamiento en caché de resultados de forma declarativa en una página web de ASP.NET o mediante los valores del archivo Web.config. Para más información, vea [Elemento outputCache para el almacenamiento en caché (Esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms228124(v=vs.100)).  
  
 ASP.NET permite extender el almacenamiento en caché de resultados mediante la creación de proveedores de caché de salida personalizados. Con proveedores personalizados, puede almacenar contenido de la caché con otros dispositivos de almacenamiento, como discos, almacenamiento en la nube y motores de caché distribuida. Para crear un proveedor de caché de salida personalizado, cree una clase que derive de la clase <xref:System.Web.Caching.OutputCacheProvider> y configure la aplicación de modo que use el proveedor de caché de salida personalizado.  
  
## <a name="caching-in-wcf-rest-services"></a>Almacenamiento en caché en servicios WCF REST  
 En los servicios WCF REST, .NET Framework permite aprovechar el almacenamiento en caché de resultados declarativo que está disponible en ASP.NET. Esto permite almacenar en caché las respuestas de las operaciones del servicio WCF REST. Cuando un usuario envía una solicitud HTTP GET a un servicio que está configurado para el almacenamiento en caché, ASP.NET devuelve la respuesta almacenada en caché y no se llama al método del servicio. Cuando la memoria caché expira, la siguiente vez que un usuario envía una solicitud HTTP GET, se llama al método del servicio y la respuesta se vuelve a almacenar en caché.  
  
 .NET Framework también permite implementar almacenamiento en caché condicional de HTTP GET. En escenarios REST, los servicios suelen usar una operación condicional HTTP GET para implementar el almacenamiento en caché inteligente de HTTP descrito en la [especificación HTTP](https://www.w3.org/Protocols/rfc2616/rfc2616.html). Para más información, vea [Caching Support for WCF Web HTTP Services (Compatibilidad del almacenamiento en caché con servicios HTTP web WCF)](../wcf/feature-details/caching-support-for-wcf-web-http-services.md).  
  
## <a name="extending-caching-in-the-net-framework"></a>Extender el almacenamiento en caché en .NET Framework  
 El almacenamiento en caché en .NET Framework está diseñado para ser extensible. La clase <xref:System.Runtime.Caching.ObjectCache> permite crear una implementación de caché personalizada. Esta clase proporciona miembros que están disponibles para todas las aplicaciones administradas, como Windows Forms, Windows Presentation Foundation (WPF) y Windows Communications Foundation (WCF). Puede hacer esto para crear una clase de caché que use otro mecanismo de almacenamiento o si quiere un control detallado sobre las operaciones de la caché.  
  
 Para extender el almacenamiento en caché, puede hacer lo siguiente:  
  
- Cree una clase personalizada que derive de la clase <xref:System.Runtime.Caching.ObjectCache> y luego proporcione una implementación de caché personalizada en la clase derivada.  
  
- Cree una clase que derive de la clase <xref:System.Runtime.Caching.MemoryCache> y personalice o extienda la clase derivada. Para obtener un ejemplo de cómo hacerlo, vea [Caching Application Data by Using Multiple Cache Objects in an ASP.NET Application (Almacenamiento en caché de datos de aplicación mediante varios objetos de caché en una aplicación ASP.NET)](https://docs.microsoft.com/archive/blogs/aspnetue/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application).  
  
- Cree una clase que derive de la clase <xref:System.Web.Caching.OutputCacheProvider> y configure la aplicación de modo que use el proveedor de caché de salida personalizado.  
  
 Para más información, vea la entrada [Extensible Output Caching with ASP.NET 4 (VS 2010 and .NET 4.0 Series) (Almacenamiento en caché de resultados extensible con ASP.NET 4 (VS 2010 y serie .NET 4.0))](https://weblogs.asp.net/scottgu/extensible-output-caching-with-asp-net-4-vs-2010-and-net-4-0-series) del blog de Scott Guthrie.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching.MemoryCache>
- [Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF](../wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
- [Tutorial: Almacenar en caché datos de la aplicación en ASP.NET](https://docs.microsoft.com/previous-versions/ff477235(v=vs.100))
