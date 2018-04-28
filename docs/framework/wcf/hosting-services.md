---
title: Servicios de hospedaje
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8311c558c180de5010850a982dc4cca7576382a3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="hosting-services"></a>Servicios de hospedaje
Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración. Los servicios[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] están diseñados para ejecutarse en cualquier proceso de Windows que admite código administrado.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporciona un modelo de programación unificado para generar aplicaciones orientadas a servicios. Este modelo de programación permanece coherente y es independiente del entorno de tiempo de ejecución en el que se implementa el servicio. En la práctica, esto significa que el código de sus servicios tiene prácticamente el mismo aspecto independientemente de la opción de hospedaje.  
  
 Estas opciones de hospedaje pueden desde ejecutarse dentro de una aplicación de consola hasta entornos de servidor como un servicio de Windows que se ejecuta dentro de un proceso de trabajo administrado por Internet Information Server (IIS) o por Windows Process Activation Service (WAS). Los programadores eligen el entorno de hospedaje que satisface los requisitos de implementación del servicio. Estos requisitos pueden derivarse de la plataforma en la que se implementa la aplicación, del transporte en el que debe enviar y recibir los mensajes, o del tipo de proceso que recicla y otra administración de procesos requerida para garantizar una disponibilidad adecuada, o de alguna otra administración o requisitos de confiabilidad. La siguiente sección proporciona información y orientación sobre las opciones de hospedaje.  
  
## <a name="hosting-options"></a>Opciones de hospedaje  
  
#### <a name="self-hosting-in-a-managed-application"></a>Autohospedaje en una aplicación administrada  
 Los servicios de[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se pueden hospedar en cualquier aplicación administrada. Ésta es la opción más flexible puesto que es la que exige una menor infraestructura para implementar. Usted incrusta el código del servicio dentro del código de la aplicación administrada y, a continuación, crea y abre una instancia del <xref:System.ServiceModel.ServiceHost> para hacer que el servicio esté disponible. Para obtener más información, consulte [Cómo: hospedar un servicio WCF en una aplicación administrada](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Esta opción habilita dos escenarios comunes: [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicios que se ejecutan dentro de las aplicaciones de consola y aplicaciones de cliente completas como las basan en Windows Presentation Foundation (WPF) o Windows Forms (WinForms). Hospedar un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] dentro de una aplicación de consola es útil, por lo general, durante la fase de desarrollo de la aplicación. Esto hace que sean fáciles de depurar, de obtener información de seguimiento para averiguar lo que está sucediendo dentro de la aplicación y fáciles de mover copiándolas en nuevas ubicaciones. Esta opción de hospedaje también facilita la comunicación de aplicaciones de cliente completas, como [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] y aplicaciones Winforms, con el mundo externo. Por ejemplo, un cliente de colaboración punto a punto que utiliza [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] para su interfaz de usuario y también hospeda un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que permite a otros clientes conectar con él y compartir información.  
  
#### <a name="managed-windows-services"></a>Servicios administrados de Windows  
 Esta opción de hospedaje consiste en el registro del dominio de la aplicación (AppDomain) que hospeda un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] como un servicio administrado de Windows (anteriormente conocido como servicio NT) para que el Administrador de control de servicios (SCM) controle la duración del proceso del servicio de los servicios de Windows. Al igual que la opción de autohospedaje, este tipo de entorno de hospedaje requiere que se escriba algún código de hospedaje como parte de la aplicación. El servicio se implementa como un servicio de Windows y como un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] provocando que herede de la clase <xref:System.ServiceProcess.ServiceBase> , así como de una interfaz de contrato de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] . <xref:System.ServiceModel.ServiceHost> se crea y se abre a continuación dentro de un método <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> invalidado y cerrado dentro de un método <xref:System.ServiceProcess.ServiceBase.OnStop> invalidado. Una clase de instalador que hereda de <xref:System.Configuration.Install.Installer> también se debe implementar para permitir que la herramienta Installutl.exe instale el programa como un servicio de Windows. Para obtener más información, consulte [Cómo: hospedar un servicio WCF en un servicio de Windows administrado](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md). El escenario habilitado por la opción de hospedaje del servicio administrado de Windows es el de un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de ejecución prolongada hospedado fuera de IIS en un entorno seguro que no es activado por mensaje. En su lugar, el sistema operativo controla la duración del servicio. Esta opción de hospedaje está disponible en todas las versiones de Windows.  
  
