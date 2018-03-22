---
title: Desarrollar e implementar WCF Data Services
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8abe23aebefadc68268aa1dada8474336b1f87e7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="developing-and-deploying-wcf-data-services"></a>Desarrollar e implementar WCF Data Services
En este tema se proporciona información sobre el desarrollo y la implementación de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Para obtener más información básica sobre [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], consulte [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md) y [Introducción](../../../../docs/framework/data/wcf/wcf-data-services-overview.md).  
  
## <a name="developing-wcf-data-services"></a>Desarrollar el servicio de datos de WCF  
 Cuando use [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para crear un servicio de datos que admita [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], debe realizar las siguientes tareas básicas durante el desarrollo:  
  
1.  **Definir el modelo de datos**  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] admite distintos proveedores de servicios de datos que le permiten definir un modelo de datos basado en los datos de diferentes orígenes de datos, desde bases de datos relacionales hasta tipos de datos enlazados en tiempo de ejecución. Para obtener más información, consulte [proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
2.  **Crear el servicio de datos**  
  
     El servicio de datos más básico expone una clase que hereda de la clase <xref:System.Data.Services.DataService%601> , con un tipo `T` que es el nombre completo del espacio de nombres del contenedor de la entidad. Para obtener más información, consulta [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Configurar el servicio de datos**  
  
     De forma predeterminada, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] deshabilita el acceso a los recursos que expone un contenedor de entidades. La clase <xref:System.Data.Services.DataServiceConfiguration> le permite configurar el acceso a los recursos y a las operaciones del servicio, especificar la versión admitida de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], así como definir otros comportamientos de todo el servicio, como los comportamientos de los procesamientos por lotes o el número máximo de entidades que pueden devolverse en una única fuente de respuesta. Para obtener más información, consulte [configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 En este tema se describe principalmente el desarrollo y la implementación de los servicios de datos mediante el uso de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Para obtener más información sobre la flexibilidad proporcionada por [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para exponer los datos como fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] , consulte [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
### <a name="choosing-a-development-web-server"></a>Elegir un servidor web de desarrollo  
 Cuando desarrolle un servicio de datos de WCF como aplicación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o un sitio web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] mediante el uso de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], dispone de una selección de servidores web en los que ejecutar el servicio de datos durante el desarrollo. Los siguientes servidores web se integran con [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] para facilitar la prueba y depuración de los servicios de datos en el equipo local.  
  
1.  **Servidor IIS local**  
  
     Cuando cree un servicio de datos que sea una aplicación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o un sitio web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que se ejecute en Internet Information Services (IIS), se recomienda que desarrolle y pruebe el servicio de datos con IIS en el equipo local. Si se ejecuta el servicio de datos en IIS, se facilita el seguimiento de las solicitudes HTTP durante el proceso de depuración. De esta forma, puede predeterminar los derechos necesarios que requiere IIS para obtener acceso a los archivos, a las bases de datos y al resto de los recursos que necesita el servicio de datos. Para ejecutar el servicio de datos en IIS, debe asegurarse de que tanto IIS como [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] estén instalados y configurados correctamente, así como de conceder acceso a las cuentas de IIS en las bases de datos y en el sistema de archivos. Para obtener más información, consulta [Cómo: Desarrollar un servicio de datos WCF que se ejecuta en IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
    > [!NOTE]
    >  Debe ejecutar [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] con derechos de administrador para habilitar el entorno de desarrollo con el fin de configurar el servidor IIS local.  
  
2.  **Servidor de desarrollo de Visual Studio**  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] incluye un servidor web integrado, el servidor de desarrollo de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] , que es el servidor web predeterminado de los proyectos de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] . Este servidor web está diseñado para ejecutar proyectos de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] en el equipo local durante el desarrollo. El [Tutorial rápido del servicio de datos de WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) muestra cómo crear un servicio de datos que se ejecute en el servidor de desarrollo de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] .  
  
     Debe tener en cuenta las siguientes limitaciones cuando use el servidor de desarrollo de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] para desarrollar el servicio de datos:  
  
    -   A este servidor solo se puede acceder desde el equipo local.  
  
    -   Este servidor escucha en `localhost` y en un puerto específico, no en el puerto 80, que es el puerto predeterminado para los mensajes HTTP. Para obtener más información, vea [Servidores web en Visual Studio para proyectos web ASP.NET](http://msdn.microsoft.com/library/31d4f588-df59-4b7e-b9ea-e1f2dd204328).  
  
    -   Este servidor ejecuta el servicio de datos en el contexto de su cuenta de usuario actual. Por ejemplo, si está ejecutando como usuario de nivel de administrador, un servicio de datos que se ejecute en el servidor de desarrollo de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] tendrá privilegios de nivel de administrador. De esta forma, el servicio de datos puede acceder a los recursos para los que no tiene derechos de acceso cuando se implementa en un servidor IIS.  
  
    -   Este servidor no incluye las características adicionales de IIS, como la autenticación.  
  
    -   Este servidor no puede administrar los flujos HTTP fragmentados, que envía de forma predeterminada el cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] cuando se accede a los datos binarios grandes desde el servicio de datos. Para obtener más información, consulte [proveedor de transmisión por secuencias](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).  
  
    -   Este servidor experimenta problemas al procesar el carácter de punto (`.`) en una dirección URL, aunque este carácter lo admita [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] en valores clave.  
  
    > [!TIP]
    >  Aunque puede usar el servidor de desarrollo de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] para probar los servicios de datos durante el desarrollo, debe probarlos de nuevo después de implementarlos en un servidor web que ejecute IIS.  
  
