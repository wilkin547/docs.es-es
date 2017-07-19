---
title: "Activaci&#243;n basada en la configuraci&#243;n en IIS y WAS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Activaci&#243;n basada en la configuraci&#243;n en IIS y WAS
Normalmente, al hospedar un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en Internet Information Services \(IIS\) o el Servicio de activación de procesos de Windows \(WAS\), debe proporcionar un archivo .svc.El archivo .svc contiene el nombre del servicio y un generador de host de servicio personalizado opcional.Este archivo adicional agrega una sobrecarga de administración.La característica de activación basada en la configuración elimina el requisito de tener un archivo .svc y, por lo tanto, la sobrecarga asociada.  
  
## Activación basada en la configuración  
 La activación basada en la configuración toma los metadatos que se solían encontrar en el archivo .svc y los coloca en el archivo Web.config.Dentro del elemento \<`serviceHostingEnvironment`\>, hay un elemento \<`serviceActivations`\>.Dentro del elemento \<`serviceActivations`\>, hay uno o más elementos \<`add`\>, uno para cada servicio hospedado.El elemento \<`add`\> contiene atributos que le permiten establecer la dirección relativa para el servicio y el tipo de servicio, o un generador de host de servicio.El siguiente ejemplo de configuración muestra cómo se utiliza esta sección.  
  
> [!NOTE]
>  Cada elemento \<`add`\> debe especificar un servicio o un atributo de generador.Se puede especificar tanto el servicio como los atributos de generador.  
  
```  
<serviceHostingEnvironment>  
  <serviceActivations>  
    <add relativeAddress="MyServiceAddress" service="Service" factory=”MyServiceHostFactory”/>  
  </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
 Con esto en el archivo Web.config, puede colocar el código fuente del servicio en el directorio App\_Code de la aplicación o un ensamblado compatible en el directorio Bin de la aplicación.  
  
> [!NOTE]
>  -   Cuando se usa la activación basada en la configuración, no se admite código insertado en los archivos .svc.  
> -   El atributo `relativeAddress` debe estar establecido en una dirección relativa como "\/\<subdirectorio\>\/service.svc" o "~\/\<subdirectorio\/service.svc".  
> -   Se produce una excepción de configuración si registra una dirección relativa que no tiene una extensión conocida asociada a WCF.  
> -   La dirección relativa especificada es relativa a la raíz de la aplicación virtual.  
> -   Debido al modelo jerárquico de la configuración, las direcciones relativas registradas en el equipo y en el sitio son heredadas por aplicaciones virtuales.  
> -   Los registros de un archivo de configuración tienen prioridad sobre la configuración de .svc, .xamlx, .xoml u otro archivo.  
> -   Cualquier '\\' \(barras diagonales inversas\) en un URI enviada a IIS\/WAS se convierte automáticamente en '\/' \(barra diagonal\).Si se agrega una dirección relativa que contiene una '\\' y le envía a IIS un URI que usa la dirección relativa, la barra diagonal inversa se convierte en una barra diagonal e IIS no puede hacerla coincidir con la dirección relativa.IIS envía información de traza que indica que no se ha detectado ninguna coincidencia.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>   
 [Servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md)   
 [Hospedar información general de servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)   
 [\<serviceHostingEnvironment\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)   
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)