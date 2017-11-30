---
title: Procedimientos recomendados de hospedaje de Internet Information Services
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
caps.latest.revision: "22"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60d703336aeac3471e4b554f65998621b5cc8ef8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="internet-information-services-hosting-best-practices"></a>Procedimientos recomendados de hospedaje de Internet Information Services
En este tema se describen algunos procedimientos recomendados para hospedar los servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementación de servicios WCF como DLL  
 Implementar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] como una DLL que se implementa en el directorio \bin de una aplicación web permite reutilizar el servicio fuera del modelo de aplicación web, por ejemplo, en un entorno de pruebas que no puede tener implantad Internet Information Services (IIS).  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Hosts de servicio de aplicaciones hospedadas en IIS  
 No utilice las API de autohospedaje imperativo para crear nuevos hosts de servicio que realicen escuchas en transportes de red no admitidos nativamente por el entorno de hospedaje de IIS (por ejemplo, [!INCLUDE[iis601](../../../../includes/iis601-md.md)] para hospedar servicios TCP, porque la comunicación TCP no se admite de manera nativa en [!INCLUDE[iis601](../../../../includes/iis601-md.md)]). Éste enfoque no se recomienda. Los hosts de servicio creados de manera imperativa no se conocen dentro del entorno de hospedaje de IIS. El punto crítico es que el procesamiento realizado por servicios creados imperativamente no se tiene en cuenta por parte de IIS cuando determina si el grupo de aplicaciones de hospedaje está inactivo. El resultado es que las aplicaciones que tienen hosts de servicio creados de esta manera imperativa tienen un entorno de hospedaje de IIS que elimina de manera agresiva los procesos de host de IIS.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URI y extremos hospedados en IIS  
 Los extremos para un servicio hospedado en IIS se deberían configurar utilizando Identificadores uniformes de recursos relativos (URI), no direcciones absolutas. Esto garantiza que la dirección de extremo cae dentro del conjunto de direcciones URI que pertenecen a la aplicación de hospedaje y asegura que la activación basada en mensaje ocurre tal y como se esperaba.  
  
## <a name="state-management-and-process-recycling"></a>Administración de estado y reciclaje de procesos  
 El entorno de hospedaje de IIS se optimiza para servicios que no mantienen el estado local en memoria. IIS recicla el proceso del host en respuesta a diversos eventos externos e internos, produciendo que se pierda cualquier estado volátil almacenado exclusivamente en memoria. Los servicios hospedados en IIS deberían almacenar su estado externo al proceso (por ejemplo, en una base de datos) o en una caché en memoria que se puede recrear con facilidad si tiene lugar un evento de reciclaje de aplicación.  
  
