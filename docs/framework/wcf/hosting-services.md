---
title: Servicios de hospedaje
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
ms.openlocfilehash: db7ca2690fc7b76d3e843a4ed51ef356890ab9eb
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402403"
---
# <a name="hosting-services"></a>Servicios de hospedaje
Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración. Servicios de Windows Communication Foundation (WCF) están diseñados para ejecutarse en cualquier proceso de Windows que admita código administrado.  
  
 WCF ofrece un modelo de programación unificado para crear aplicaciones orientadas a servicios. Este modelo de programación permanece coherente y es independiente del entorno de tiempo de ejecución en el que se implementa el servicio. En la práctica, esto significa que el código de sus servicios tiene prácticamente el mismo aspecto independientemente de la opción de hospedaje.  
  
 Estas opciones de hospedaje pueden desde ejecutarse dentro de una aplicación de consola hasta entornos de servidor como un servicio de Windows que se ejecuta dentro de un proceso de trabajo administrado por Internet Information Server (IIS) o por Windows Process Activation Service (WAS). Los programadores eligen el entorno de hospedaje que satisface los requisitos de implementación del servicio. Estos requisitos pueden derivarse de la plataforma en la que se implementa la aplicación, del transporte en el que debe enviar y recibir los mensajes, o del tipo de proceso que recicla y otra administración de procesos requerida para garantizar una disponibilidad adecuada, o de alguna otra administración o requisitos de confiabilidad. La siguiente sección proporciona información y orientación sobre las opciones de hospedaje.  
  
## <a name="hosting-options"></a>Opciones de hospedaje  
  
