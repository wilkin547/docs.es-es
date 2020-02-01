---
title: Servicios de hospedaje
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
ms.openlocfilehash: 9608f9cc55bbba29686440be529659c6606b0eb8
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921052"
---
# <a name="hosting-services"></a>Servicios de hospedaje

Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración. Los servicios Windows Communication Foundation (WCF) están diseñados para ejecutarse en cualquier proceso de Windows que admita código administrado.

WCF proporciona un modelo de programación unificado para la creación de aplicaciones orientadas a servicios. Este modelo de programación permanece coherente y es independiente del entorno de tiempo de ejecución en el que se implementa el servicio. En la práctica, esto significa que el código de sus servicios tiene prácticamente el mismo aspecto independientemente de la opción de hospedaje.

Estas opciones de hospedaje pueden desde ejecutarse dentro de una aplicación de consola hasta entornos de servidor como un servicio de Windows que se ejecuta dentro de un proceso de trabajo administrado por Internet Information Server (IIS) o por Windows Process Activation Service (WAS). Los programadores eligen el entorno de hospedaje que satisface los requisitos de implementación del servicio. Estos requisitos pueden derivarse de la plataforma en la que se implementa la aplicación, del transporte en el que debe enviar y recibir los mensajes, o del tipo de proceso que recicla y otra administración de procesos requerida para garantizar una disponibilidad adecuada, o de alguna otra administración o requisitos de confiabilidad. La siguiente sección proporciona información y orientación sobre las opciones de hospedaje.

## <a name="hosting-options"></a>Opciones de hospedaje

### <a name="self-host-in-a-managed-application"></a>Autohospedaje en una aplicación administrada
 Los servicios WCF se pueden hospedar en cualquier aplicación administrada. Ésta es la opción más flexible puesto que es la que exige una menor infraestructura para implementar. Usted incrusta el código del servicio dentro del código de la aplicación administrada y, a continuación, crea y abre una instancia del <xref:System.ServiceModel.ServiceHost> para hacer que el servicio esté disponible. Para obtener más información, consulte [Cómo: hospedar un servicio WCF en una aplicación administrada](how-to-host-a-wcf-service-in-a-managed-application.md).

 Esta opción habilita dos escenarios comunes: los servicios WCF que se ejecutan dentro de las aplicaciones de consola y las aplicaciones cliente enriquecidas, como las basadas en Windows Presentation Foundation (WPF) o Windows Forms (WinForms). Hospedar un servicio WCF dentro de una aplicación de consola suele ser útil durante la fase de desarrollo de la aplicación. Esto hace que sean fáciles de depurar, de obtener información de seguimiento para averiguar lo que está sucediendo dentro de la aplicación y fáciles de mover copiándolas en nuevas ubicaciones. Esta opción de hospedaje también facilita que las aplicaciones cliente enriquecidas, como las aplicaciones de WPF y WinForms, se comuniquen con el mundo exterior. Por ejemplo, un cliente de colaboración punto a punto que usa WPF para su interfaz de usuario y también hospeda un servicio WCF que permite a otros clientes conectarse a él y compartir información.

### <a name="managed-windows-services"></a>Servicios administrados de Windows

Esta opción de hospedaje consiste en registrar el dominio de aplicación (AppDomain) que hospeda un servicio WCF como un servicio administrado de Windows (anteriormente conocido como servicio NT) para que la duración del proceso del servicio se controle mediante el administrador de control de servicios (SCM) para Servicios de Windows. Al igual que la opción de autohospedaje, este tipo de entorno de hospedaje requiere que se escriba algún código de hospedaje como parte de la aplicación. El servicio se implementa como un servicio de Windows y como un servicio WCF, lo que hace que herede de la clase <xref:System.ServiceProcess.ServiceBase>, así como de una interfaz de contrato de servicio WCF. <xref:System.ServiceModel.ServiceHost> se crea y se abre a continuación dentro de un método <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> invalidado y cerrado dentro de un método <xref:System.ServiceProcess.ServiceBase.OnStop> invalidado. Una clase de instalador que hereda de <xref:System.Configuration.Install.Installer> también se debe implementar para permitir que la herramienta Installutl.exe instale el programa como un servicio de Windows. Para obtener más información, consulte [Cómo: hospedar un servicio WCF en un servicio administrado de Windows](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md). El escenario habilitado por la opción de hospedaje del servicio administrado de Windows es el de un servicio WCF de ejecución prolongada hospedado fuera de IIS en un entorno seguro que no está activado por mensaje. En su lugar, el sistema operativo controla la duración del servicio. Esta opción de hospedaje está disponible en todas las versiones de Windows.

