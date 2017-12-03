---
title: "Utilización de enlaces para configurar servicios y clientes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF], using
ms.assetid: c39479c3-0766-4a17-ba4c-97a74607f392
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e5290256f302f16f17dd50b570b470beedd00d81
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="using-bindings-to-configure-services-and-clients"></a>Utilización de enlaces para configurar servicios y clientes
Los enlaces son los objetos que especifican los datos de comunicación exigidos para conectar a un punto de conexión. Más específicamente, los enlaces contienen información de configuración utilizada para crear el cliente o servicio en tiempo de ejecución mediante la definición de las características de transportes, formatos de la conexión (codificación de mensajes) y protocolos que se utilizarán en el extremo respectivo o canal de cliente. Para crear un servicio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] en funcionamiento, cada extremo del servicio exige un enlace. Este tema explica qué enlaces son, cómo se definen, y cómo se especifica un enlace determinado para un extremo.  
  
## <a name="what-a-binding-defines"></a>Qué define un enlace  
 La información de un enlace puede ser muy básica o muy compleja. El enlace más básico especifica solo el protocolo de transporte (como HTTP) que se debe utilizar para conectar al extremo. Más generalmente, la información que contiene un enlace sobre cómo conectarse a un extremo queda incluida en una de las categorías de la tabla siguiente.  
  
 Protocolos  
 Determina el mecanismo de seguridad utilizado, función de la mensajería de confianza o configuración de flujo de contexto de transacción.  
  
 Transporte  
 Determina el protocolo de transporte subyacente que se utilizará (por ejemplo, TCP o HTTP).  
  
 Codificación  
 Determina la codificación del mensaje, por ejemplo, texto/XML, binario o Mecanismo de optimización de transmisión del mensaje (MTOM), que determinan cómo se representan los mensajes como secuencias de bytes en la conexión.  
  
## <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye un conjunto de enlaces proporcionados por el sistema que están diseñados para cubrir la mayoría de los requisitos de aplicación y escenarios. Las clases siguientes representan algunos ejemplos de enlaces proporcionados por el sistema:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>: Un enlace de protocolo HTTP conveniente para conectar a los Servicios Web que cumple a la especificación del WS-I Basic Profile 1.1 (por ejemplo, servicios web ASP.NET [ASMX] - servicios basados).  
  
-   <xref:System.ServiceModel.WSHttpBinding>: Un enlace de protocolo HTTP conveniente para conectar a los extremos que cumplen con los protocolos de especificaciones de servicios Web.  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>: Utiliza la codificación binaria .NET y las tecnologías de trama junto con el transporte de canalización con nombre de Windows para conectar a otros extremos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en el mismo equipo.  
  
-   <xref:System.ServiceModel.NetMsmqBinding>: Utiliza la codificación binaria .NET y las tecnologías de trama junto con el Message Queuing (también conocido como MSMQ) para crear las conexiones de mensaje en cola con otros extremos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Para obtener una lista completa de los enlaces proporcionados por el sistema, con descripciones, consulte [enlaces proporcionados](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="custom-bindings"></a>Enlaces personalizados  
 Si la colección de enlaces proporcionada por el sistema no tiene la combinación correcta de características que necesita una aplicación de servicio, puede crear un enlace <xref:System.ServiceModel.Channels.CustomBinding>. [!INCLUDE[crabout](../../../includes/crabout-md.md)]los elementos de un <xref:System.ServiceModel.Channels.CustomBinding> enlace, consulte [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) y [enlaces personalizados](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="using-bindings"></a>Utilizar los enlaces  
 El uso de enlaces conlleva dos pasos básicos:  
  
1.  Seleccione o defina un enlace. El método más fácil es elegir uno de los enlaces proporcionados por el sistema y utilizar su configuración predeterminada. Puede elegir también un enlace proporcionado por el sistema y restablecer sus valores de propiedad para satisfacer sus necesidades También puede crear un enlace personalizado y establecer las propiedades como necesite.  
  
2.  Cree un extremo que utiliza este enlace.  
  
## <a name="code-and-configuration"></a>Código y configuración  
 Puede definir o configurar los enlaces a través del código o configuración. Estos dos enfoques son independientes según el tipo de enlace utilizado, por ejemplo, si utiliza un enlace proporcionado por el sistema o un enlace <xref:System.ServiceModel.Channels.CustomBinding>. En general, el uso de código proporciona un control total sobre la definición de un enlace cuando se compila. El uso de configuración, por otro lado, permite al administrador del sistema o al usuario de un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] o cliente cambiar los parámetros de enlaces. Esta flexibilidad es a menudo deseable porque no hay ninguna manera de predecir los requisitos específicos del equipo y las condiciones de red en la cual se implementará una aplicación [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Separar la información de enlace (y direccionamiento) del código permite a los administradores cambiar los datos obligatorios sin tener que recompilar o implementar de nuevo la aplicación. Tenga en cuenta que si el enlace se define en código, sobrescribe las definiciones basadas en configuración realizadas en el archivo de configuración. Para obtener ejemplos de estos enfoques, consulte los temas siguientes:  
  
-   [Cómo: hospedar un servicio WCF en una aplicación administrada](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md) proporciona un ejemplo de cómo crear un enlace en código.  
  
-   [Cómo: configurar un cliente](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md) proporciona un ejemplo de creación de un cliente mediante configuración.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la creación de puntos finales](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Cómo especificar un enlace de servicio en la configuración](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [Cómo especificar un enlace de servicio en el código](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)  
 [Cómo especificar un enlace de cliente en la configuración](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)  
 [Cómo especificar un enlace de cliente en el código](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-code.md)
