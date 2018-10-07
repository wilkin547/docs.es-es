---
title: Hospedaje en Servicio de activación de procesos de Windows
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], WAS
ms.assetid: d2b9d226-15b7-41fc-8c9a-cb651ac20ecd
ms.openlocfilehash: d51cd3bcef44c32c24630c1a3a332b2144a41469
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839435"
---
# <a name="hosting-in-windows-process-activation-service"></a>Hospedaje en Servicio de activación de procesos de Windows
El servicio de activación de procesos de Windows (WAS) administra la activación y duración de los procesos de trabajo que contienen aplicaciones que hospedar servicios de Windows Communication Foundation (WCF). El modelo de procesamiento WAS generaliza el modelo de procesamiento [!INCLUDE[iis601](../../../../includes/iis601-md.md)] para el servidor HTTP quitando la dependencia en HTTP. Esto permite a los servicios WCF usar HTTP y protocolos no HTTP, tales como Net.TCP, en un entorno de hospedaje que admite la activación basada en mensajes y ofrece la posibilidad de hospedar un gran número de aplicaciones en un equipo determinado.  
  
 Para obtener más información sobre la creación de un servicio WCF que se ejecuta en el entorno de hospedaje de WAS, vea [Cómo: hospedar un servicio WCF en WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
 El modelo de procesamiento WAS proporciona varias características que permiten hospedar aplicaciones de una manera más robusta, administrable y que utiliza eficazmente los recursos:  
  
-   La activación basada en mensaje de aplicaciones y aplicaciones de procesos de trabajo se inicia y detiene dinámicamente en respuesta a los elementos de trabajo de entrada que llegan utilizando protocolos de red HTTP y no HTTP.  
  
-   Una robusta aplicación y reciclaje de procesos de trabajo para mantener el estado de las aplicaciones que se están ejecutando.  
  
-   Configuración y administración centralizada de aplicaciones.  
  
-   Permite a las aplicaciones beneficiarse del modelo de procesamiento de IIS sin necesitar la superficie de implementación de una instalación de IIS completa.  
  
 Para obtener más información acerca de las características de WAS, vea [IIS 7.0 Beta: administración de Web de IIS 7.0](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
 [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496) funciona con [!INCLUDE[iisver](../../../../includes/iisver-md.md)] y el servicio de activación de proceso Windows (WAS) para proporcionar un entorno para servicios NET4 WCF y WF de hospedaje de aplicaciones enriquecido. Estas ventajas incluyen la administración del ciclo de vida de los procesos, el reciclaje de procesos, el hospedaje compartido, la protección rápida ante los errores, los procesos huérfanos, la activación a petición y la supervisión del estado de mantenimiento. Para obtener información detallada, consulte [AppFabric Hosting Features](https://go.microsoft.com/fwlink/?LinkId=196494) y [conceptos de hospedaje de AppFabric](https://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="elements-of-the-was-addressing-model"></a>Elementos del modelo de direccionamiento de WAS  
 Las aplicaciones tienen direcciones de Identificador uniforme de recursos (URI), que son las unidades del código cuya duración y entorno de ejecución son administrados por el servidor. Una instancia de servidor WAS única puede ser el inicio de muchas aplicaciones diferentes. Organizan los servidores de aplicaciones en grupos llamados *sitios*. Dentro de un sitio, las aplicaciones se organizan de manera jerárquica que refleja la estructura de los URI que sirven como sus direcciones externas.  
  
 Las direcciones de las aplicaciones tienen dos partes: un prefijo de URI base y una dirección relativa específica de la aplicación (ruta), que proporcionan la dirección externa para una aplicación cuando se unen. El prefijo de URI base se construye desde el enlace del sitio y se utiliza para todas las aplicaciones bajo el sitio. Direcciones de la aplicación, a continuación, se construyen tomando fragmentos de ruta de acceso específica de la aplicación (por ejemplo, "/ /applicationone") y anexándolos al prefijo URI base (por ejemplo, "NET. TCP://localhost") para llegar a la aplicación completa de URI.  
  
 La siguiente tabla muestra varios escenarios de direccionamiento posibles para sitios WAS con enlaces de sitio HTTP y que no sean HTTP.  
  
|Escenario|Enlaces de sitio|Ruta de acceso de la aplicación|URI base de aplicación|  
|--------------|-------------------|----------------------|---------------------------|  
|Solo HTTP|http: *: 80:\*|/appTwo|http://localhost/appTwo/|  
|HTTP y que no sea HTTP|http: *: 80:\*<br /><br /> NET.TCP: 808:\*|/appTwo|http://localhost/appTwo/<br />net.tcp://localhost/appTwo/|  
|Solo no HTTP|net.pipe: *|/appThree|net.pipe://appThree/|  
  
 Los servicios y recursos dentro de una aplicación también se pueden direccionar. Dentro de una aplicación, los recursos de la aplicación se direccionan en relación a la ruta de acceso base de la aplicación. Por ejemplo, suponga que un sitio con un nombre de equipo contoso.com tiene enlaces del sitio para los protocolos HTTP y Net.TCP. Suponga también que el sitio contiene una aplicación ubicada en /Billing (facturación), que expone un servicio en GetOrders.svc. A continuación, si el servicio GetOrders.svc expuso un punto de conexión con una dirección relativa de SecureEndpoint, el punto de conexión de servicio se expondría en los dos URI siguientes:  
  
- `http://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
- `net.tcp://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
  
## <a name="the-was-runtime"></a>El tiempo de ejecución de WAS  
 Las aplicaciones se organizan en sitios para propósitos de direccionamiento y administración. En tiempo de ejecución, las aplicaciones también se agrupan en grupos de aplicaciones. Un grupo de aplicaciones puede alojar muchas aplicaciones diferentes desde muchos sitios diferentes. Todas las aplicaciones dentro de un grupo de aplicaciones comparten un conjunto común de características de tiempo de ejecución. Por ejemplo, todas se ejecutan bajo la misma versión de Common Language Runtime (CLR) y comparten una identidad de proceso común. Cada grupo de aplicaciones corresponde a una instancia de un proceso de trabajo (w3wp.exe). Cada aplicación administrada que se ejecuta dentro de un grupo de aplicaciones compartido se aísla de otras aplicaciones por medio de un AppDomain de CLR.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura de activación de WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)  
 [Configuración de WAS para su uso con WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [Instalación y configuración de los componentes de activación de WFC](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)  
 [Cómo: hospedar un servicio WCF en WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)  
 [Características de hospedaje de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201276)