### <a name="internet-information-services-iis"></a>Internet Information Services (IIS)

La opción de hospedaje de IIS se integra con ASP.NET y utiliza las características que ofrecen estas tecnologías, como el reciclaje de procesos, el cierre por inactividad, la supervisión del estado de los procesos y la activación basada en mensajes. En los sistemas operativos Windows XP y Windows Server 2003, esta es la solución preferida para hospedar aplicaciones de servicios web que deben ser de alta disponibilidad y muy escalables. IIS también proporciona una capacidad de administración integrada que los clientes esperan de un producto de servidor de clase empresarial. Esta opción de hospedaje requiere que se configure correctamente IIS, pero no requiere que se escriba ningún código de hospedaje como parte de la aplicación. Para obtener más información acerca de cómo configurar el hospedaje de IIS para un servicio WCF, consulte [How to: host a WCF Service in IIS](./feature-details/how-to-host-a-wcf-service-in-iis.md).

 Los servicios hospedados en IIS solo pueden usar el transporte HTTP. Su implementación en IIS 5,1 ha introducido algunas limitaciones en Windows XP. La activación basada en mensajes proporcionada para un servicio WCF de IIS 5,1 en Windows XP bloquea cualquier otro servicio WCF autohospedado en el mismo equipo desde el puerto 80 para comunicarse. Los servicios WCF se pueden ejecutar en el mismo AppDomain/grupo de aplicaciones/proceso de trabajo que otras aplicaciones cuando se hospedan en IIS 6,0 en Windows Server 2003. Sin embargo, como WCF e IIS 6,0 usan la pila HTTP de modo kernel (HTTP. sys), IIS 6,0 puede compartir el puerto 80 con otros servicios WCF autohospedados que se ejecutan en el mismo equipo, a diferencia de IIS 5,1.

### <a name="windows-process-activation-service-was"></a>Servicio de activación de procesos de Windows (WAS)

Windows Process Activation Service (WAS) es el nuevo mecanismo de activación de procesos para Windows Server 2008 que también está disponible en Windows Vista. Conserva el conocido modelo de proceso de IIS 6,0 (grupos de aplicaciones y activación de procesos basada en mensajes) y características de hospedaje (como protección rápida contra errores, supervisión de estado y reciclaje), pero elimina la dependencia en HTTP de la activación. arquitectura. IIS 7,0 usa WAS para realizar la activación basada en mensajes a través de HTTP. Los componentes WCF adicionales también se conectan a WAS para proporcionar la activación basada en mensajes sobre los otros protocolos que admite WCF, como TCP, MSMQ y canalizaciones con nombre. Esto permite a las aplicaciones que utilizan protocolos de comunicación utilizar las características de IIS, como el reciclaje de procesos, la protección rápida frente a errores y el sistema de configuración común que sólo estaban disponibles para las aplicaciones basadas en HTTP.

 Esta opción de hospedaje requiere que se configure correctamente WAS, pero no requiere que se escriba ningún código de hospedaje como parte de la aplicación. Para obtener más información acerca de cómo configurar el hospedaje de WAS, consulte [Cómo: hospedar un servicio WCF en was](./feature-details/how-to-host-a-wcf-service-in-was.md).