> [!NOTE]
>  Los protocolos que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa para la conconfiabilidad y seguridad de la capa de mensaje usan el estado volátil en memoria. Las sesiones confiables y las sesiones de seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden finalizar inesperadamente debido a reciclajes de la aplicación. Las aplicaciones hospedadas en IIS que hacen uso de estos protocolos no deberían depender de la clave de sesión proporcionada por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para correlacionar el estado de nivel de aplicación (por ejemplo, una construcción del nivel de aplicación o un encabezado de correlación personalizado) o deshabilitar el reciclaje de procesos de IIS para la aplicación hospedada.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Optimización del rendimiento en escenarios de nivel medio  
 Para obtener un rendimiento óptimo en un *escenario de nivel medio*: un servicio que llama a otros servicios en respuesta a los mensajes entrantes: crear una instancia de la [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente al servicio remoto de servicio una vez y reutilícelo en varias solicitudes entrantes. Crear instancias de los clientes del servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es una operación costosa relativa a hacer una llamada de servicio en una instancia de un cliente preexistente, y los escenarios de nivel medio generan ganancias de rendimiento distintas almacenando en memoria caché los clientes remotos de las solicitudes. Los clientes del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] son seguros para subprocesos, por lo que no es necesario sincronizar el acceso a un cliente a través de varios subprocesos.  
  
 Los escenarios de nivel medio también generan ganancias de rendimiento utilizando API asincrónicas generadas por la opción `svcutil /a`. El `/a` opción causas el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar `BeginXXX/EndXXX` métodos para cada operación de servicio, lo que permite llamadas de larga duración a los servicios remotos hacerse en subprocesos en segundo plano.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF en escenarios multitarjeta o de varios nombres  
 Puede implementar servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dentro de una granja de servidores web de IIS, donde un conjunto de equipos comparte un nombre externo común (como http://www.contoso.com) pero son direccionados individualmente por nombres de host diferentes (por ejemplo, http://www.contoso.com podría dirigir el tráfico a dos equipos diferentes denominados (http://machine1.internal.contoso.com y http://machine2.internal.contoso.com). [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]admite totalmente este escenario de implementación, pero requiere una configuración especial del sitio web de IIS que hospeda los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para mostrar el nombre del host correcto (externo) en los metadatos del servicio (lenguaje de descripción de servicios Web).  
  
 Para asegurarse de que el nombre del host correcto aparece en los metadatos de servicio que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera, configure la identidad predeterminada para que el sitio web de IIS que hospeda los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilice un nombre de host explícito. Por ejemplo, equipos que residen dentro de la granja www.contoso.com deberían utilizar un enlace de sitio IIS de *: 80: www.contoso.com para HTTP y \*: 443:www.contoso.com para HTTPS.  
  
 Puede configurar los enlaces de sitio web de IIS utilizando el complemento de Microsoft Management Console (MMC).  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>Los grupos de aplicaciones que se ejecutan en contextos de usuario diferentes sobrescriben los ensamblados desde otras cuentas en la carpeta temporal  
 Para asegurarse de que los grupos de aplicaciones que se ejecutan en diferentes contextos de usuario no pueden sobrescribir los ensamblados desde otras cuentas en la carpeta de archivos [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] temporales, utilice identidades diferentes y carpetas temporales para las aplicaciones diferentes. Por ejemplo, si tiene dos aplicaciones virtuales /Application1 y / Application2, puede crear dos grupos de aplicaciones, A y B, con dos identidades diferentes. El grupo de aplicaciones A se puede ejecutar bajo una identidad de usuario (user1), mientras que el grupo de aplicaciones B se puede ejecutar bajo otra identidad de usuario (user2) y configurar /Application1 para que use A y /Application2 para que use B.  
  
 En el archivo Web.config, puede configurar la carpeta temporal mediante \< system.web/compilation/@tempFolder>. Para/Application1, puede ser "c:\tempForUser1" y para application2 puede ser "c:\tempForUser2". Conceda el permiso de escritura correspondiente a estas carpetas para las dos identidades.  
  
 A continuación, user2 no puede cambiar la carpeta de generación de código para /application2 (bajo c:\tempForUser1).  
  
## <a name="enabling-asynchronous-processing"></a>Habilitar el procesamiento asincrónico  
 De forma predeterminada, los mensajes enviados a un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedado en IIS 6.0 y versiones anteriores se procesan de forma sincrónica. ASP.NET llama a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en su propio subproceso (el subproceso de trabajo de ASP.NET) y [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa otro subproceso para procesar la solicitud. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] acapara el subproceso de trabajo de ASP.NET hasta que este complete su procesamiento. Esto lleva a un procesamiento sincrónico de las solicitudes. El procesamiento de las solicitudes de forma asincrónica ofrece una mayor escalabilidad, ya que reduce el número de subprocesos necesarios para procesar una solicitud. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no acapara el subproceso de ASP.NET mientras procesa la solicitud. No se recomienda el uso del comportamiento asincrónico de equipos que ejecutan IIS 6.0 porque no hay ninguna manera de limitar las solicitudes entrantes que el servidor se abrirán *denegación de servicio* ataques (DOS). A partir de IIS 7.0, se ha introducido un acelerador de solicitudes simultáneas: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Con este nuevo acelerador, el procesamiento asincrónico se puede usar de forma segura.  De forma predeterminada en IIS 7.0, se registran el controlador y el módulo asincrónicos. Si se ha deshabilitado, puede habilitar manualmente el procesamiento asincrónico de las solicitudes en el archivo Web.config de la aplicación. La configuración que se use depende de la configuración de `aspNetCompatibilityEnabled`. Si ha establecido `aspNetCompatibilityEnabled` en `false`, configure el objeto `System.ServiceModel.Activation.ServiceHttpModule` tal y como se muestra en el fragmento de código de configuración siguiente.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="false" />      
  </system.serviceModel>  
  <system.webServer>  
    <modules>  
      <remove name="ServiceModel"/>  
      <add name="ServiceModel"   
           preCondition="integratedMode,runtimeVersionv2.0"   
           type="System.ServiceModel.Activation.ServiceHttpModule, System.ServiceModel,Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
    </modules>  
    </system.webServer>  
```  
  
 Si ha establecido `aspNetCompatibilityEnabled` en `true`, configure el objeto `System.ServiceModel.Activation.ServiceHttpHandlerFactory` tal y como se muestra en el fragmento de código de configuración siguiente.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />      
  </system.serviceModel>  
  <system.webServer>  
    <handlers>  
          <clear/>  
          <add name="TestAsyncHttpHandler"   
               path="*.svc"   
               verb="*"   
               type="System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"           
               />  
    </handlers>      
  </system.webServer>  
```  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de hospedaje de servicio](http://msdn.microsoft.com/en-us/f703a3f6-0fba-418a-a92f-7ce75ccfa47e)  
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
