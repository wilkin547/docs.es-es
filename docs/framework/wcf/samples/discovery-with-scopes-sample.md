---
title: "Ejemplo de detecci&#243;n con &#225;mbitos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6a37a754-6b8c-4ebe-bdf2-d4f0520271d5
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Ejemplo de detecci&#243;n con &#225;mbitos
Este ejemplo muestra cómo utilizar los ámbitos para clasificar los extremos detectables además de cómo utilizar <xref:System.ServiceModel.Discovery.DiscoveryClient> para realizar una búsqueda asincrónica de los extremos.En el servicio, este ejemplo muestra cómo personalizar la detección de cada extremo agregando un comportamiento de detección de extremo y utilizándolo para agregar un ámbito al extremo así como controlando la detectabilidad del extremo.En el cliente, el ejemplo revisa el modo en que los clientes pueden crear un <xref:System.ServiceModel.Discovery.DiscoveryClient> y ajustar los parámetros de búsqueda para incluir ámbitos agregándolos a <xref:System.ServiceModel.Discovery.FindCriteria>.Este ejemplo también muestra el modo en que los clientes pueden restringir las respuestas agregando un criterio de terminación.  
  
## Características de servicio  
 Este proyecto muestra dos extremos de servicio que se agregan a un <xref:System.ServiceModel.ServiceHost>.Cada extremo tiene un <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> asociado.Este comportamiento se utiliza para agregar los ámbitos del URI para ambos extremos.Los ámbitos se utilizan para distinguir cada uno de estos extremos para que los clientes puedan ajustar la búsqueda.Para el segundo extremo, la detectabilidad puede deshabilitarse estableciendo la propiedad <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> en `false`.De este modo se asegura de que los metadatos de detección asociados a este extremo no se envían como parte de ningún mensaje de detección.  
  
## Características de cliente  
 El método `FindCalculatorServiceAddress()` muestra cómo utilizar <xref:System.ServiceModel.Discovery.DiscoveryClient> y pasarlo en un <xref:System.ServiceModel.Discovery.FindCriteria> con dos restricciones.Un ámbito se agrega a los criterios y la propiedad <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> se establece en 1.El ámbito limita los resultados solo a los servicios que publican el mismo ámbito.Al establecer <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> en 1, se limitan las respuestas que el <xref:System.ServiceModel.Discovery.DiscoveryClient> espera a un extremo, como máximo.La llamada a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> es una operación sincrónica que bloquea el subproceso hasta que se alcance un tiempo de espera o se encuentre un extremo.  
  
#### Para utilizar este ejemplo  
  
1.  Este ejemplo utiliza los extremos HTTP y para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas.Vea [Configura HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener detalles.Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas.Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería: `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  Compile la solución.  
  
3.  Ejecute el ejecutable de servicio desde el directorio de compilación.  
  
4.  Ejecute la aplicación cliente.Observe que el cliente puede localizar el servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryWithScopes`  
  
## Vea también