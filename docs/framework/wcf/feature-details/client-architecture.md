---
description: 'Más información acerca de: arquitectura de cliente'
title: Arquitectura de cliente
ms.date: 03/30/2017
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
ms.openlocfilehash: dc027d5b9d470afe71c577681f42fc2d0b6bef4c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743627"
---
# <a name="client-architecture"></a>Arquitectura de cliente

Las aplicaciones usan objetos de cliente Windows Communication Foundation (WCF) para invocar operaciones de servicio. En este tema se describen los objetos de cliente de WCF, los canales de cliente de WCF y sus relaciones con la arquitectura de canal subyacente. Para obtener información general básica sobre los objetos de cliente de WCF, consulte [información general del cliente de WCF](../wcf-client-overview.md). Para obtener más información acerca de la capa del canal, consulte [extensión de la capa del canal](../extending/extending-the-channel-layer.md).  
  
## <a name="overview"></a>Información general  

 El tiempo de ejecución del modelo de servicio crea clientes de WCF, que se componen de lo siguiente:  
  
- Una implementación del cliente generada automáticamente de un contrato de servicios, que convierte el código de aplicación de las llamadas en mensajes salientes y convierte los mensajes de respuesta en parámetros de salida y devuelve valores que su aplicación puede recuperar.  
  
- Una implementación de una interfaz de control (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>) que agrupa varias interfaces y proporciona el acceso para controlar la funcionalidad, sobre todo la capacidad de cerrar la sesión del cliente y eliminar el canal.  
  
- Un canal de cliente que se crea basado en los valores de configuración especificados por el enlace utilizado.  
  
 Las aplicaciones pueden crear estos clientes a petición, ya sea a través de <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> o mediante la creación de una instancia de una <xref:System.ServiceModel.ClientBase%601> clase derivada tal como la genera la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Estas clases de cliente ya creadas se encapsulan y delegan en una implementación de canal de cliente que se construye de manera dinámica por un <xref:System.ServiceModel.ChannelFactory>. Por consiguiente, el canal de cliente y el generador de canales que los genera son el punto de interés focal para este debate.  
  
## <a name="client-objects-and-client-channels"></a>Objetos cliente y canales de cliente  

 La interfaz base de los clientes de WCF es la <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> interfaz, que expone la funcionalidad del cliente principal, así como la funcionalidad básica del objeto de comunicación de <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType> , la funcionalidad de contexto de <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType> y el comportamiento extensible de <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType> .  
  
 La interfaz <xref:System.ServiceModel.IClientChannel>, sin embargo, no define ningún contrato de servicios. Se declaran mediante la interfaz de contrato de servicio (que normalmente se genera a partir de metadatos de servicio mediante una herramienta como la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)). Los tipos de cliente de WCF extienden <xref:System.ServiceModel.IClientChannel> y la interfaz de contrato de servicio de destino para permitir que las aplicaciones llamen a las operaciones directamente y también tengan acceso a la funcionalidad en tiempo de ejecución del lado cliente. La creación de un cliente WCF proporciona <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> objetos WCF con la información necesaria para crear un tiempo de ejecución que pueda conectarse e interactuar con el punto de conexión de servicio configurado.  
  
 Como se mencionó anteriormente, los dos tipos de cliente de WCF deben configurarse antes de poder usarlos. Los tipos de cliente de WCF más sencillos son los objetos que se derivan de <xref:System.ServiceModel.ClientBase%601> (o <xref:System.ServiceModel.DuplexClientBase%601> si el contrato de servicio es un contrato dúplex). Puede crear estos tipos utilizando un constructor, configurado mediante programación, o mediante un archivo de configuración. Después se llama directamente para invocar las operaciones de servicio. Para obtener información general básica de los <xref:System.ServiceModel.ClientBase%601> objetos, consulte [información general del cliente de WCF](../wcf-client-overview.md).  
  
 El segundo tipo se genera en el tiempo de ejecución desde una llamada al método <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>. Las aplicaciones preocupadas con un control estricto de las características específicas de la comunicación utilizan normalmente este tipo de cliente, denominado *objeto de canal de cliente*, porque permite una interacción más directa que el sistema de canal y el tiempo de ejecución del cliente subyacente.  
  
