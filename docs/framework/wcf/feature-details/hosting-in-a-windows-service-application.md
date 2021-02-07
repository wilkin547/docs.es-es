---
description: 'Más información sobre: hospedaje en una aplicación de servicio de Windows'
title: Hospedaje en una aplicación de servicios de Windows
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: 702fe95b14b9bce3ffaa774e17a9fc1293717e66
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743127"
---
# <a name="hosting-in-a-windows-service-application"></a>Hospedaje en una aplicación de servicios de Windows

Los servicios de Windows (anteriormente conocidos como servicios de Windows NT) proporcionan un modelo de procesamiento particularmente apropiado para las aplicaciones que deben vivir en una aplicación ejecutable de larga duración y que no deben mostrar ninguna forma de interfaz de usuario. La duración de un proceso de una aplicación de servicios de Windows es administrada mediante el Administrador de control de servicios (SCM) que le permite iniciar, detener y pausar aplicaciones de servicios de Windows. Puede configurar un proceso de servicio de Windows para que se inicie automáticamente cuando se inicie el equipo, convirtiéndolo en un entorno de hospedaje adecuado para aplicaciones "AlwaysOn". Para obtener más información acerca de las aplicaciones de servicios de Windows, vea [aplicaciones de servicios de Windows](https://go.microsoft.com/fwlink/?LinkId=89450).  
  
 Las aplicaciones que hospedan servicios de Windows Communication Foundation de larga duración (WCF) comparten muchas características con los servicios de Windows. En concreto, los servicios WCF son ejecutables de servidor de larga duración que no interactúan directamente con el usuario y, por tanto, no implementan ninguna forma de interfaz de usuario. Como tal, el hospedaje de servicios WCF dentro de una aplicación de servicio de Windows es una opción para compilar aplicaciones WCF sólidas y de larga ejecución.  
  
 A menudo, los desarrolladores de WCF deben decidir si hospedar su aplicación WCF dentro de una aplicación de servicio de Windows o dentro del entorno de hospedaje de Internet Information Services (IIS) o del servicio de activación de procesos de Windows (WAS). Debería considerar el uso de aplicaciones de servicios de Windows bajo las siguientes condiciones:  
  
- Su aplicación requiere la activación explícita. Por ejemplo, debería utilizar los servicios de Windows cuando su aplicación se deba iniciar automáticamente cuando el servidor se inicie en lugar de iniciarse dinámicamente en respuesta al primer mensaje entrante.  
  
- El proceso que hospeda su aplicación debe seguir ejecutándose una vez iniciado. Una vez iniciado, un proceso de servicio de Windows permanece ejecutándose a menos que sea cerrado explícitamente por parte de un administrador del servidor mediante el Administrador de control de servicios. Las aplicaciones hospedadas en IIS o WAS se pueden iniciar y detener dinámicamente para realizar un uso óptimo de los recursos del sistema. Las aplicaciones que requieren el control explícito sobre la duración de su proceso de hospedaje deberían utilizar los servicios de Windows en lugar de IIS o WAS.  
  
- El servicio WCF debe ejecutarse en Windows Server 2003 y usar transportes que no sean HTTP. En Windows Server 2003, el entorno de hospedaje de IIS 6,0 está restringido únicamente a la comunicación HTTP. Las aplicaciones de servicios de Windows no están sujetas a esta restricción y pueden usar cualquier protocolo de transporte que admita WCF, incluidos net. TCP, net. Pipe y net. MSMQ.  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>Hospedaje de WCF dentro de una aplicación de servicio de Windows  
  
1. Cree una aplicación de servicio de Windows. Puede escribir aplicaciones de servicio de Windows mediante código administrado utilizando las clases del espacio de nombres <xref:System.ServiceProcess>. Esta aplicación debe incluir una clase que herede a partir de <xref:System.ServiceProcess.ServiceBase>.  
  
2. Vincule la duración de los servicios WCF a la duración de la aplicación de servicio de Windows. Normalmente, desea que los servicios WCF hospedados en una aplicación de servicio de Windows se activen cuando se inicie el servicio de hospedaje, dejen de escuchar mensajes cuando se detenga el servicio de hospedaje y cierren el proceso de hospedaje cuando el servicio WCF encuentre un error. Esto se puede lograr de la siguiente manera:  
  
    - Invalide <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> para abrir una o más instancias de <xref:System.ServiceModel.ServiceHost>. Una sola aplicación de servicio de Windows puede hospedar varios servicios WCF que se inician y detienen como un grupo.  
  
    - Invalide <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Closed> en <xref:System.ServiceModel.ServiceHost> todos los servicios WCF en ejecución que se iniciaron durante <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> .  
  
    - Suscríbase al evento <xref:System.ServiceModel.Channels.CommunicationObject.Faulted> de <xref:System.ServiceModel.ServiceHost> y utilice la clase <xref:System.ServiceProcess.ServiceController> para cerrar la aplicación de servicio de Windows en caso de error.  
  
     Las aplicaciones de servicios de Windows que hospedan servicios WCF se implementan y administran de la misma manera que las aplicaciones de servicios de Windows que no usan WCF.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceProcess>
- [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](https://go.microsoft.com/fwlink/?LinkId=94875)
- [Procedimiento para hospedar un servicio WCF en un servicio administrado de Windows](how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Host de servicio de Windows](../samples/windows-service-host.md)
- [Arquitectura de programación de aplicaciones de servicio](https://go.microsoft.com/fwlink/?LinkId=94876)
- [Características de hospedaje de Windows Server AppFabric](/previous-versions/appfabric/ee677189(v=azure.10))
