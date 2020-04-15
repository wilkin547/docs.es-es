---
title: Desarrollar e implementar WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: 4591175da5078a194bfe69884701e5432a0c38a3
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389729"
---
# <a name="develop-and-deploy-wcf-data-services"></a>Desarrollar e implementar servicios de datos WCF

En este artículo se proporciona información acerca de cómo desarrollar e implementar servicios de datos de WCFWCF Data Services. Para obtener más información básica acerca de WCF Data Services, vea [Introducción](getting-started-with-wcf-data-services.md) y [información general](wcf-data-services-overview.md).

## <a name="develop-wcf-data-services"></a>Desarrollar servicios de datos WCF

Cuando se usa Servicios de datos de WCFWCF Data Services para crear un servicio de datos que admite el Protocolo de datos abiertos (OData), debe realizar las siguientes tareas básicas durante el desarrollo:

1. **Definir el modelo de datos**

     Servicios de datos de WCFWCF Data Services admite una variedad de proveedores de servicios de datos que permiten definir un modelo de datos basado en datos de una variedad de orígenes de datos, desde bases de datos relacionales a tipos de datos enlazados en tiempo de espera. Para obtener más información, vea [Proveedores](data-services-providers-wcf-data-services.md)de servicios de datos .

2. **Crear el servicio de datos**

     El servicio de datos más básico expone una clase que hereda de la clase <xref:System.Data.Services.DataService%601> , con un tipo `T` que es el nombre completo del espacio de nombres del contenedor de la entidad. Para obtener más información, consulta [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Configurar el servicio de datos**

     De forma predeterminada, Servicios de datos de WCFWCF Data Services deshabilita el acceso a los recursos expuestos por un contenedor de entidades. La <xref:System.Data.Services.DataServiceConfiguration> interfaz le permite configurar el acceso a recursos y operaciones de servicio, especificar la versión compatible de OData y definir otros comportamientos de todo el servicio, como comportamientos de procesamiento por lotes o el número máximo de entidades que se pueden devolver en una sola fuente de respuesta. Para obtener más información, consulte [Configuración del servicio](configuring-the-data-service-wcf-data-services.md)de datos .

En este artículo se describe principalmente el desarrollo y la implementación de servicios de datos mediante Visual Studio. Para obtener información acerca de la flexibilidad proporcionada por Servicios de datos de WCFWCF Data Services para exponer los datos como fuentes de OData, vea Definir servicios de [datos WCF](defining-wcf-data-services.md).

### <a name="choose-a-development-web-server"></a>Elija un servidor web de desarrollo

Al desarrollar un servicio de datos WCF como una aplicación de ASP.NET o ASP.NET sitio Web mediante Visual Studio 2015, tiene una opción de servidores Web en los que ejecutar el servicio de datos durante el desarrollo. Los siguientes servidores Web se integran con Visual Studio para facilitar la prueba y depuración de los servicios de datos en el equipo local.

1. **Servidor IIS local**

     Al crear un servicio de datos que es una aplicación de ASP.NET o ASP.NET sitio Web que se ejecuta en Internet Information Services (IIS), se recomienda desarrollar y probar el servicio de datos mediante IIS en el equipo local. Si se ejecuta el servicio de datos en IIS, se facilita el seguimiento de las solicitudes HTTP durante el proceso de depuración. De esta forma, puede predeterminar los derechos necesarios que requiere IIS para obtener acceso a los archivos, a las bases de datos y al resto de los recursos que necesita el servicio de datos. Para ejecutar el servicio de datos en IIS, asegúrese de que IIS y Windows Communication Foundation (WCF) están instalados y configurados correctamente y conceda acceso a las cuentas de IIS en el sistema de archivos y las bases de datos. Para obtener más información, consulta [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

    > [!NOTE]
    > Debe ejecutar Visual Studio con derechos de administrador para habilitar el entorno de desarrollo para configurar el servidor IIS local.

2. **Servidor de desarrollo de Visual Studio**

     Visual Studio incluye un servidor Web integrado, el servidor de desarrollo de Visual Studio, que es el servidor Web predeterminado para los proyectos de ASP.NET. Este servidor web está diseñado para ejecutar proyectos ASP.NET en el equipo local durante el desarrollo. El inicio rápido de Servicios de datos de [WCFWCF Data Services](quickstart-wcf-data-services.md) muestra cómo crear un servicio de datos que se ejecuta en el servidor de desarrollo de Visual Studio.

     Debe tener en cuenta las siguientes limitaciones al usar el servidor de desarrollo de Visual Studio para desarrollar el servicio de datos:

    - A este servidor solo se puede acceder desde el equipo local.

    - Este servidor escucha en `localhost` y en un puerto específico, no en el puerto 80, que es el puerto predeterminado para los mensajes HTTP. Para obtener más información, vea [Servidores web en Visual Studio para proyectos web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).

    - Este servidor ejecuta el servicio de datos en el contexto de su cuenta de usuario actual. Por ejemplo, si se ejecuta como un usuario de nivel de administrador, un servicio de datos que se ejecuta en el servidor de desarrollo de Visual Studio tendrá privilegios de nivel de administrador. De esta forma, el servicio de datos puede acceder a los recursos para los que no tiene derechos de acceso cuando se implementa en un servidor IIS.

    - Este servidor no incluye las características adicionales de IIS, como la autenticación.

    - Este servidor no puede controlar secuencias HTTP fragmentadas, que son enviadas de forma predeterminada por el cliente de Servicios de datos de WCFWCF Data Services al tener acceso a datos binarios grandes desde el servicio de datos. Para obtener más información, consulte [Proveedor de streaming](streaming-provider-wcf-data-services.md).

    - Este servidor tiene problemas con`.`el procesamiento del carácter de punto ( ) en una dirección URL, aunque este carácter es compatible con WCF Data Services en valores de clave.

    > [!TIP]
    > Aunque puede usar el servidor de desarrollo de Visual Studio para probar los servicios de datos durante el desarrollo, debe probarlos de nuevo después de implementarlos en un servidor web que ejecute IIS.

3. **Entorno de desarrollo de Microsoft Azure**

     Herramientas de Windows Azure para Visual Studio incluye un conjunto integrado de herramientas para desarrollar servicios de Windows Azure en Visual Studio. Con estas herramientas, puede desarrollar un servicio de datos que se puede implementar en Microsoft Azure y que puede probar en el equipo local antes de su implementación. Use estas herramientas al usar Visual Studio para desarrollar un servicio de datos que se ejecute en la plataforma Windows Azure. Para obtener información acerca de la instalación de las herramientas, vea Herramientas de [Azure para Visual Studio 2015](../../../azure/sdk/vs2015-install.md). Para obtener más información sobre el desarrollo de un servicio de datos que se ejecuta en Windows Azure, consulte la [publicación Implementación de un servicio OData en Windows Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="development-tips"></a>Sugerencias de desarrollo

Tenga en cuenta lo siguiente al desarrollar un servicio de datos:

- Si planea autenticar usuarios o restringir el acceso para usuarios específicos, determine los requisitos de seguridad del servicio de datos. Para obtener más información, consulta [Securing WCF Data Services](securing-wcf-data-services.md).

- Un programa de inspección HTTP puede ser útil al depurar un servicio de datos al permitirle inspeccionar el contenido de los mensajes de solicitud y respuesta. Cualquier analizador de paquetes de red que pueda mostrar paquetes sin procesar se puede usar para inspeccionar las solicitudes HTTP al servicio de datos y las respuestas.

- Al depurar un servicio de datos, es posible que desee obtener más información sobre un error del servicio de datos que durante la operación normal. Puede obtener información adicional sobre el error del servicio de datos si establece la propiedad <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> de <xref:System.Data.Services.DataServiceConfiguration> en `true` y la propiedad <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> del atributo <xref:System.ServiceModel.Description.ServiceDebugBehavior> de la clase de servicio de datos en `true`. Para obtener más información, vea el post [Depuración de servicios](https://docs.microsoft.com/archive/blogs/phaniraj/debugging-wcf-data-services)de datos WCF . También puede habilitar el seguimiento en WCF para ver las excepciones generadas en la capa de mensajería HTTP. Para obtener más información, consulta [Configuring Tracing](../../wcf/diagnostics/tracing/configuring-tracing.md).

- Normalmente, un servicio de datos se desarrolla como un proyecto de aplicación ASP.NET, pero también puede crear el servicio de datos como un proyecto de sitio Web de ASP.NET en Visual Studio. Para obtener información sobre las diferencias entre los dos tipos de proyectos, vea Proyectos de aplicación web frente a proyectos de [sitio web en Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd547590(v=vs.110)).

- Cuando se crea un servicio de datos mediante el **agregar nuevo elemento** cuadro de diálogo en Visual Studio, el servicio de datos se hospeda en ASP.NET en IIS. Aunque ASP.NET e IIS es el host predeterminado para un servicio de datos, se admiten otras opciones de hospedaje. Para obtener más información, consulte [Hosting the Data Service](hosting-the-data-service-wcf-data-services.md).

## <a name="deploy-wcf-data-services"></a>Implementar servicios de datos WCF

El servicio de datos de WCF proporciona flexibilidad al elegir el proceso que hospede el servicio de datos. Puede usar Visual Studio para implementar un servicio de datos en las siguientes plataformas:

- **Servidor web hospedado en IIS**

    Cuando se desarrolla un servicio de datos como un proyecto de ASP.NET, se puede implementar en un servidor Web IIS mediante los procesos de implementación de ASP.NET estándar.  Visual Studio proporciona las siguientes tecnologías de implementación para ASP.NET, en función del tipo de proyecto ASP.NET que hospeda el servicio de datos que va a implementar.

  - **Tecnologías de implementación para aplicaciones web ASP.NET**

    - [Cómo: Crear un paquete de implementación web en Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465323(v=vs.110))

    - [Cómo: Implementar un proyecto web mediante la publicación con un solo clic en Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))

  - **Tecnologías de implementación para sitios web ASP.NET**

    - [Cómo: Copiar archivos de sitio web con la herramienta Copiar sitio web](https://docs.microsoft.com/previous-versions/aspnet/c95809c0(v=vs.100))

    - [Cómo: Publicar sitios web](https://docs.microsoft.com/previous-versions/aspnet/20yh9f1b(v=vs.100))

    - [Tutorial: Implementación de una aplicación web ASP.NET mediante XCOPY](https://docs.microsoft.com/previous-versions/aspnet/f735abw9(v=vs.100))

     Para obtener más información acerca de las opciones de implementación para una aplicación de ASP.NET, vea Información general sobre la [implementación web para Visual Studio y ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/dd394698(v=vs.110)).

    > [!TIP]
    > Antes de intentar implementar el servicio de datos en IIS, asegúrese de haber probado la implementación en un servidor web que esté ejecutando IIS. Para obtener más información, consulta [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

- **Windows Azure**

     Puede implementar un servicio de datos en Windows Azure mediante Herramientas de Windows Azure para Visual Studio. Puede descargar las Herramientas de Windows Azure para Visual Studio desde el Centro de descarga de [Microsoft](https://go.microsoft.com/fwlink/?LinkID=201848). Para obtener más información acerca de la implementación de un servicio de datos en Windows Azure, consulte la [publicación Implementación de un servicio OData en Windows Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="deployment-considerations"></a>Consideraciones de implementación

Tenga en cuenta lo siguiente al implementar un servicio de datos:

- Al implementar un servicio de datos que usa el proveedor de Entity Framework para tener acceso a una base de datos de SQL Server, es posible que también tenga que propagar estructuras de datos, datos o ambos con la implementación del servicio de datos. Visual Studio puede crear automáticamente scripts (archivos .sql) para hacerlo en la base de datos de destino y estos scripts se pueden incluir en el paquete de implementación web de una aplicación de ASP.NET. Para obtener más información, vea [Cómo: implementar una base](https://docs.microsoft.com/previous-versions/dd465343(v=vs.100))de datos con un proyecto de aplicación web . Para un sitio Web ASP.NET, puede hacerlo mediante el **Asistente para publicación** de bases de datos en Visual Studio. Para obtener más información, vea [Publicación](https://docs.microsoft.com/previous-versions/aspnet/bb907585(v=vs.100))de una base de datos SQL .

- Dado que Servicios de datos de WCFWCF Data Services incluye una implementación básica de WCF, puede usar Windows Server AppFabric para supervisar un servicio de datos implementado en IIS que se ejecuta en Windows Server. Para obtener más información acerca del uso de Windows Server AppFabric para supervisar un servicio de datos, vea la publicación Seguimiento de SERVICIOS de [datos WCF con Windows Server AppFabric](https://docs.microsoft.com/archive/blogs/rjacobs/tracking-wcf-data-services-with-windows-server-appfabric).

## <a name="see-also"></a>Consulte también

- [Hospedaje del servicio de datos](hosting-the-data-service-wcf-data-services.md)
- [Proteger WCF Data Services](securing-wcf-data-services.md)
- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
