---
title: "Caching in .NET Framework Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ASP.NET caching"
  - "caching [.NET Framework]"
  - "caching [ASP.NET]"
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
caps.latest.revision: 26
author: "tdykstra"
ms.author: "tdykstra"
manager: "wpickett"
caps.handback.revision: 26
---
# Caching in .NET Framework Applications
El almacenamiento en caché permite almacenar los datos en memoria para poder acceder a ellos rápidamente.  Cuando se tiene acceso de nuevo a los datos, las aplicaciones pueden obtener los datos de la memoria caché en lugar de recuperarlos del origen inicial.  Esto puede mejorar el rendimiento y la escalabilidad.  Además, con el almacenamiento en caché, los datos siguen estando disponibles si el origen de datos temporalmente no lo está.  
  
 .NET Framework proporciona funcionalidad de almacenamiento en caché que puede usar para mejorar el rendimiento y la escalabilidad de las aplicaciones cliente y servidor de Windows, incluido ASP.NET.  
  
> [!NOTE]
>  En [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] y en versiones anteriores, ASP.NET proporciona una implementación de caché en memoria en el espacio de nombres <xref:System.Web.Caching>.  En versiones anteriores de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], el almacenamiento en caché solo estaba disponible en el espacio de nombres <xref:System.Web> y, por tanto, necesitaba una dependencia en las clases de ASP.NET.  En .NET Framework 4, el espacio de nombres <xref:System.Runtime.Caching> contiene las API diseñadas tanto para las aplicaciones web como para las no web.  
  
## Almacenar datos en caché  
 Puede almacenar información en caché usando clases del espacio de nombres <xref:System.Runtime.Caching>.  Las clases de almacenamiento en caché de este espacio de nombres proporcionan las características siguientes:  
  
-   Tipos abstractos que proporcionan la base para crear implementaciones personalizadas de caché.  
  
-   Una implementación concreta de la caché de objetos en memoria.  
  
 La clase base abstracta de almacenamiento en caché \(<xref:System.Runtime.Caching.ObjectCache>\) define las tareas de almacenamiento en caché siguientes:  
  
-   Crear y administrar entradas de caché.  
  
-   Especificar la información de expiración y de expulsión.  
  
-   Desencadenar eventos que se generan como respuesta a cambios en las entradas de caché.  
  
 La clase <xref:System.Runtime.Caching.MemoryCache> es una implementación de caché de objetos en memoria de la clase <xref:System.Runtime.Caching.ObjectCache>.  Puede usar la clase <xref:System.Runtime.Caching.MemoryCache> para la mayoría de las tareas de almacenamiento en caché.  
  
> [!NOTE]
>  La clase <xref:System.Runtime.Caching.MemoryCache> se modela sobre el objeto de caché de ASP.NET que se define en el espacio de nombres <xref:System.Web.Caching>.  Por tanto, la lógica interna de almacenamiento en caché es similar a la que se proporcionaba en versiones anteriores de ASP.NET.  
  
 Para obtener un ejemplo de cómo usar el almacenamiento en caché en una aplicación WPF, vea [Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md).  
  
## Almacenamiento en caché en aplicaciones ASP.NET  
 Las clases de almacenamiento en caché del espacio de nombres <xref:System.Runtime.Caching> proporcionan funcionalidad para almacenar en caché datos en ASP.NET.  
  
> [!NOTE]
>  Si su aplicación tiene como destino [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] o una versión anterior, debe usar las clases de almacenamiento en caché que se definen en el espacio de nombres <xref:System.Web.Caching>.  Para obtener más información, vea [ASP.NET Caching Overview](../Topic/ASP.NET%20Caching%20Overview.md).  
  
> [!NOTE]
>  Al desarrollar aplicaciones nuevas, se recomienda usar la clase <xref:System.Runtime.Caching.MemoryCache>.  La API proporcionada en el espacio de nombres <xref:System.Runtime.Caching> es como la API proporcionada en el espacio de nombres <xref:System.Web.Caching.Cache>.  Por tanto, la API le resultará familiar si usó el almacenamiento en caché en versiones anteriores de ASP.NET. Para obtener un ejemplo de cómo usar el almacenamiento en caché en aplicaciones ASP.NET, vea [Walkthrough: Caching Application Data in ASP.NET](../Topic/Walkthrough:%20Caching%20Application%20Data%20in%20ASP.NET.md).  
  
