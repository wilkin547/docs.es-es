---
title: "puntos de conexión: direcciones, enlaces y contratos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1ee80307e0db82f4744970844754a910e81ca3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>puntos de conexión: direcciones, enlaces y contratos
Toda la comunicación con un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] servicio se produce a través de la *extremos* del servicio. Los extremos proporcionan acceso a los clientes a la funcionalidad que ofrece un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Cada extremo está compuesto de cuatro propiedades:  
  
-   Una dirección que indica dónde se puede encontrar el extremo.  
  
-   Un enlace que especifica cómo un se puede comunicar un cliente con el extremo.  
  
-   Un contrato que identifica las operaciones disponibles.  
  
-   Un conjunto de comportamientos que especifican detalles de implementación local del extremo.  
  
 En este tema se describe esta estructura de extremo y se explica cómo se representa en el modelo de objetos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="the-structure-of-an-endpoint"></a>Estructura de un extremo  
 Cada extremo está compuesto de lo siguiente:  
  
-   Dirección: la dirección identifica únicamente el extremo e indica a los consumidores potenciales del servicio dónde se ubica éste. Está representado en el modelo de objetos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] por la clase <xref:System.ServiceModel.EndpointAddress>. Una clase <xref:System.ServiceModel.EndpointAddress> contiene:  
  
    -   Una propiedad <xref:System.ServiceModel.EndpointAddress.Uri%2A>, que representa la dirección del servicio.  
  
    -   Una propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A>, que representa la identidad de seguridad del servicio y una colección de encabezados de mensaje opcionales. Los encabezados de mensaje opcionales se utilizan para proporcionar información de direccionamiento adicional y más detallada para identificar o interactuar con el punto de conexión.  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Al especificar una dirección de punto de conexión](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
-   Enlace: el enlace especifica cómo comunicarse con el punto de conexión. Esto incluye:  
  
    -   El protocolo de transporte que se ha de utilizar (por ejemplo, TCP o HTTP).  
  
    -   La codificación que se ha de utilizar para los mensajes (por ejemplo, texto o binario).  
  
    -   Los requisitos de seguridad necesarios (por ejemplo, SSL o seguridad de mensaje SOAP).  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Información general de enlaces de WCF](../../../../docs/framework/wcf/bindings-overview.md). Un enlace se representa en el modelo de objetos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante la clase base abstracta <xref:System.ServiceModel.Channels.Binding>. Para la mayoría de los escenarios, los usuarios pueden utilizar uno de los enlaces proporcionados por el sistema. Para obtener más información, consulte [enlaces proporcionados](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
-   Contratos: el contrato describe qué funcionalidad expone el punto de conexión al cliente. Un contrato especifica:  
  
    -   Qué operaciones puede llamar un cliente.  
  
    -   La forma del mensaje.  
  
    -   El tipo de parámetros de entrada o datos requeridos para llamar a la operación.  
  
    -   Qué tipo de mensaje de procesamiento respuesta puede esperar el cliente.  
  
     Para obtener más información acerca de cómo definir un contrato, vea [diseñar contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
-   Comportamientos: puede utilizar los comportamientos de punto de conexión para personalizar el comportamiento local del punto de conexión de servicio. Comportamientos de extremo logran esto participando en el proceso de creación una [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]en tiempo de ejecución. Un ejemplo de un comportamiento de extremo es la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, que permite especificar una dirección de escucha diferente que la dirección SOAP o la dirección del Lenguaje de descripción de servicios Web (WSDL). [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).  
  
## <a name="defining-endpoints"></a>Definición de puntos de conexión  
 Puede especificar el punto de conexión de un servicio de manera imperativa mediante código o de manera declarativa mediante configuración. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: crear un extremo de servicio en configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) y [Cómo: crear un extremo de servicio en el código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
## <a name="in-this-section"></a>En esta sección  
 En esta sección se explica el propósito de los enlaces, extremos y direcciones; se muestra cómo configurar un enlace y un extremo; y cómo utilizar el comportamiento `ClientVia` y la propiedad `ListenUri`.  
  
 [Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 Describe cómo se direccionan los extremos en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)  
 Describe cómo se utilizan los enlaces para especificar el transporte, codificación y detalles protocolares requeridos para que los clientes y servicios se comuniquen entre sí.  
  
 [Contratos](../../../../docs/framework/wcf/feature-details/contracts.md)  
 Describe cómo los contratos definen los métodos de un servicio.  
  
 [Cómo: crear un extremo de servicio en configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Describe cómo crear un punto de conexión de servicio mediante configuración  
  
 [Cómo: crear un extremo de servicio en el código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Describe cómo crear un punto de conexión de servicio mediante código.  
  
 [Cómo: utilizar Svcutil.exe para validar código de servicio compilado](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 Describe cómo detectar errores en las configuraciones y las implementaciones del servicio sin hospedar el servicio utilizando la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="see-also"></a>Vea también  
 [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)  
 [Extensión de enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md)
