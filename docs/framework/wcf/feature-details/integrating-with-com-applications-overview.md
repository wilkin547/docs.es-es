---
title: "Integración con la información general de las aplicaciones COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4e995fc66a925cb0ebe272c9dceca1ba63b9459d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="integrating-with-com-applications-overview"></a>Integración con la información general de las aplicaciones COM
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona un entorno enriquecido al desarrollador del código administrado para crear aplicaciones conectadas. Sin embargo, si tiene una inversión sustancial en código basado en COM no administrado y no desea migrar, aún podrá integrar directamente los servicios web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en el código existente mediante el moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. El moniker de servicio se puede utilizar a partir de una gama amplia de entornos de desarrollo basados en COM, como Office VBA, Visual Basic 6.0 o Visual C++ 6.0.  
  
> [!NOTE]
>  El moniker de servicio utiliza un canal de comunicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para toda la comunicación. Los mecanismos de identidad y seguridad para ese canal difieren de aquéllos utilizados en los proxies COM y DCOM estándar. Además, dado que el moniker de servicio utiliza un canal de comunicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], el período de tiempo de espera predeterminado es un minuto para todas las llamadas.  
  
 El moniker de servicio se utiliza con la función `GetObject` para proporcionar un enfoque fuertemente tipado, específico de COM al desarrollador no administrado con el fin de llamar a los servicios web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Esto requiere una definición local, visible a través de COM del contrato de servicio web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y el enlace que se va a usar. Al igual que otros clientes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], el moniker de servicio debe construir un canal con tipo al servicio, aunque esta construcción del canal se produce de forma transparente en el programador COM en la primera llamada al método.  
  
 Al igual que otros clientes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], al utilizar el moniker, las aplicaciones especifican la dirección, el enlace y el contrato para comunicarse con un servicio. El contrato se puede especificar de una de las maneras siguientes:  
  
-   Contrato con tipo: el contrato se registra como un tipo visible COM en el equipo cliente.  
  
-   Contrato de WSDL: el contrato se proporciona con la forma de un documento WSDL.  
  
-   Contrato de MEX: el contrato se recupera en el tiempo de ejecución a partir de un extremo de intercambio de metadatos (MEX).  
  
## <a name="parameters-supported-by-the-service-moniker"></a>Parámetros admitidos por el moniker de servicio  
 En la tabla siguiente se muestran los parámetros admitidos por el moniker de servicio.  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`address`|Ubicación de URL del servicio.|  
|`binding`|Nombre de sección de enlace desde la configuración de la aplicación.|  
|`bindingConfiguration`|Instancia del enlace con nombre desde la sección de enlace con nombre.|  
|`contract`|Identificador de interfaz (IID) que representa el contrato de servicio o el nombre del contrato (de MEX).|  
|`wsdl`|Documento WSDL que proporciona un formulario alternativo de definición de contrato.|  
|`spnIdentity`|Identidad del nombre de entidad de seguridad de servidor (SPN) que se va a utilizar para comunicarse con el servicio.|  
|`upnIdentity`|Identidad del nombre principal del usuario (UPN) que se va a utilizar para comunicarse con el servicio.|  
|`dnsIdentity`|Identidad de DNS que se va a utilizar para comunicarse con el servicio.|  
|`mexAddress`|Ubicación de la dirección URL del punto de conexión de intercambio de metadatos (MEX) del servicio.|  
|`mexBinding`|El nombre de la sección de enlace a partir de la configuración de la aplicación para conectarse con el punto de conexión MEX.|  
|`mexBindingConfiguration`|Instancia de enlace con nombre desde la que la sección de enlace con nombre se conecta con el punto de conexión MEX.|  
|`bindingNamespace`|El espacio de nombres del nombre de la sección de enlace desde el MEX recuperado.|  
|`contractNamespace`|El espacio de nombres del contrato desde el MEX recuperado.|  
|`mexSpnIdentity`|Identidad del nombre de entidad de seguridad de servidor (SPN) que se va a utilizar para comunicarse con el punto de conexión MEX.|  
|`mexUpnIdentity`|Identidad del nombre principal del usuario (UPN) que se va a utilizar para comunicarse con el punto de conexión MEX.|  
|`mexDnsIdentity`|Identidad de DNS que se va a utilizar para comunicarse con el punto de conexión MEX.|  
|`serializer`|Especifique el uso de "xml" o serializador de "datacontract."|  
  
> [!NOTE]
>  Incluso cuando se utiliza con clientes completamente basados en COM, el moniker de servicio exige que se instale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y .NET Framework 2.0 compatible en el equipo cliente. También es fundamental que las aplicaciones cliente que utilizan el moniker de servicio carguen la versión adecuada del tiempo de ejecución de .NET Framework. Al utilizar el moniker en aplicaciones de Office, es posible que sea necesario un archivo de configuración para asegurarse de que se carga la versión de marco correcta. Por ejemplo, con Excel, el texto siguiente debería colocarse en un archivo denominado Excel.exe.config en el mismo directorio que el archivo Excel.exe:  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  `<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a>Vea también  
 [Cómo: registrar y configurar un Moniker de servicio](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
