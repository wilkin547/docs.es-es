---
title: "Activación basada en la configuración en IIS y WAS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 116d7ec11f141e813aa960b28289031e0cfa8999
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="configuration-based-activation-in-iis-and-was"></a>Activación basada en la configuración en IIS y WAS
Normalmente, al hospedar un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en Internet Information Services (IIS) o el Servicio de activación de procesos de Windows (WAS), debe proporcionar un archivo .svc. El archivo .svc contiene el nombre del servicio y un generador de host de servicio personalizado opcional. Este archivo adicional agrega una sobrecarga de administración. La característica de activación basada en la configuración elimina la necesidad de tener un archivo .svc y, por lo tanto, la sobrecarga asociada.  
  
## <a name="configuration-based-activation"></a>Activación basada en la configuración  
 La activación basada en la configuración toma los metadatos que se solían encontrar en el archivo .svc y los coloca en el archivo Web.config. En el <`serviceHostingEnvironment`> elemento no existe un <`serviceActivations`> elemento. En el <`serviceActivations`> elemento son uno o más <`add`> elementos, uno para cada servicio hospedado. El <`add`> elemento contiene atributos que permiten definir la dirección relativa para el servicio y el tipo de servicio o un generador de host de servicio. El siguiente ejemplo de configuración muestra cómo se utiliza esta sección.  
  
> [!NOTE]
>  Cada <`add`> elemento debe especificar un servicio o un atributo factory. Se puede especificar tanto el servicio como los atributos de generador.  
  
```xml  
<serviceHostingEnvironment>  
  <serviceActivations>  
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>  
  </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
 Con esto en el archivo Web.config, puede colocar el código fuente del servicio en el directorio App_Code de la aplicación o un ensamblado compatible en el directorio Bin de la aplicación.  
  
> [!NOTE]
>  -   Cuando se usa la activación basada en la configuración, no se admite código insertado en los archivos .svc.  
> -   El `relativeAddress` atributo debe establecerse en una dirección relativa como "\<subdirectorio > / service.svc" o "~ /\<subdirectorio/service.svc".  
> -   Se produce una excepción de configuración si registra una dirección relativa que no tiene una extensión conocida asociada a WCF.  
> -   La dirección relativa especificada es relativa a la raíz de la aplicación virtual.  
> -   Debido al modelo jerárquico de la configuración, las direcciones relativas registradas en el equipo y en el sitio son heredadas por aplicaciones virtuales.  
> -   Los registros de un archivo de configuración tienen prioridad sobre la configuración de .svc, .xamlx, .xoml u otro archivo.  
> -   Cualquier '\' (barras diagonales inversas) en un URI enviada a IIS/WAS se convierte automáticamente en '/' (barra diagonal). Si se agrega una dirección relativa que contiene una '\' y le envía a IIS un URI que usa la dirección relativa, la barra diagonal inversa se convierte en una barra diagonal e IIS no puede hacerla coincidir con la dirección relativa. IIS envía información de traza que indica que no se ha detectado ninguna coincidencia.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>  
 [Servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md)  
 [Hospedar información general de servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 [\<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)  
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