#### <a name="self-hosting-in-a-managed-application"></a>Autohospedaje en una aplicación administrada  
 Servicios WCF pueden hospedarse en cualquier aplicación administrada. Ésta es la opción más flexible puesto que es la que exige una menor infraestructura para implementar. Usted incrusta el código del servicio dentro del código de la aplicación administrada y, a continuación, crea y abre una instancia del <xref:System.ServiceModel.ServiceHost> para hacer que el servicio esté disponible. Para obtener más información, vea [Cómo: Hospedar un servicio WCF en una aplicación administrada](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Esta opción habilita dos escenarios comunes: Servicios WCF que se ejecutan dentro de las aplicaciones de consola y aplicaciones cliente enriquecidas, como las basadas en Windows Presentation Foundation (WPF) o Windows Forms (WinForms). Hospedar un servicio WCF dentro de una aplicación de consola es suele ser útil durante la fase de desarrollo de la aplicación. Esto hace que sean fáciles de depurar, de obtener información de seguimiento para averiguar lo que está sucediendo dentro de la aplicación y fáciles de mover copiándolas en nuevas ubicaciones. Esta opción de hospedaje también facilita a las aplicaciones cliente enriquecidas, como las aplicaciones de WPF y WinForms para comunicarse con el exterior. Por ejemplo, un cliente de colaboración de punto a punto que usa WPF para su interfaz de usuario y también hospeda un servicio WCF que permite a otros clientes para conectarse a él y compartir información.  
  
#### <a name="managed-windows-services"></a>Servicios administrados de Windows  
 Esta opción de hospedaje consiste en registrar el dominio de aplicación (AppDomain) que hospeda un servicio WCF como un servicio administrado de Windows (anteriormente conocido como servicio NT) para que la duración del proceso del servicio se controla mediante el Administrador de control de servicios (SCM) para Servicios de Windows. Al igual que la opción de autohospedaje, este tipo de entorno de hospedaje requiere que se escriba algún código de hospedaje como parte de la aplicación. El servicio se implementa como un servicio de Windows y como un servicio WCF, que hacen que se va a heredar la <xref:System.ServiceProcess.ServiceBase> clase, así como la interfaz de contrato de servicio desde un WCF. <xref:System.ServiceModel.ServiceHost> se crea y se abre a continuación dentro de un método <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> invalidado y cerrado dentro de un método <xref:System.ServiceProcess.ServiceBase.OnStop> invalidado. Una clase de instalador que hereda de <xref:System.Configuration.Install.Installer> también se debe implementar para permitir que la herramienta Installutl.exe instale el programa como un servicio de Windows. Para obtener más información, vea [Cómo: Hospedar un servicio WCF en un servicio de Windows administrado](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md). El escenario habilitado por el servicio de Windows administrado, opción de hospedaje es de un servicio WCF de ejecución prolongada hospedado fuera de IIS en un entorno seguro que no es activado por mensaje. En su lugar, el sistema operativo controla la duración del servicio. Esta opción de hospedaje está disponible en todas las versiones de Windows.  
  
#### <a name="internet-information-services-iis"></a>Internet Information Services (IIS)  
 La opción de hospedaje de IIS se integra con ASP.NET y usa las características que ofrecen estas tecnologías, como proceso reciclaje, cierre por inactividad, supervisión del estado de proceso y la activación basada en mensajes. En los sistemas operativos [!INCLUDE[wxp](../../../includes/wxp-md.md)] y [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] , ésta es la solución preferida para hospedar aplicaciones de servicios web que deben estar muy disponibles y ser muy escalables. IIS también proporciona una capacidad de administración integrada que los clientes esperan de un producto de servidor de clase empresarial. Esta opción de hospedaje requiere que se configure correctamente IIS, pero no requiere que se escriba ningún código de hospedaje como parte de la aplicación. Para obtener más información sobre cómo configurar IIS de hospedaje para un servicio WCF, vea [Cómo: Hospedar un servicio WCF en IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
 Observe que los servicios hospedados por IIS sólo pueden utilizar transporte HTTP. Su implementación en IIS 5.1 ha introducido algunas limitaciones en [!INCLUDE[wxp](../../../includes/wxp-md.md)]. La activación basada en mensajes para un servicio WCF que proporciona IIS 5.1 en [!INCLUDE[wxp](../../../includes/wxp-md.md)] bloquea cualquier otro servicio WCF autohospedado en el mismo equipo desde que se usa el puerto 80 para comunicarse. Pueden ejecutar los servicios WCF en el mismo proceso o grupo de trabajo de AppDomain o aplicación que otras aplicaciones cuando se hospeda en IIS 6.0 en [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]. Pero, dado que WCF e IIS 6.0 usan la pila HTTP de modo kernel (HTTP.sys), IIS 6.0 puede compartir el puerto 80 con otros servicios WCF autohospedados que se ejecutan en el mismo equipo, a diferencia de IIS 5.1.  
  
#### <a name="windows-process-activation-service-was"></a>Servicio de activación de procesos de Windows (WAS)  
 Windows Process Activación Servicio (WAS) es el nuevo mecanismo de activación de procesos del [!INCLUDE[lserver](../../../includes/lserver-md.md)] , que también está disponible en [!INCLUDE[wv](../../../includes/wv-md.md)]. Conserva el familiar modelo de proceso de IIS 6.0 (grupos de aplicaciones y activación de procesos basada en mensajes) y el hospedaje de características (como protección rápida contra errores, seguimiento de estado y reciclaje), pero quita la dependencia de HTTP de la activación arquitectura. [!INCLUDE[iisver](../../../includes/iisver-md.md)] usa WAS para lograr la activación mediante mensajes sobre HTTP. Componentes WCF adicionales también se añaden a WAS para proporcionar la activación basada en mensajes a través de otros protocolos que WCF admite, como TCP, MSMQ y canalizaciones con nombre. Esto permite a las aplicaciones que utilizan protocolos de comunicación utilizar las características de IIS, como el reciclaje de procesos, la protección rápida frente a errores y el sistema de configuración común que sólo estaban disponibles para las aplicaciones basadas en HTTP.  
  
 Esta opción de hospedaje requiere que se configure correctamente WAS, pero no requiere que se escriba ningún código de hospedaje como parte de la aplicación. Para obtener más información sobre cómo configurar el hospedaje de WAS, vea [Cómo: Hospedar un servicio WCF en WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="choosing-a-hosting-environment"></a>Elección de un entorno de hospedaje  
 La siguiente tabla resume algunos de las ventajas y escenarios clave asociados a cada una de las opciones de hospedaje.  
  
|Entorno de hospedaje|Escenarios comunes|Ventajas y limitaciones clave|  
|-------------------------|----------------------|----------------------------------|  
|Aplicación administrada ("autohospedada")|-Utilizadas durante el desarrollo de aplicaciones de consola.<br />-WinForm enriquecidos y las aplicaciones de cliente WPF tienen acceso a servicios.|-   Flexible.<br />-Fácil de implementar.<br />-No una solución empresarial de servicios.|  
|Windows Services (conocidos anteriormente como servicios NT)|-Un servicio WCF de ejecución prolongada hospedado fuera de IIS.|-Duración del proceso de servicio controlado por el sistema operativo, no activado por mensaje.<br />-Compatible con todas las versiones de Windows.<br />-Entorno seguro.|  
|IIS 5.1, IIS 6.0|-Ejecutar un servicio WCF en paralelo con contenido ASP.NET en Internet mediante el protocolo HTTP.|-Reciclaje de procesos.<br />-Apagado inactivo.<br />-Supervisión del estado de proceso.<br />-Basada en mensajes de activación.<br />-Sólo HTTP.|  
|Servicio de activación de procesos de Windows (WAS)|-Ejecutar un servicio WCF sin tener que instalar IIS en Internet utilizando varios protocolos de transporte.|: IIS no es necesario.<br />-Reciclaje de procesos.<br />-Apagado inactivo.<br />-Supervisión del estado de proceso.<br />-Basada en mensajes de activación.<br />-Funciona con HTTP, TCP, canalizaciones con nombre y MSMQ.|  
|IIS 7.0|-Ejecutar un servicio WCF con el contenido ASP.NET.<br />-Ejecutar un servicio WCF en Internet utilizando varios protocolos de transporte.|-ERA ventajas.<br />-Se integra con contenido ASP.NET e IIS.|  
  
 La opción de un entorno de hospedaje depende de la versión de Windows en la que se implemente, los transportes que requiera para enviar mensajes y el tipo de proceso y reciclaje de dominio de aplicación que requiera. La siguiente tabla resume los datos relacionados con estos requisitos.  
  
|Entorno de hospedaje|Disponibilidad de plataforma|Transportes admitidos|Reciclaje de procesos y AppDomain|  
|-------------------------|---------------------------|--------------------------|-------------------------------------|  
|Aplicaciones administradas ("autohospedadas")|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|  
|Windows Services (conocidos anteriormente como servicios NT)|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|  
|IIS 5,1|[!INCLUDE[wxp](../../../includes/wxp-md.md)]|HTTP|Sí|  
|IIS 6,0|[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]|HTTP|Sí|  
|Servicio de activación de procesos de Windows (WAS)|[!INCLUDE[wv](../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Sí|  
  
 Es importante tener en cuenta que ejecutar un servicio o cualquier extensión desde un host que no sea de confianza pone en peligro la seguridad. Asimismo, tenga en cuenta que al abrir un <xref:System.ServiceModel.ServiceHost> bajo suplantación, una aplicación debe garantizar que el usuario no ha cerrado sesión, por ejemplo mediante el almacenamiento en memoria caché de la <xref:System.Security.Principal.WindowsIdentity> del usuario.  
  
## <a name="see-also"></a>Vea también

- [Requisitos del sistema](../../../docs/framework/wcf/wcf-system-requirements.md)
- [Ciclo de vida de programación básica](../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md)
- [Cómo: Hospedar un servicio WCF en IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Cómo: Hospedar un servicio WCF en WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)
- [Cómo: Hospedar un servicio WCF en un servicio administrado de Windows](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Cómo: Hospedar un servicio WCF en una aplicación administrada](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