3.  **Entorno de desarrollo de Microsoft Azure**  
  
     Microsoft Azure Tools para [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] incluye un conjunto integrado de herramientas para desarrollar los servicios de Microsoft Azure en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Con estas herramientas, puede desarrollar un servicio de datos que se puede implementar en Microsoft Azure y que puede probar en el equipo local antes de su implementación. Use estas herramientas cuando use [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] para desarrollar un servicio de datos que se ejecute en la plataforma Microsoft Azure. Puede descargar Microsoft Azure Tools para [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] del [Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkID=201848). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo desarrollar un servicio de datos que se ejecute en Microsoft Azure, consulte la publicación [Deploying an OData Service in Microsoft Azure (Implementación de un servicio de OData en Microsoft Azure)](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="development-tips"></a>Sugerencias de desarrollo  
 Debe plantearse lo siguiente cuando desarrolle un servicio de datos:  
  
-   Determine los requisitos de seguridad del servicio de datos, si planea autenticar a los usuarios o restringir el acceso de usuarios específicos. Para obtener más información, consulta [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
-   Un programa de inspección HTTP puede ser muy útil cuando se depure un servicio de datos, ya que permite inspeccionar el contenido de los mensajes de solicitud y respuesta. Cualquier analizador de paquetes de red que pueda mostrar paquetes sin procesar se puede usar para inspeccionar las solicitudes HTTP al servicio de datos y las respuestas.  
  
-   Cuando depure un servicio de datos, quizá desee obtener más información sobre un error desde el servicio de datos que durante el funcionamiento normal. Puede obtener información adicional sobre el error del servicio de datos si establece la propiedad <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> de <xref:System.Data.Services.DataServiceConfiguration> en `true` y la propiedad <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> del atributo <xref:System.ServiceModel.Description.ServiceDebugBehavior> de la clase de servicio de datos en `true`. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] la publicación [Debugging WCF Data Services (Depuración de WCF Data Services)](http://go.microsoft.com/fwlink/?LinkId=201868). También puede habilitar la traza en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para ver las excepciones producidas en la capa de mensajería HTTP. Para obtener más información, consulta [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
-   Se suele desarrollar un servicio de datos como proyecto de aplicación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , pero también puede crear el servicio de datos como proyecto de sitio web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Para obtener información sobre las diferencias entre los dos tipos de proyectos, vea [NIB: Web Application Projects versus Web Site Projects en Visual Studio](http://msdn.microsoft.com/library/2861815e-f5a2-4378-a2f8-b8a86dc012f5).  
  
-   Cuando cree un servicio de datos mediante el uso del cuadro de diálogo **Agregar nuevo elemento** de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hospeda el servicio de datos en IIS. Mientras que [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e IIS sean el host predeterminado para un servicio de datos, se admiten opciones de hospedaje adicionales. Para obtener más información, consulte [aloja el servicio de datos](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md).  
  
## <a name="deploying-wcf-data-services"></a>Implementar WCF Data Services  
 El servicio de datos de WCF proporciona flexibilidad al elegir el proceso que hospede el servicio de datos. Puede usar [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] para implementar un servicio de datos en las siguientes plataformas:  
  
-   **Servidor web hospedado en IIS**  
  
     Cuando un servicio de datos se desarrolla como un proyecto [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , se puede implementar en un servidor web de IIS usando los procesos de implementación estándar de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] proporciona las siguientes tecnologías de implementación para [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], dependiendo del tipo de proyecto [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que hospede el servicio de datos que está implementando.  
  
    -   **Tecnologías de implementación para aplicaciones web ASP.NET**  
  
        -   [Paquete de implementación Web](http://msdn.microsoft.com/library/1f9713c8-9540-494c-b80d-9893b970ad6f)  
  
        -   [Publicación de un solo clic](http://msdn.microsoft.com/library/59226246-99ad-4aec-975d-7c61e8a8911c)  
  
    -   **Tecnologías de implementación para sitios web ASP.NET**  
  
        -   [Herramienta Copiar sitio web](http://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)  
  
        -   [Herramienta Publicar sitio web](http://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)  
  
        -   [XCopy](http://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Opciones de la implementación de un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicación, consulte [Web Deployment Overview para Visual Studio y ASP.NET](http://msdn.microsoft.com/library/99bd1927-b59f-4e02-87b4-55c6ba2adbc3).  
  
    > [!TIP]
    >  Antes de intentar implementar el servicio de datos en IIS, asegúrese de haber probado la implementación en un servidor web que esté ejecutando IIS. Para obtener más información, consulta [Cómo: Desarrollar un servicio de datos WCF que se ejecuta en IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
-   **Windows Azure**  
  
     Puede implementar un servicio de datos en Microsoft Azure con Microsoft Azure Tools para [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Puede descargar Microsoft Azure Tools para [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] del [Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkID=201848). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] la implementación de un servicio de datos en Microsoft Azure, consulte la publicación [Deploying an OData Service in Microsoft Azure (Implementación de un servicio de OData en Microsoft Azure)](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="deployment-considerations"></a>Consideraciones de implementación  
 Debe plantearse lo siguiente cuando implemente un servicio de datos:  
  
-   Al implementar un servicio de datos que usa el proveedor de [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] para tener acceso a una base de datos de SQL Server, también podría tener que propagar estructuras de datos, datos o ambos con su implementación del servicio de datos. [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] puede crear automáticamente scripts (archivos .sql) para hacer esto en la base de datos de destino y estos scripts se pueden incluir en el paquete de implementación web de una aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] . Para obtener más información, consulte [NIB: Cómo: implementar una base de datos con un proyecto de aplicación Web](http://msdn.microsoft.com/library/683b33f1-8a3d-45cf-af6e-61ab50fc518b). En un sitio web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , puede hacer esto con el **Asistente para publicar bases de datos** en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Para obtener más información, consulta [implementar una base de datos mediante el Asistente para publicación de base de datos](http://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7).  
  
-   Dado que [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] incluye una implementación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] básica, puede usar Windows Server AppFabric para supervisar un servicio de datos implementado en IIS que se ejecuta en Windows Server. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] el uso de la supervisión de un servicio de datos con Windows Server AppFabric, consulte la publicación [Tracking WCF Data Services with Windows Server AppFabric (Seguimiento de WCF Data Services con Windows Server AppFabric)](http://go.microsoft.com/fwlink/?LinkID=202005).  
  
## <a name="see-also"></a>Vea también  
 [Hospedaje del servicio de datos](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 [Protección de WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