### Almacenar resultados en la memoria caché  
 Para almacenar en caché manualmente los datos de la aplicación, puede usar la clase <xref:System.Runtime.Caching.MemoryCache> de ASP.NET. ASP.NET también admite el almacenamiento en caché de resultados, que almacena en memoria el resultado generado de las páginas, los controles y las respuestas HTTP.  Puede configurar el almacenamiento en caché de resultados mediante declaración en una página web ASP.NET o usando configuraciones del archivo web.config.  Para obtener más información, vea [Elemento outputCache para el almacenamiento en caché \(Esquema de configuración de ASP.NET\)](http://msdn.microsoft.com/es-es/47cd2b47-316f-4dfd-bbf8-539be3066fee).  
  
 ASP.NET le permite extender almacenamiento en caché de resultados creando proveedores personalizados de caché de resultados.  Al usar proveedores personalizados, puede almacenar el contenido almacenado en caché usando otros dispositivos de almacenamiento como discos, almacenamiento en la nube y motores de caché distribuidos.  Para crear un proveedor personalizado de caché de resultados, debe crear una clase que se derive de la clase <xref:System.Web.Caching.OutputCacheProvider> y configurar la aplicación para que use el proveedor personalizado de caché de resultados.  
  
## Almacenar en caché servicios REST de WCF  
 Para los servicios REST de WCF, .NET Framework permite aprovechar el almacenamiento en caché de resultados declarativo disponible en ASP.NET. Esto le permite almacenar en caché las respuestas de las operaciones de servicios REST de WCF.  Cuando un usuario envía una solicitud GET HTTP a un servicio que está configurado para el almacenamiento en caché, ASP.NET devuelve la respuesta almacenada en caché y no se llama al método del servicio.  Después de que expira la memoria caché, la próxima vez que un usuario envía una solicitud GET HTTP, se llama a su método de servicio y la respuesta se almacena en caché de nuevo.  
  
 .NET Framework también permite implementar el almacenamiento en caché condicional de solicitudes GET HTTP.  En escenarios REST, una solicitud GET HTTP condicional se utiliza los servicios suelen implementar el almacenamiento en caché HTTP inteligente como se describe en [Especificación de HTTP](http://go.microsoft.com/fwlink/?LinkId=165800).  Para obtener más información, vea [Almacenar en memoria caché la compatibilidad para los servicios web HTTP de WCF](http://go.microsoft.com/fwlink/?LinkId=184598).  
  
## Extender el almacenamiento en caché en .NET Framework  
 El almacenamiento en caché de .NET Framework está diseñado para ser extensible.  La clase <xref:System.Runtime.Caching.ObjectCache> le permite crear una implementación personalizada de la memoria caché.  Esta clase proporciona miembros que están disponibles para todas las aplicaciones administradas, incluido Windows Forms, Windows Presentation Foundation \(WPF\) y Windows Communications Foundation \(WCF\).  Puede hacerlo para crear una clase de caché que use otro mecanismo de almacenamiento diferente o si desea tener un control específico sobre las operaciones de caché.  
  
 Para extender el almacenamiento en caché puede hacer lo siguiente:  
  
-   Crear una clase personalizada que se derive de la clase <xref:System.Runtime.Caching.ObjectCache> y, a continuación, proporcionar una implementación personalizada de caché en la clase derivada.  
  
-   Crear una clase que se derive de la clase <xref:System.Runtime.Caching.MemoryCache> y personalizar o extender la clase derivada.  Para obtener un ejemplo de cómo hacerlo, vea [Almacenar en caché datos de la aplicación con los objetos de caché de Varias en una aplicación ASP.NET](http://blogs.msdn.com/aspnetue/archive/2010/03/22/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application.aspx).  
  
-   Crear una clase que se derive de la clase <xref:System.Web.Caching.OutputCacheProvider> y configurar la aplicación para que use el proveedor personalizado de caché de resultados.  
  
 Para obtener más información, vea la [Almacenamiento en caché de resultados extensible con ASP.NET 4 \(VS 2010 y .NET 4,0\)](http://go.microsoft.com/fwlink/?LinkId=185772) entrada del blog de Scott Guthrie.  
  
## Vea también  
 <xref:System.Runtime.Caching.ObjectCache>   
 <xref:System.Runtime.Caching.MemoryCache>   
 [Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)   
 [Walkthrough: Caching Application Data in ASP.NET](../Topic/Walkthrough:%20Caching%20Application%20Data%20in%20ASP.NET.md)