## <a name="choose-a-hosting-environment"></a>Elegir un entorno de hospedaje
 La siguiente tabla resume algunos de las ventajas y escenarios clave asociados a cada una de las opciones de hospedaje.

|Entorno de hospedaje|Escenarios habituales|Ventajas y limitaciones clave|
|-------------------------|----------------------|----------------------------------|
|Aplicación administrada ("autohospedada")|-Aplicaciones de consola usadas durante el desarrollo.<br />-Aplicaciones cliente enriquecidas de WinForm y WPF que obtienen acceso a los servicios.|Sobrescriba.<br />-Fácil de implementar.<br />-No es una solución empresarial para servicios.|
|Windows Services (conocidos anteriormente como servicios NT)|-Un servicio WCF de ejecución prolongada hospedado fuera de IIS.|-Duración del proceso de servicio controlada por el sistema operativo, no activada por mensajes.<br />-Compatible con todas las versiones de Windows.<br />-Entorno seguro.|
|IIS 5.1, IIS 6.0|-Ejecutar un servicio WCF en paralelo con el contenido de ASP.NET en Internet mediante el protocolo HTTP.|-Reciclaje de procesos.<br />-Apagado inactivo.<br />-Supervisión del estado del proceso.<br />-Activación basada en mensaje.<br />-Solo HTTP.|
|Servicio de activación de procesos de Windows (WAS)|-Ejecutar un servicio WCF sin instalar IIS en Internet mediante varios protocolos de transporte.|-IIS no es necesario.<br />-Reciclaje de procesos.<br />-Apagado inactivo.<br />-Supervisión del estado del proceso.<br />-Activación basada en mensaje.<br />-Funciona con HTTP, TCP, canalizaciones con nombre y MSMQ.|
|IIS 7.0|-Ejecución de un servicio WCF con contenido de ASP.NET.<br />-Ejecutar un servicio WCF en Internet utilizando varios protocolos de transporte.|-Beneficios.<br />-Integrado con el contenido de ASP.NET y IIS.|

 La opción de un entorno de hospedaje depende de la versión de Windows en la que se implemente, los transportes que requiera para enviar mensajes y el tipo de proceso y reciclaje de dominio de aplicación que requiera. La siguiente tabla resume los datos relacionados con estos requisitos.

|Entorno de hospedaje|Disponibilidad de plataforma|Transportes admitidos|Reciclaje de procesos y AppDomain|
|-------------------------|---------------------------|--------------------------|-------------------------------------|
|Aplicaciones administradas ("autohospedadas")|Windows XP, Windows Server 2003, Windows Vista,<br /><br /> Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|
|Windows Services (conocidos anteriormente como servicios NT)|Windows XP, Windows Server 2003, Windows Vista,<br /><br /> Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|
|IIS 5,1|Windows XP|HTTP|Sí|
|IIS 6,0|Windows Server 2003|HTTP|Sí|
|Servicio de activación de procesos de Windows (WAS)|Windows Vista, Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Sí|

 Es importante tener en cuenta que ejecutar un servicio o cualquier extensión desde un host que no sea de confianza pone en peligro la seguridad. Además, al abrir un <xref:System.ServiceModel.ServiceHost> bajo suplantación, una aplicación debe asegurarse de que el usuario no está cerrado, por ejemplo, mediante el almacenamiento en caché del <xref:System.Security.Principal.WindowsIdentity> del usuario.

## <a name="see-also"></a>Vea también

- [Ciclo de vida de programación básica](basic-programming-lifecycle.md)
- [Implementación de contratos de servicio](implementing-service-contracts.md)
- [Cómo: hospedar un servicio WCF en IIS](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Cómo: hospedar un servicio WCF en WAS](./feature-details/how-to-host-a-wcf-service-in-was.md)
- [Hospedaje de un servicio WCF en un servicio administrado de Windows](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Cómo hospedar un servicio WCF en una aplicación administrada](how-to-host-a-wcf-service-in-a-managed-application.md)
