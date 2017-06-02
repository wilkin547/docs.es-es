---
title: "Extremos: direcciones, enlaces y contratos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "extremos [WCF]"
  - "WCF [WCF], extremos"
  - "Windows Communication Foundation [WCF], extremos"
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Extremos: direcciones, enlaces y contratos
Toda comunicación con un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se produce a través de los *extremos* del servicio.Los extremos proporcionan acceso a los clientes a la funcionalidad que ofrece un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Cada extremo está compuesto de cuatro propiedades:  
  
-   Una dirección que indica dónde se puede encontrar el extremo.  
  
-   Un enlace que especifica cómo se puede comunicar un cliente con el extremo.  
  
-   Un contrato que identifica las operaciones disponibles.  
  
-   Un conjunto de comportamientos que especifican detalles de implementación local del extremo.  
  
 En este tema se describe esta estructura de extremo y se explica cómo se representa en el modelo de objetos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Estructura de un extremo  
 Cada extremo está compuesto de lo siguiente:  
  
-   Dirección: la dirección identifica únicamente el extremo e indica a los consumidores potenciales del servicio dónde se ubica éste.Está representado en el modelo de objetos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] por la clase <xref:System.ServiceModel.EndpointAddress>.Una clase <xref:System.ServiceModel.EndpointAddress> contiene:  
  
    -   Una propiedad <xref:System.ServiceModel.EndpointAddress.Uri%2A>, que representa la dirección del servicio.  
  
    -   Una propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A>, que representa la identidad de seguridad del servicio y una colección de encabezados de mensaje opcionales.Los encabezados de mensaje opcionales se utilizan para proporcionar información de direccionamiento adicional y más detallada para identificar o interactuar con el extremo.  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Especificación de una dirección de extremo](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
-   Enlace: el enlace especifica cómo comunicarse con el extremo.Esto incluye:  
  
    -   El protocolo de transporte que se ha de utilizar \(por ejemplo, TCP o HTTP\).  
  
    -   La codificación que se ha de utilizar para los mensajes \(por ejemplo, texto o binario\).  
  
    -   Los requisitos de seguridad necesarios \(por ejemplo, SSL o seguridad de mensaje SOAP\).  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Información general de WCF Bindings](../../../../docs/framework/wcf/bindings-overview.md).Un enlace se representa en el modelo de objetos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante la clase base abstracta <xref:System.ServiceModel.Channels.Binding>.Para la mayoría de los escenarios, los usuarios pueden utilizar uno de los enlaces proporcionados por el sistema.Para obtener más información, consulte [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
-   Contratos: el contrato describe qué funcionalidad expone el extremo al cliente.Un contrato especifica:  
  
    -   Qué operaciones puede llamar un cliente.  
  
    -   La forma del mensaje.  
  
    -   El tipo de parámetros de entrada o datos requeridos para llamar a la operación.  
  
    -   Qué tipo de mensaje de procesamiento respuesta puede esperar el cliente.  
  
     Para obtener más información sobre la definición de un contrato, vea [Diseño de contratos de servicios](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
-   Comportamientos: puede utilizar los comportamientos de extremo para personalizar el comportamiento local del extremo de servicio.Los comportamientos de extremo logran esto participando en el proceso de compilación de un tiempo de ejecución de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Un ejemplo de un comportamiento de extremo es la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, que permite especificar una dirección de escucha diferente que la dirección SOAP o la dirección del Lenguaje de descripción de servicios Web \(WSDL\).[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).  
  
## Definición de extremos  
 Puede especificar el extremo de un servicio de manera imperativa mediante código o de manera declarativa mediante configuración.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo crear un extremo de servicio en configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) y [Cómo crear un extremo de servicio en código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
## En esta sección  
 En esta sección se explica el propósito de los enlaces, extremos y direcciones; se muestra cómo configurar un enlace y un extremo; y cómo utilizar el comportamiento `ClientVia` y la propiedad `ListenUri`.  
  
 [Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 Describe cómo se direccionan los extremos en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)  
 Describe cómo se utilizan los enlaces para especificar el transporte, codificación y detalles protocolares requeridos para que los clientes y servicios se comuniquen entre sí.  
  
 [Contratos](../../../../docs/framework/wcf/feature-details/contracts.md)  
 Describe cómo los contratos definen los métodos de un servicio.  
  
 [Cómo crear un extremo de servicio en configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Describe cómo crear un extremo de servicio mediante configuración  
  
 [Cómo crear un extremo de servicio en código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Describe cómo crear un extremo de servicio mediante código.  
  
 [Cómo: Utilizar Svcutil.exe para validar el código del servicio compilado](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 Describe cómo detectar errores en las implementaciones y configuraciones de servicio sin hospedar el servicio mediante la [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## Vea también  
 [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)   
 [Extensión de enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md)