#### <a name="internet-information-services-iis"></a>Internet Information Services (IIS)  
 La opción de alojamiento de IIS se integra con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] y utiliza las características que ofrecen estas tecnologías, como el reciclaje de procesos, cierre por inactividad, supervisión de estado de procesos y activación basada en mensajes. En los sistemas operativos [!INCLUDE[wxp](../../../includes/wxp-md.md)] y [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] , ésta es la solución preferida para hospedar aplicaciones de servicios web que deben estar muy disponibles y ser muy escalables. IIS también proporciona una capacidad de administración integrada que los clientes esperan de un producto de servidor de clase empresarial. Esta opción de hospedaje requiere que se configure correctamente IIS, pero no requiere que se escriba ningún código de hospedaje como parte de la aplicación. [!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo configurar el hospedaje de IIS para un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , consulte [How to: Host a WCF Service in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
 Observe que los servicios hospedados por IIS sólo pueden utilizar transporte HTTP. Su implementación en IIS 5.1 ha introducido algunas limitaciones en [!INCLUDE[wxp](../../../includes/wxp-md.md)]. La activación mediante mensajes proporcionada para un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] por IIS 5.1 en [!INCLUDE[wxp](../../../includes/wxp-md.md)] impide que cualquier otro servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hospedado por sí mismo en el mismo equipo use el puerto 80 para comunicarse. Los servicios de[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] pueden ejecutarse en el mismo dominio de aplicación, grupo de aplicacienes o proceso de trabajo que otras aplicacienes cuando se hospedan en [!INCLUDE[iis601](../../../includes/iis601-md.md)] en [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]. Pero debido a que [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e [!INCLUDE[iis601](../../../includes/iis601-md.md)] usan la pila HTTP de modo de kernel (HTTP.sys), [!INCLUDE[iis601](../../../includes/iis601-md.md)] puede compartir el puerto 80 con otros servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] autohospedados que se ejecuten en el mismo equipo, al contrario que IIS 5.1.  
  
#### <a name="windows-process-activation-service-was"></a>Servicio de activación de procesos de Windows (WAS)  
 Windows Process Activación Servicio (WAS) es el nuevo mecanismo de activación de procesos del [!INCLUDE[lserver](../../../includes/lserver-md.md)] , que también está disponible en [!INCLUDE[wv](../../../includes/wv-md.md)]. Conserva el conocido modelo de proceso de [!INCLUDE[iis601](../../../includes/iis601-md.md)] (grupos de aplicaciones y activación de procesos basada en mensajes) y características de hospedaje (como protección rápida contra errores, supervisión de estado y reciclaje), pero elimina la dependencia de la arquitectura de activación con respecto a HTTP. [!INCLUDE[iisver](../../../includes/iisver-md.md)] usa WAS para lograr la activación mediante mensajes sobre HTTP. Los componentes de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] adicionales también se añaden a WAS para proporcionar la activación mediante mensajes sobre otros protocolos que [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] admite, como TCP, MSMQ y canalizaciones con nombre. Esto permite a las aplicaciones que utilizan protocolos de comunicación utilizar las características de IIS, como el reciclaje de procesos, la protección rápida frente a errores y el sistema de configuración común que sólo estaban disponibles para las aplicaciones basadas en HTTP.  
  
 Esta opción de hospedaje requiere que se configure correctamente WAS, pero no requiere que se escriba ningún código de hospedaje como parte de la aplicación. [!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo configurar el hospedaje de WAS, consulte [How to: Host a WCF Service in WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="choosing-a-hosting-environment"></a>Elección de un entorno de hospedaje  
 La siguiente tabla resume algunos de las ventajas y escenarios clave asociados a cada una de las opciones de hospedaje.  
  
|Entorno de hospedaje|Escenarios comunes|Ventajas y limitaciones clave|  
|-------------------------|----------------------|----------------------------------|  
|Aplicación administrada ("autohospedada")|-Utilizadas durante el desarrollo de aplicaciones de consola.<br />-WinForm enriquecidos y [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] acceso a los servicios de aplicaciones de cliente.|-Flexible.<br />-Fácil de implementar.<br />-No una solución empresarial de servicios.|  
|Windows Services (conocidos anteriormente como servicios NT)|-Una larga duración [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio hospedado fuera de IIS.|-La duración del proceso de Service está controlada por el sistema operativo, no activada por mensaje.<br />-Compatible con todas las versiones de Windows.<br />-Entorno seguro.|  
|IIS 5.1, [!INCLUDE[iis601](../../../includes/iis601-md.md)]|-Ejecutar una [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio en paralelo con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] contenido en Internet mediante el protocolo HTTP.|-El reciclaje de procesos.<br />-Cierre inactivo.<br />-Procesar la supervisión de estado.<br />Activación mediante mensajes.<br />-Sólo HTTP.|  
|Servicio de activación de procesos de Windows (WAS)|-Ejecutar una [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio sin tener que instalar IIS en Internet utilizando varios protocolos de transporte.|: IIS no es necesario.<br />-El reciclaje de procesos.<br />-Cierre inactivo.<br />-Procesar la supervisión de estado.<br />Activación mediante mensajes.<br />-Funciona con HTTP, TCP, canalizaciones con nombre y MSMQ.|  
|IIS 7.0|-Ejecutar una [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] contenido.<br />-Ejecutar una [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio en Internet utilizando varios protocolos de transporte.|-ERA ventajas.<br />-Integrado con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] y el contenido IIS.|  
  
 La opción de un entorno de hospedaje depende de la versión de Windows en la que se implemente, los transportes que requiera para enviar mensajes y el tipo de proceso y reciclaje de dominio de aplicación que requiera. La siguiente tabla resume los datos relacionados con estos requisitos.  
  
|Entorno de hospedaje|Disponibilidad de plataforma|Transportes admitidos|Reciclaje de procesos y AppDomain|  
|-------------------------|---------------------------|--------------------------|-------------------------------------|  
|Aplicaciones administradas ("autohospedadas")|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|  
|Windows Services (conocidos anteriormente como servicios NT)|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|  
|IIS 5,1|[!INCLUDE[wxp](../../../includes/wxp-md.md)]|HTTP|Sí|  
|[!INCLUDE[iis601](../../../includes/iis601-md.md)]|[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]|HTTP|Sí|  
|Servicio de activación de procesos de Windows (WAS)|[!INCLUDE[wv](../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Sí|  
  
 Es importante tener en cuenta que ejecutar un servicio o cualquier extensión desde un host que no sea de confianza pone en peligro la seguridad. Asimismo, tenga en cuenta que al abrir un <xref:System.ServiceModel.ServiceHost> bajo suplantación, una aplicación debe garantizar que el usuario no ha cerrado sesión, por ejemplo mediante el almacenamiento en memoria caché de la <xref:System.Security.Principal.WindowsIdentity> del usuario.  
  
## <a name="see-also"></a>Vea también  
 [Requisitos del sistema](../../../docs/framework/wcf/wcf-system-requirements.md)  
 [Ciclo de vida de programación básica](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md)  
 [Cómo: hospedar un servicio WCF en IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
 [Cómo: hospedar un servicio WCF en WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)  
 [Hospedaje de un servicio WCF en un servicio administrado de Windows](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [Cómo hospedar un servicio WCF en una aplicación administrada](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
