---
title: Información general de enlaces de Windows Communication Foundation
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
- bindings [WCF], overview
ms.assetid: cfb5842f-e0f9-4c56-a015-f2b33f258232
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 58b3691c186dc6a33c94d9f8a1af96be488d67df
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="windows-communication-foundation-bindings-overview"></a>Información general de enlaces de Windows Communication Foundation
Los enlaces son objetos que se utilizan para especificar los datos de la comunicación requeridos para conectar al extremo de un servicio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Cada extremo en un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] requiere que un enlace esté bien especificado. En este tema, se describen los tipos de datos de comunicación que los enlaces definen, los elementos de un enlace, qué enlaces están incluidos en [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]y cómo se puede especificar un enlace para un extremo.  
  
## <a name="what-a-binding-defines"></a>Qué define un enlace  
 La información de un enlace puede ser muy básica o muy compleja. El enlace más básico especifica solo el protocolo de transporte (como HTTP) que se debe utilizar para conectar al extremo. En términos más generales, la información que contiene un enlace sobre cómo conectarse a un extremo queda incluida en una de las siguientes categorías.  
  
 Protocolos  
 Determina el mecanismo de seguridad utilizado: función de la mensajería de confianza o configuración de flujo de contexto de transacción.  
  
 Codificación  
 Determina la codificación del mensaje (por ejemplo, texto o binario).  
  
 Transporte  
 Determina el protocolo de transporte subyacente que se utilizará (por ejemplo, TCP o HTTP).  
  
## <a name="the-elements-of-a-binding"></a>Los elementos de un enlace  
 Un enlace está básicamente compuesto de una pila ordenada de elementos de enlace, cada uno de los cuales especifica parte de la información de la comunicación requerida para conectar a un extremo de servicio. Las dos capas más bajas de la pila son necesarias. En la base de la pila se encuentra el elemento de enlace de transporte y justo antes que éste se encuentra el elemento que contiene las especificaciones de la codificación del mensaje. Los elementos de enlace opcionales que especifican los demás protocolos de comunicación se superponen a estos dos elementos necesarios. Para obtener más información acerca de estos elementos de enlace y su orden correcto, consulte [enlaces personalizados](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema  
 La información de un enlace puede ser compleja y puede que parte de su configuración no sea compatible con otros. Por esta razón, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye un conjunto de enlaces proporcionados por el sistema. Estos enlaces están diseñados para cubrir la mayoría de los requisitos de aplicación. Las clases siguientes representan algunos ejemplos de enlaces proporcionados por el sistema:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>: Un enlace de protocolo HTTP adecuado para conectar a los Servicios Web que cumple con la especificación del WS-I Basic Profile (por ejemplo, servicios web ASP.NET - servicios basados).  
  
-   <xref:System.ServiceModel.WSHttpBinding>: Un enlace interoperable adecuado para conectar a los extremos que se ajustan a WS - * protocolos.  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>: Utiliza [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] para conectar a otros extremos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en el mismo equipo.  
  
-   <xref:System.ServiceModel.NetMsmqBinding>: Utiliza [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] para crear las conexiones de mensajes en cola con otros extremos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Para obtener una lista completa, con descripciones de todos los [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-proporciona enlaces, vea [enlaces proporcionados](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="using-your-own-bindings"></a>Utilizar sus propios enlaces  
 Si ninguno de los enlaces proporcionados por el sistema incluidos tiene la combinación correcta de características que requiere una aplicación de servicio, puede crear su propio enlace. Existen dos formas de lograr esto. Puede crear un nuevo enlace a partir de elementos de enlace ya existentes mediante un objeto <xref:System.ServiceModel.Channels.CustomBinding> o puede crear un enlace completamente definido por el usuario derivando del enlace <xref:System.ServiceModel.Channels.Binding>. Para obtener más información acerca de cómo crear su propio enlace mediante estos dos enfoques, consulte [enlaces personalizados](../../../docs/framework/wcf/extending/custom-bindings.md) y [crear enlaces](../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
## <a name="using-bindings"></a>Utilizar los enlaces  
 El uso de enlaces conlleva dos pasos básicos:  
  
1.  Seleccione o defina un enlace. El método más fácil es elegir uno de los enlaces proporcionados por el sistema incluido con [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y lo utiliza con su configuración predeterminada. Puede elegir también un enlace proporcionado por el sistema y restablecer sus valores de propiedad para satisfacer sus necesidades Otra manera es crear un enlace personalizado o un enlace definido por el usuario para tener grados de control y personalización más altos.  
  
2.  Cree un extremo que utilice el enlace seleccionado o definido.  
  
## <a name="code-and-configuration"></a>Código y configuración  
 Puede definir los enlaces de dos maneras: a través del código o a través de la configuración. Estos dos enfoques no dependen de si está utilizando un enlace proporcionado por el sistema o un enlace personalizado. En general, utilizar el código le proporciona un control total sobre la definición de un enlace y el tiempo de diseño. Por otro lado, la configuración permite a un administrador del sistema o el usuario de un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] o cliente cambiar los parámetros de un enlace sin tener que recompilar la aplicación de servicio. Esta flexibilidad es a menudo deseable, porque no hay ninguna manera de predecir los requisitos específicos del equipo con los que se implementará una aplicación [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Dejar fuera la información de enlace (y el direccionamiento) del código les permite cambiar sin requerir recopilación o nueva implementación de la aplicación. Tenga en cuenta que se crean enlaces definidos en código después de los enlaces especificados en la configuración, de modo que se permite a los enlaces definidos por código sobrescribir los enlaces definidos por la configuración.  
  
## <a name="see-also"></a>Vea también  
 [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
