---
title: Desarrollar e implementar WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: 1dc9f3d261738a6dff0339c094c7aba5e32680ee
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200059"
---
# <a name="develop-and-deploy-wcf-data-services"></a>Desarrolle e implemente WCF Data Services

En este artículo se proporciona información sobre el desarrollo y la implementación de WCF Data Services. Para obtener más información básica sobre WCF Data Services, consulte [Introducción](getting-started-with-wcf-data-services.md) e [información general](wcf-data-services-overview.md).

## <a name="develop-wcf-data-services"></a>Desarrollar WCF Data Services

Al usar WCF Data Services para crear un servicio de datos que admita el Open Data Protocol (OData), debe realizar las siguientes tareas básicas durante el desarrollo:

1. **Definir el modelo de datos**

     WCF Data Services admite una variedad de proveedores de servicios de datos que permiten definir un modelo de datos basado en los datos de una variedad de orígenes de datos, desde bases de datos relacionales hasta tipos de datos enlazados en tiempo de ejecución. Para obtener más información, vea [proveedores de Data Services](data-services-providers-wcf-data-services.md).

2. **Crear el servicio de datos**

     El servicio de datos más básico expone una clase que hereda de la clase <xref:System.Data.Services.DataService%601> , con un tipo `T` que es el nombre completo del espacio de nombres del contenedor de la entidad. Para obtener más información, consulta [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Configurar el servicio de datos**

     De forma predeterminada, WCF Data Services deshabilita el acceso a los recursos expuestos por un contenedor de entidades. La <xref:System.Data.Services.DataServiceConfiguration> interfaz le permite configurar el acceso a los recursos y las operaciones de servicio, especificar la versión admitida de oData y definir otros comportamientos de todo el servicio, como los comportamientos de procesamiento por lotes o el número máximo de entidades que se pueden devolver en una única fuente de respuesta. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).

En este artículo se trata principalmente el desarrollo y la implementación de los servicios de datos mediante Visual Studio. Para obtener información sobre la flexibilidad proporcionada por WCF Data Services para exponer los datos como fuentes de OData, consulte [definir WCF Data Services](defining-wcf-data-services.md).

### <a name="choose-a-development-web-server"></a>Elegir un servidor Web de desarrollo

Al desarrollar un servicio de datos de WCF como una aplicación de ASP.NET o un sitio web de ASP.NET mediante Visual Studio 2015, tiene la opción de elegir servidores Web en los que ejecutar el servicio de datos durante el desarrollo. Los siguientes servidores Web se integran con Visual Studio para facilitar la prueba y depuración de los servicios de datos en el equipo local.

1. **Servidor IIS local**

     Al crear un servicio de datos que es una aplicación de ASP.NET o un sitio web de ASP.NET que se ejecuta en Internet Information Services (IIS), se recomienda que desarrolle y pruebe el servicio de datos con IIS en el equipo local. Si se ejecuta el servicio de datos en IIS, se facilita el seguimiento de las solicitudes HTTP durante el proceso de depuración. Esto también le permite predeterminar los derechos necesarios que requiere IIS para obtener acceso a archivos, bases de datos y otros recursos necesarios para el servicio de datos. Para ejecutar el servicio de datos en IIS, asegúrese de que tanto IIS como Windows Communication Foundation (WCF) estén instalados y configurados correctamente y concedan acceso a las cuentas de IIS en el sistema de archivos y las bases de datos. Para obtener más información, consulta [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

    > [!NOTE]
    > Debe ejecutar Visual Studio con derechos de administrador para habilitar el entorno de desarrollo con el fin de configurar el servidor IIS local.

2. **Servidor de desarrollo de Visual Studio**

     Visual Studio incluye un servidor Web integrado, el Servidor de desarrollo de Visual Studio, que es el servidor Web predeterminado para los proyectos de ASP.NET. Este servidor web está diseñado para ejecutar proyectos de ASP.NET en el equipo local durante el desarrollo. En la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md) se muestra cómo crear un servicio de datos que se ejecuta en el servidor de desarrollo de Visual Studio.

     Tenga en cuenta las siguientes limitaciones cuando use el Servidor de desarrollo de Visual Studio para desarrollar el servicio de datos:

    - A este servidor solo se puede acceder desde el equipo local.

    - Este servidor escucha en `localhost` y en un puerto específico, no en el puerto 80, que es el puerto predeterminado para los mensajes HTTP. Para obtener más información, vea [Servidores web en Visual Studio para proyectos web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).

    - Este servidor ejecuta el servicio de datos en el contexto de su cuenta de usuario actual. Por ejemplo, si está ejecutando como usuario de nivel de administrador, un servicio de datos que se ejecute en el Servidor de desarrollo de Visual Studio tendrá privilegios de nivel de administrador. De esta forma, el servicio de datos puede acceder a los recursos para los que no tiene derechos de acceso cuando se implementa en un servidor IIS.

    - Este servidor no incluye las características adicionales de IIS, como la autenticación.

    - Este servidor no puede administrar flujos HTTP fragmentados, que el cliente WCF Data Services envía de forma predeterminada al obtener acceso a datos binarios grandes desde el servicio de datos. Para obtener más información, consulte [proveedor de streaming](streaming-provider-wcf-data-services.md).

    - Este servidor tiene problemas para procesar el carácter de`.`punto () en una dirección URL, aunque este carácter es compatible con WCF Data Services en valores de clave.

    > [!TIP]
    > Aunque puede usar el Servidor de desarrollo de Visual Studio para probar los servicios de datos durante el desarrollo, debe probarlos de nuevo después de implementarlos en un servidor Web que ejecute IIS.

