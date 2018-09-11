---
title: Desarrollar e implementar WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: cf1782eaf54701f0cf93576325b3d46e8bc4d3f1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271196"
---
# <a name="develop-and-deploy-wcf-data-services"></a>Desarrollar e implementar WCF Data Services

En este tema se proporciona información sobre cómo desarrollar e implementar WCF Data Services. Para obtener más información básica acerca de WCF Data Services, consulte [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md) y [Introducción](../../../../docs/framework/data/wcf/wcf-data-services-overview.md).

## <a name="develop-wcf-data-services"></a>Desarrollar servicios de datos WCF

Cuando usa WCF Data Services para crear un servicio de datos que admite el [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], debe realizar las siguientes tareas básicas durante el desarrollo:

1.  **Definir el modelo de datos**

     WCF Data Services admite una variedad de proveedores de servicios de datos que le permiten definir un modelo de datos según los datos desde una variedad de orígenes de datos, desde bases de datos relacionales para los tipos de datos en tiempo de ejecución. Para obtener más información, consulte [proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).

2.  **Crear el servicio de datos**

     El servicio de datos más básico expone una clase que hereda de la clase <xref:System.Data.Services.DataService%601> , con un tipo `T` que es el nombre completo del espacio de nombres del contenedor de la entidad. Para obtener más información, consulta [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

3.  **Configurar el servicio de datos**

     De forma predeterminada, WCF Data Services deshabilita el acceso a los recursos expuestos por un contenedor de entidades. El <xref:System.Data.Services.DataServiceConfiguration> interfaz le permite configurar el acceso a los recursos y operaciones de servicio, especifique la versión compatible de OData así como definir otros comportamientos de todo el servicio, como el procesamiento por lotes comportamientos o el número máximo de entidades que se pueden devolver en una fuente de respuesta única. Para obtener más información, consulte [configurando el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

En este tema se trata principalmente el desarrollo e implementación de servicios de datos mediante el uso de Visual Studio. Para obtener información sobre la flexibilidad proporcionada por WCF Data Services para exponer los datos como fuentes de OData, consulte [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

### <a name="choose-a-development-web-server"></a>Elija un servidor de desarrollo Web

Al desarrollar un servicio de datos de WCF como una [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicación o [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sitio Web mediante Visual Studio 2015, tendrá la opción de servidores Web en el que se va a ejecutar el servicio de datos durante el desarrollo. Los siguientes servidores Web que se integran con Visual Studio para que sea más fácil probar y depurar los servicios de datos en el equipo local.

1.  **Servidor IIS local**

     Cuando cree un servicio de datos que sea una aplicación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o un sitio web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que se ejecute en Internet Information Services (IIS), se recomienda que desarrolle y pruebe el servicio de datos con IIS en el equipo local. Si se ejecuta el servicio de datos en IIS, se facilita el seguimiento de las solicitudes HTTP durante el proceso de depuración. De esta forma, puede predeterminar los derechos necesarios que requiere IIS para obtener acceso a los archivos, a las bases de datos y al resto de los recursos que necesita el servicio de datos. Para ejecutar el servicio de datos en IIS, debe asegurarse de que IIS y Windows Communication Foundation (WCF) están instalados y configurados correctamente y conceder acceso a las cuentas de IIS en el sistema de archivos y bases de datos. Para obtener más información, consulta [Cómo: Desarrollar un servicio de datos WCF que se ejecuta en IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).

    > [!NOTE]
    > Debe ejecutar Visual Studio con derechos de administrador para habilitar el entorno de desarrollo configurar el servidor IIS local.

2.  **Servidor de desarrollo de Visual Studio**

     Visual Studio incluye un servidor Web integrado, el servidor de desarrollo de Visual Studio, que es el servidor Web predeterminado para [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proyectos. Este servidor web está diseñado para ejecutar proyectos de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] en el equipo local durante el desarrollo. El [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) se muestra cómo crear un servicio de datos que se ejecuta en el servidor de desarrollo de Visual Studio.

     Debe tener en cuenta las siguientes limitaciones cuando se usa el servidor de desarrollo de Visual Studio para desarrollar el servicio de datos:

    -   A este servidor solo se puede acceder desde el equipo local.

    -   Este servidor escucha en `localhost` y en un puerto específico, no en el puerto 80, que es el puerto predeterminado para los mensajes HTTP. Para obtener más información, vea [Servidores web en Visual Studio para proyectos web ASP.NET](https://msdn.microsoft.com/library/31d4f588-df59-4b7e-b9ea-e1f2dd204328).

    -   Este servidor ejecuta el servicio de datos en el contexto de su cuenta de usuario actual. Por ejemplo, si está ejecutando como un usuario de nivel de administrador, un servicio de datos que se ejecutan en el servidor de desarrollo de Visual Studio tendrá privilegios de administrador. De esta forma, el servicio de datos puede acceder a los recursos para los que no tiene derechos de acceso cuando se implementa en un servidor IIS.

    -   Este servidor no incluye las características adicionales de IIS, como la autenticación.

    -   Este servidor no puede controlar secuencias fragmentadas de HTTP, que se envían sea predeterminado por el cliente de WCF Data Services al tener acceso a datos binarios grandes desde el servicio de datos. Para obtener más información, consulte [proveedor de transmisión](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).

    -   Este servidor tiene problemas con el período de procesamiento (`.`) de caracteres en una dirección URL, aunque este carácter es compatible con WCF Data Services en los valores de clave.

    > [!TIP]
    > Aunque puede utilizar el servidor de desarrollo de Visual Studio para probar los servicios de datos durante el desarrollo, debe probarlos de nuevo después de implementarlos en un servidor Web que se ejecuta IIS.

3.  **Entorno de desarrollo de Microsoft Azure**

     Windows Azure Tools para Visual Studio incluye un conjunto integrado de herramientas para desarrollar servicios de Windows Azure en Visual Studio. Con estas herramientas, puede desarrollar un servicio de datos que se puede implementar en Microsoft Azure y que puede probar en el equipo local antes de su implementación. Use estas herramientas cuando se usa Visual Studio para desarrollar un servicio de datos que se ejecuta en la plataforma Windows Azure. Puede descargar Windows Azure Tools para Visual Studio desde el [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=201848). Para obtener más información sobre cómo desarrollar un servicio de datos que se ejecuta en Windows Azure, vea la entrada [Deploying an OData Service implementación en Windows Azure](https://go.microsoft.com/fwlink/?LinkId=201847).

### <a name="development-tips"></a>Sugerencias de desarrollo

Debe plantearse lo siguiente cuando desarrolle un servicio de datos:

-   Determine los requisitos de seguridad del servicio de datos, si planea autenticar a los usuarios o restringir el acceso de usuarios específicos. Para obtener más información, consulta [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).

-   Un programa de inspección HTTP puede ser muy útil cuando se depure un servicio de datos, ya que permite inspeccionar el contenido de los mensajes de solicitud y respuesta. Cualquier analizador de paquetes de red que pueda mostrar paquetes sin procesar se puede usar para inspeccionar las solicitudes HTTP al servicio de datos y las respuestas.

-   Cuando depure un servicio de datos, quizá desee obtener más información sobre un error desde el servicio de datos que durante el funcionamiento normal. Puede obtener información adicional sobre el error del servicio de datos si establece la propiedad <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> de <xref:System.Data.Services.DataServiceConfiguration> en `true` y la propiedad <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> del atributo <xref:System.ServiceModel.Description.ServiceDebugBehavior> de la clase de servicio de datos en `true`. Para obtener más información, vea la entrada [depurar WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=201868). También puede habilitar el seguimiento de WCF para ver las excepciones producidas en la capa de mensajería HTTP. Para obtener más información, consulta [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).

-   Normalmente, se desarrolla un servicio de datos como un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proyecto de aplicación, pero también puede crear el servicio de datos como un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proyecto de sitio Web en Visual Studio. Para obtener información sobre las diferencias entre los dos tipos de proyectos, vea [NIB: Web Application Projects versus Web Site proyectos en Visual Studio](https://msdn.microsoft.com/library/2861815e-f5a2-4378-a2f8-b8a86dc012f5).

-   Cuando crea un servicio de datos mediante el **Agregar nuevo elemento** cuadro de diálogo en Visual Studio, el servicio de datos está hospedada en [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] en IIS. Mientras que [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e IIS sean el host predeterminado para un servicio de datos, se admiten opciones de hospedaje adicionales. Para obtener más información, consulte [hospeda el servicio de datos](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md).

## <a name="deploy-wcf-data-services"></a>Implementar servicios de datos WCF

El servicio de datos de WCF proporciona flexibilidad al elegir el proceso que hospede el servicio de datos. Puede usar Visual Studio para implementar un servicio de datos en las siguientes plataformas:

-   **Servidor web hospedado en IIS**

     Cuando un servicio de datos se desarrolla como un proyecto [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , se puede implementar en un servidor web de IIS usando los procesos de implementación estándar de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .  Visual Studio proporciona las siguientes tecnologías de implementación para [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], según el tipo de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proyecto que hospeda el servicio de datos que se va a implementar.

    -   **Tecnologías de implementación para aplicaciones web ASP.NET**

        -   [Paquete de implementación Web](https://msdn.microsoft.com/library/1f9713c8-9540-494c-b80d-9893b970ad6f)

        -   [Publicación con un clic](https://msdn.microsoft.com/library/59226246-99ad-4aec-975d-7c61e8a8911c)

    -   **Tecnologías de implementación para sitios web ASP.NET**

        -   [Herramienta Copiar sitio Web](https://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)

        -   [Herramienta Publicar sitio Web](https://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)

        -   [XCopy](https://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)

     Para obtener más información sobre las opciones de implementación para una [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicación, consulte [información general de implementación Web para Visual Studio y ASP.NET](https://msdn.microsoft.com/library/99bd1927-b59f-4e02-87b4-55c6ba2adbc3).

    > [!TIP]
    > Antes de intentar implementar el servicio de datos en IIS, asegúrese de haber probado la implementación en un servidor web que esté ejecutando IIS. Para obtener más información, consulta [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).

-   **Windows Azure**

     Puede implementar un servicio de datos en Windows Azure mediante el uso de Windows Azure Tools para Visual Studio. Puede descargar Windows Azure Tools para Visual Studio desde el [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=201848). Para obtener más información sobre cómo implementar un servicio de datos en Windows Azure, vea la entrada [Deploying an OData Service implementación en Windows Azure](https://go.microsoft.com/fwlink/?LinkId=201847).

### <a name="deployment-considerations"></a>Consideraciones de implementación

Debe plantearse lo siguiente cuando implemente un servicio de datos:

-   Al implementar un servicio de datos que usa el proveedor de [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] para tener acceso a una base de datos de SQL Server, también podría tener que propagar estructuras de datos, datos o ambos con su implementación del servicio de datos. Visual Studio puede crear automáticamente scripts (archivos. SQL) para hacer esto en la base de datos de destino, y estos scripts se pueden incluir en el paquete de implementación Web de un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicación. Para obtener más información, consulte [Cómo: implementar una base de datos con un proyecto de aplicación Web](https://msdn.microsoft.com/library/683b33f1-8a3d-45cf-af6e-61ab50fc518b). Para un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sitio Web, se puede hacer esto con el **Database Publishing Wizard** en Visual Studio. Para obtener más información, consulta [implementar una base de datos mediante el Asistente para publicación de base de datos](https://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7).

-   Dado que WCF Data Services incluye una implementación básica de WCF, puede usar Windows Server AppFabric para supervisar un servicio de datos implementado en IIS que se ejecuta en Windows Server. Para obtener más información sobre el uso de Windows Server AppFabric para supervisar un servicio de datos, vea la entrada [seguimiento WCF Data Services con Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=202005).

## <a name="see-also"></a>Vea también

- [Hospedaje del servicio de datos](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)
- [Protección de WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
