---
title: "Utilizaci&#243;n de las herramientas de desarrollo de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Utilizaci&#243;n de las herramientas de desarrollo de WCF
En esta sección se describen las herramientas de desarrollo [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[indigo1](../../../includes/indigo1-md.md)] que pueden ayudarle a desarrollar su servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Puede utilizar las plantillas [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] como base para generar rápidamente su propio servicio y, a continuación, utilizar el host automático de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para depurar y probar el servicio.  Todas estas herramientas proporcionan una depuración y un ciclo de prueba rápido y estable, y descartan la necesidad de adaptarse a un modelo de hospedaje en una fase temprana.  
  
## Herramientas de desarrollador de WCF  
 [Plantillas de Visual Studio para WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Puede utilizar las plantillas predefinidas de proyecto y elemento [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para generar rápidamente los servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y las aplicaciones que los rodean.  
  
 [Host de servicio WCF \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 El host automático de servicio \(WcfSvcHost.exe\) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] permite iniciar el depurador \(F5\) [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para hospedar y probar automáticamente un servicio implementado.  Después, puede probar el servicio utilizando el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(WcfTestClient.exe\), o su propio cliente, para buscar y corregir cualquier error potencial.  
  
 [Cliente de prueba de WCF \(WcfTestClient.exe\)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 El cliente de prueba \(WcfTestClient.exe\) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es una herramienta GUI que permite introducir parámetros de tipos arbitrarios, enviar esa entrada al servicio, y ver la respuesta que devuelve el servicio.  Proporciona un servicio de prueba sin problemas cuando se combina con el host automático de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 [Generar clases de tipos de datos a partir de XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 Los datos XML almacenados en el portapapeles se pueden pegar en una página de códigos.  Las clases definidas en los datos se convertirán en tipos de código.  
  
## Utilización de las herramientas sin el privilegio de administrador  
 Para permitir que los usuarios sin el privilegio de administrador desarrollen servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], se crea una ACL \(Lista de control de acceso\) para el espacio de nombres "http:\/\/\+:8731\/Design\_Time\_Addresses" durante la instalación de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  La ACL se establece en la interfaz de usuario \(UI\), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo.  Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite que las plantillas WCF o WF envíen y reciban datos con su configuración predeterminada.  También permite a los usuarios utilizar el host automático de servicio \(wcfSvcHost.exe\) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sin concederles los privilegios de administrador.  
  
 Puede modificar el acceso mediante la herramienta Netsh.exe de [!INCLUDE[wv](../../../includes/wv-md.md)] con la cuenta elevada de administrador.  En el siguiente ejemplo se muestra el uso de Netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] Netsh.exe, consulte [Cómo usar la herramienta Netsh.exe y los conmutadores de línea de comandos](http://go.microsoft.com/fwlink/?LinkId=97877).  
  
## Vea también  
 [Plantillas de Visual Studio para WCF](../../../docs/framework/wcf/wcf-vs-templates.md)   
 [Host de servicio WCF \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)   
 [Cliente de prueba de WCF \(WcfTestClient.exe\)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)