3. **Entorno de desarrollo de Azure**

     Azure Tools para Visual Studio incluye un conjunto integrado de herramientas para desarrollar servicios de Azure en Visual Studio. Con estas herramientas, puede desarrollar un servicio de datos que se puede implementar en Azure, y puede probar el servicio de datos en el equipo local antes de la implementación. Use estas herramientas cuando use Visual Studio para desarrollar un servicio de datos que se ejecute en la plataforma Azure. Para obtener información sobre la instalación de las herramientas, vea [Azure Tools para Visual Studio 2015](../../../azure/sdk/vs2015-install.md). Para obtener más información sobre el desarrollo de un servicio de datos que se ejecuta en Azure, consulte la entrada de blog sobre la [implementación de un servicio de oData en Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="development-tips"></a>Sugerencias de desarrollo

Tenga en cuenta lo siguiente cuando desarrolle un servicio de datos:

- Si planea autenticar a los usuarios o restringir el acceso a usuarios específicos, determine los requisitos de seguridad del servicio de datos. Para obtener más información, consulta [Securing WCF Data Services](securing-wcf-data-services.md).

- Un programa de inspección HTTP puede ser útil al depurar un servicio de datos, ya que permite inspeccionar el contenido de los mensajes de solicitud y respuesta. Cualquier analizador de paquetes de red que pueda mostrar paquetes sin procesar se puede usar para inspeccionar las solicitudes HTTP al servicio de datos y las respuestas.

- Al depurar un servicio de datos, puede que desee obtener más información sobre un error del servicio de datos que durante el funcionamiento normal. Puede obtener información adicional sobre el error del servicio de datos si establece la propiedad <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> de <xref:System.Data.Services.DataServiceConfiguration> en `true` y la propiedad <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> del atributo <xref:System.ServiceModel.Description.ServiceDebugBehavior> de la clase de servicio de datos en `true`. Para obtener más información, vea la [WCF Data Services post depuración](https://docs.microsoft.com/archive/blogs/phaniraj/debugging-wcf-data-services). También puede habilitar el seguimiento en WCF para ver las excepciones que se producen en el nivel de mensajería HTTP. Para obtener más información, consulta [Configuring Tracing](../../wcf/diagnostics/tracing/configuring-tracing.md).

- Normalmente, un servicio de datos se desarrolla como un proyecto de aplicación de ASP.NET, pero también puede crear el servicio de datos como un proyecto de sitio web de ASP.NET en Visual Studio. Para obtener información sobre las diferencias entre los dos tipos de proyectos, vea [proyectos de aplicación web frente a proyectos de sitio web en Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd547590(v=vs.110)).

- Cuando se crea un servicio de datos mediante el cuadro de diálogo **Agregar nuevo elemento** de Visual Studio, el servicio de datos se hospeda en ASP.net en IIS. Aunque ASP.NET e IIS es el host predeterminado para un servicio de datos, se admiten otras opciones de hospedaje. Para obtener más información, vea [hospedar el servicio de datos](hosting-the-data-service-wcf-data-services.md).

## <a name="deploy-wcf-data-services"></a>Implementar WCF Data Services

El servicio de datos de WCF proporciona flexibilidad al elegir el proceso que hospede el servicio de datos. Puede usar Visual Studio para implementar un servicio de datos en las siguientes plataformas:

- **Servidor web hospedado en IIS**

    Cuando un servicio de datos se desarrolla como un proyecto de ASP.NET, se puede implementar en un servidor Web de IIS mediante los procesos de implementación estándar de ASP.NET. Visual Studio proporciona las siguientes tecnologías de implementación para ASP.NET, en función del tipo de proyecto ASP.NET que hospede el servicio de datos que va a implementar.

  - **Tecnologías de implementación para aplicaciones web ASP.NET**

    - [Cómo: Crear un paquete de implementación web en Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465323(v=vs.110))

    - [Cómo: implementar un proyecto web mediante publicación con un solo clic en Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))

  - **Tecnologías de implementación para sitios web ASP.NET**

    - [Cómo: copiar archivos de sitio web con la herramienta Copiar sitio web](https://docs.microsoft.com/previous-versions/aspnet/c95809c0(v=vs.100))

    - [Cómo: publicar sitios web](https://docs.microsoft.com/previous-versions/aspnet/20yh9f1b(v=vs.100))

    - [Tutorial: implementar una aplicación Web de ASP.NET con XCOPY](https://docs.microsoft.com/previous-versions/aspnet/f735abw9(v=vs.100))

     Para obtener más información sobre las opciones de implementación de una aplicación de ASP.NET, vea [información general sobre la implementación web para Visual Studio y ASP.net](https://docs.microsoft.com/previous-versions/aspnet/dd394698(v=vs.110)).

    > [!TIP]
    > Antes de intentar implementar el servicio de datos en IIS, asegúrese de haber probado la implementación en un servidor web que esté ejecutando IIS. Para obtener más información, consulta [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

- **Azure**

     Puede implementar un servicio de datos en Azure mediante [Azure Tools para Visual Studio](../../../azure/sdk/vs2015-install.md). Para obtener más información sobre la implementación de un servicio de datos en Azure, consulte [implementación de un servicio de oData en Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="deployment-considerations"></a>Consideraciones de implementación

Tenga en cuenta lo siguiente al implementar un servicio de datos:

- Al implementar un servicio de datos que usa el proveedor de Entity Framework para tener acceso a una base de datos SQL Server, también podría tener que propagar estructuras de datos, datos o ambos con la implementación del servicio de datos. Visual Studio puede crear automáticamente scripts (archivos. SQL) para hacer esto en la base de datos de destino y estos scripts se pueden incluir en el paquete de implementación web de una aplicación ASP.NET. Para obtener más información, vea [Cómo: implementar una base de datos con un proyecto de aplicación web](https://docs.microsoft.com/previous-versions/dd465343(v=vs.100)). Para un sitio web de ASP.NET, puede hacerlo mediante el **Asistente para la publicación de bases de datos** en Visual Studio. Para obtener más información, vea [publicar un SQL Database](https://docs.microsoft.com/previous-versions/aspnet/bb907585(v=vs.100)).

- Dado que WCF Data Services incluye una implementación de WCF básica, puede usar Windows Server AppFabric para supervisar un servicio de datos implementado en IIS que se ejecuta en Windows Server. Para obtener más información acerca del uso de Windows Server AppFabric para supervisar un servicio de datos, consulte el [WCF Data Services de seguimiento posterior con Windows Server AppFabric](https://docs.microsoft.com/archive/blogs/rjacobs/tracking-wcf-data-services-with-windows-server-appfabric).

## <a name="see-also"></a>Consulte también

- [Hospedaje del servicio de datos](hosting-the-data-service-wcf-data-services.md)
- [Proteger WCF Data Services](securing-wcf-data-services.md)
- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
