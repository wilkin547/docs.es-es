---
title: Hospedaje en una aplicación de servicios de Windows
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: 2b3935babec0c7cdc3ffca5dd11d693fdfee7a89
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532564"
---
# <a name="hosting-in-a-windows-service-application"></a>Hospedaje en una aplicación de servicios de Windows
Los servicios de Windows (anteriormente conocidos como servicios de Windows NT) proporcionan un modelo de procesamiento particularmente apropiado para las aplicaciones que deben vivir en una aplicación ejecutable de larga duración y que no deben mostrar ninguna forma de interfaz de usuario. La duración de un proceso de una aplicación de servicios de Windows es administrada mediante el Administrador de control de servicios (SCM) que le permite iniciar, detener y pausar aplicaciones de servicios de Windows. Puede configurar un proceso de servicio de Windows que se inicie automáticamente cuando se inicia el equipo, lo que un entorno de hospedaje adecuado para aplicaciones "siempre activado". Para obtener más información acerca de las aplicaciones de servicio de Windows, consulte [aplicaciones de servicio de Windows](https://go.microsoft.com/fwlink/?LinkId=89450).  
  
 Las aplicaciones que hospedan servicios Windows Communication Foundation (WCF) de ejecución prolongada comparten muchas características con los servicios de Windows. En concreto, los servicios de WCF son los archivos ejecutables de larga ejecución server que no interactúan directamente con el usuario y, por tanto, no implementan ninguna forma de interfaz de usuario. Por lo tanto, hospedaje de servicios WCF dentro de una aplicación de servicio de Windows es una opción para la creación de robustas y de larga ejecución, las aplicaciones de WCF.  
  
 A menudo, los desarrolladores de WCF deben decidir si hospedar su aplicación WCF dentro de una aplicación de servicio de Windows o dentro del entorno de hospedaje de Internet Information Services (IIS) o servicio de activación de proceso de Windows (WAS). Debería considerar el uso de aplicaciones de servicios de Windows bajo las siguientes condiciones:  
  
-   Su aplicación requiere la activación explícita. Por ejemplo, debería utilizar los servicios de Windows cuando su aplicación se deba iniciar automáticamente cuando el servidor se inicie en lugar de iniciarse dinámicamente en respuesta al primer mensaje entrante.  
  
-   El proceso que hospeda su aplicación debe seguir ejecutándose una vez iniciado. Una vez iniciado, un proceso de servicio de Windows permanece ejecutándose a menos que sea cerrado explícitamente por parte de un administrador del servidor mediante el Administrador de control de servicios. Las aplicaciones hospedadas en IIS o WAS se pueden iniciar y detener dinámicamente para realizar un uso óptimo de los recursos del sistema. Las aplicaciones que requieren el control explícito sobre la duración de su proceso de hospedaje deberían utilizar los servicios de Windows en lugar de IIS o WAS.  
  
-   El servicio WCF debe ejecutarse en Windows Server 2003 y usar transportes que no sean HTTP. En Windows Server 2003, el entorno de hospedaje de [!INCLUDE[iis601](../../../../includes/iis601-md.md)] está restringido solo a la comunicación HTTP. Las aplicaciones de servicio de Windows no están sujetos a esta restricción y pueden utilizar cualquier transporte WCF admite, incluyendo net.tcp, net.pipe y net.msmq.  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>Hospedaje de WCF dentro de una aplicación de servicio de Windows  
  
1.  Cree una aplicación de servicio de Windows. Puede escribir aplicaciones de servicio de Windows mediante código administrado utilizando las clases del espacio de nombres <xref:System.ServiceProcess>. Esta aplicación debe incluir una clase que herede a partir de <xref:System.ServiceProcess.ServiceBase>.  
  
2.  Vincule la duración de los servicios WCF para la duración de la aplicación de servicio de Windows. Normalmente, desea que los servicios WCF hospedados en una aplicación de servicio de Windows para activarse cuando se inicia el servicio de hospedaje, dejarán de escuchar los mensajes cuando se detiene el servicio de hospedaje y cierre el proceso de hospedaje cuando el servicio WCF encuentra un error. Esto se puede lograr de la siguiente manera:  
  
    -   Invalide <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> para abrir una o más instancias de <xref:System.ServiceModel.ServiceHost>. Una única aplicación de servicio de Windows puede hospedar varios servicios WCF que inician y detienen como un grupo.  
  
    -   Invalidar <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Closed> en el <xref:System.ServiceModel.ServiceHost> cualquier ejecutar servicios de WCF que se iniciaron durante <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>.  
  
    -   Suscríbase al evento <xref:System.ServiceModel.Channels.CommunicationObject.Faulted> de <xref:System.ServiceModel.ServiceHost> y utilice la clase <xref:System.ServiceProcess.ServiceController> para cerrar la aplicación de servicio de Windows en caso de error.  
  
     Las aplicaciones de servicio de Windows que hospedan servicios WCF se implementan y administran en la misma manera que las aplicaciones de servicio de Windows que no hace usan de WCF.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceProcess>  
 [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](https://go.microsoft.com/fwlink/?LinkId=94875)  
 [Hospedaje de un servicio WCF en un servicio administrado de Windows](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [Host de servicio de Windows](../../../../docs/framework/wcf/samples/windows-service-host.md)  
 [Arquitectura de programación de aplicaciones de servicio](https://go.microsoft.com/fwlink/?LinkId=94876)  
 [Características de hospedaje de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201276)