## <a name="channel-factories"></a>Generadores de canales  

 La clase que es responsable de la creación del tiempo de ejecución subyacente que admite las invocaciones del cliente es la clase <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Tanto los objetos de cliente de WCF como los objetos de canal de cliente de WCF usan un <xref:System.ServiceModel.ChannelFactory%601> objeto para crear instancias; el <xref:System.ServiceModel.ClientBase%601> objeto de cliente derivado encapsula el control del generador de canales, pero para varios escenarios es perfectamente razonable usar el generador de canales directamente. El escenario común para esto es si desea crear repetidamente nuevos canales de cliente a partir de un generador existente. Si está utilizando un objeto de cliente, puede obtener el generador de canales subyacente de un objeto de cliente de WCF llamando a la <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType> propiedad.  
  
 Lo importante que debe recordar sobre los generadores de canales es que crean nuevas instancias de canales de cliente para la configuración proporcionada para ellos antes de llamar a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>. Después de llamar a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (o <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> , <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType> o cualquier operación en un objeto de cliente de WCF), no puede modificar el generador de canales y esperar obtener canales a diferentes instancias de servicio, incluso si simplemente está cambiando la dirección del punto de conexión de destino. Si desea crear un objeto de cliente o un canal de cliente con una configuración diferente, debe crear primero un nuevo generador de canales.  
  
 Para obtener más información acerca de varios problemas con objetos de cliente de WCF y canales de cliente de WCF, consulte [acceso a servicios mediante un cliente WCF](accessing-services-using-a-client.md).  
  
 En las dos secciones siguientes se describe la creación y el uso de objetos de canal de cliente de WCF.  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Creación de un nuevo objeto de canal de cliente WCF  

 Para mostrar el uso de un canal de cliente, suponga que se ha generado el siguiente contrato de servicios.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Para conectar a un servicio `ISampleService`, utilice directamente la interfaz de contrato generada con un generador de canales (<xref:System.ServiceModel.ChannelFactory%601>). Cuando crea y configura un generador de canales para un contrato determinado, puede llamar al método <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> para devolver objetos de canal de cliente que puede utilizar para comunicar con un servicio `ISampleService`.  
  
 Al utilizar la clase <xref:System.ServiceModel.ChannelFactory%601> con una interfaz del contrato de servicios, debe convertirse a la interfaz <xref:System.ServiceModel.IClientChannel> para abrir, cerrar, o anular el canal explícitamente. Para facilitar su funcionamiento, la herramienta Svcutil.exe también genera una interfaz del asistente que implementa la interfaz del contrato de servicio y <xref:System.ServiceModel.IClientChannel> para permitir que usted interactúe con la infraestructura del canal de cliente sin tener que convertirse. El código siguiente muestra la definición de un canal de cliente del asistente que implementa el contrato de servicios anterior.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Creación de un nuevo objeto de canal de cliente WCF  

 Para utilizar un canal de cliente para conectar con un servicio `ISampleService`, utilice directamente la interfaz de contrato generada (o la versión del asistente) con un generador de canales, pasando el tipo de la interfaz de contrato como el parámetro de tipo. Una vez que se haya creado y configurado un generador de canales para un contrato determinado, puede llamar al método <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> para devolver los objetos de canal de cliente que puede utilizar para comunicar con un servicio `ISampleService`.  
  
 Cuando se crea, los objetos de canal de cliente implementan <xref:System.ServiceModel.IClientChannel> y la interfaz de contrato. Por consiguiente, puede utilizarlos directamente para llamar a las operaciones que interactúan con un servicio que admite ese contrato.  
  
 La diferencia entre utilizar los objetos de cliente y los objetos de canal de cliente es básicamente una de control y facilidad de uso para los desarrolladores. Muchos desarrolladores que se sienten cómodos trabajando con clases y objetos preferirán usar el objeto de cliente de WCF en lugar del canal de cliente de WCF.  
  
 Para obtener un ejemplo, consulte [Cómo: usar ChannelFactory](how-to-use-the-channelfactory.md).
