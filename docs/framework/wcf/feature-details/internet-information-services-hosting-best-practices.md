---
title: Procedimientos recomendados de hospedaje de Internet Information Services
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: 0ca5e20b846a1b10f5a52748ff06a4af958b2f4c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2018
ms.locfileid: "45658761"
---
# <a name="internet-information-services-hosting-best-practices"></a>Procedimientos recomendados de hospedaje de Internet Information Services
En este tema se describe algunos procedimientos recomendados para hospedar servicios Windows Communication Foundation (WCF).  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementación de servicios WCF como DLL  
 Implementación de WCF service como un archivo DLL que se implementa en el directorio \bin de una aplicación Web permite que reutilizar el servicio fuera del modelo de aplicación Web, por ejemplo, en un entorno de prueba que no tenga implementado Internet Information Services (IIS).  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Hosts de servicio de aplicaciones hospedadas en IIS  
 No utilice las API de autohospedaje imperativo para crear nuevos hosts de servicio que realicen escuchas en transportes de red no admitidos nativamente por el entorno de hospedaje de IIS (por ejemplo, [!INCLUDE[iis601](../../../../includes/iis601-md.md)] para hospedar servicios TCP, porque la comunicación TCP no se admite de manera nativa en [!INCLUDE[iis601](../../../../includes/iis601-md.md)]). Éste enfoque no se recomienda. Los hosts de servicio creados de manera imperativa no se conocen dentro del entorno de hospedaje de IIS. El punto crítico es que el procesamiento realizado por servicios creados imperativamente no se tiene en cuenta por parte de IIS cuando determina si el grupo de aplicaciones de hospedaje está inactivo. El resultado es que las aplicaciones que tienen hosts de servicio creados de esta manera imperativa tienen un entorno de hospedaje de IIS que elimina de manera agresiva los procesos de host de IIS.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URI y extremos hospedados en IIS  
 Los puntos de conexión para un servicio hospedado en IIS se deberían configurar utilizando Identificadores uniformes de recursos relativos (URI), no direcciones absolutas. Esto garantiza que la dirección de extremo cae dentro del conjunto de direcciones URI que pertenecen a la aplicación de hospedaje y asegura que la activación basada en mensaje ocurre tal y como se esperaba.  
  
## <a name="state-management-and-process-recycling"></a>Administración de estado y reciclaje de procesos  
 El entorno de hospedaje de IIS se optimiza para servicios que no mantienen el estado local en memoria. IIS recicla el proceso del host en respuesta a diversos eventos externos e internos, produciendo que se pierda cualquier estado volátil almacenado exclusivamente en memoria. Los servicios hospedados en IIS deberían almacenar su estado externo al proceso (por ejemplo, en una base de datos) o en una caché en memoria que se puede recrear con facilidad si tiene lugar un evento de reciclaje de aplicación.  
  
> [!NOTE]
>  Usan los protocolos que usa WCF para la seguridad y confiabilidad del nivel de mensaje del estado en memoria volátil. Las sesiones confiables de WCF y las sesiones de seguridad pueden finalizar inesperadamente debido a reciclajes de la aplicación. Las aplicaciones hospedadas en IIS que hacen usan de estos protocolos debe depender en algo distinto de la clave de sesión proporcionado por WCF para correlacionar el estado de la capa de aplicación (por ejemplo, una construcción del nivel de aplicación o un encabezado de correlación personalizado) o deshabilitar Proceso IIS de reciclaje para la aplicación hospedada.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Optimización del rendimiento en escenarios de nivel medio  
 Para obtener un rendimiento óptimo en un *escenario de nivel medio*: un servicio que llama a otros servicios en respuesta a los mensajes entrantes: crear una instancia del cliente del servicio WCF al servicio remoto una vez y reutilícelo en varias entrante solicitudes. Creación de instancias de los clientes de servicios WCF es una operación costosa relativa a hacer un servicio de llamada en una instancia de cliente preexistente, y escenarios de nivel medio generan ganancias de rendimiento distintas almacenando en caché los clientes remotos a través de solicitudes. Los clientes de servicios WCF son seguros para subprocesos, por lo que no es necesario sincronizar el acceso a un cliente a través de varios subprocesos.  
  
 Los escenarios de nivel medio también generan ganancias de rendimiento utilizando API asincrónicas generadas por la opción `svcutil /a`. El `/a` opción hace que el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar `BeginXXX/EndXXX` métodos para cada operación de servicio, lo que permite potencialmente de larga ejecución realizar las llamadas a servicios remotos en subprocesos en segundo plano.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF en escenarios multitarjeta o de varios nombres  
 Puede implementar servicios WCF dentro de una granja de servidores Web de IIS, donde un conjunto de equipos comparten un nombre común externo (como http://www.contoso.com) pero son direccionados individualmente por nombres de host diferentes (por ejemplo, http://www.contoso.com podría dirigir el tráfico a dos equipos diferentes denominado http://machine1.internal.contoso.com y http://machine2.internal.contoso.com). Este escenario de implementación es totalmente compatible con WCF, pero requiere configuración especial para el sitio Web de IIS que hospeda los servicios WCF para mostrar el nombre de host correcto (externo) en los metadatos del servicio (Web Services Description Language).  
  
 Para asegurarse de que el nombre de host correcto aparece en los metadatos del servicio que WCF genera, configure la identidad predeterminada para el sitio Web de IIS que hospeda los servicios WCF para usar un nombre de host explícito. Por ejemplo, los equipos que residen dentro de la granja www.contoso.com deben usar un enlace de sitio IIS de *: 80: www.contoso.com para HTTP y \*: 443:www.contoso.com para HTTPS.  
  
 Puede configurar los enlaces de sitio web de IIS utilizando el complemento de Microsoft Management Console (MMC).  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>Los grupos de aplicaciones que se ejecutan en contextos de usuario diferentes sobrescriben los ensamblados desde otras cuentas en la carpeta temporal  
 Para asegurarse de que los grupos de aplicaciones que se ejecutan en diferentes contextos de usuario no pueden sobrescribir los ensamblados desde otras cuentas en la carpeta de archivos [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] temporales, utilice identidades diferentes y carpetas temporales para las aplicaciones diferentes. Por ejemplo, si tiene dos aplicaciones virtuales /Application1 y / Application2, puede crear dos grupos de aplicaciones, A y B, con dos identidades diferentes. El grupo de aplicaciones A se puede ejecutar bajo una identidad de usuario (user1), mientras que el grupo de aplicaciones B se puede ejecutar bajo otra identidad de usuario (user2) y configurar /Application1 para que use A y /Application2 para que use B.  
  
 En el archivo Web.config, puede configurar la carpeta temporal mediante \< system.web/compilation/@tempFolder>. Para/Application1, puede ser "c:\tempForUser1" y application2 puede ser "c:\tempForUser2". Conceda el permiso de escritura correspondiente a estas carpetas para las dos identidades.  
  
 A continuación, user2 no puede cambiar la carpeta de generación de código para /application2 (bajo c:\tempForUser1).  
  
## <a name="enabling-asynchronous-processing"></a>Habilitar el procesamiento asincrónico  
 De forma predeterminada, los mensajes enviados a un servicio WCF hospedado en IIS 6.0 y versiones anteriores se procesan de forma sincrónica. ASP.NET llama a WCF en su propio subproceso (el subproceso de trabajo ASP.NET) y WCF usa otro subproceso para procesar la solicitud. WCF acapara el subproceso de trabajo de ASP.NET hasta que este complete su procesamiento. Esto lleva a un procesamiento sincrónico de las solicitudes. Procesamiento de solicitudes de forma asincrónica ofrece una mayor escalabilidad porque reduce el número de subprocesos necesarios para procesar una solicitud: WCF no acapara el subproceso de ASP.NET al procesar la solicitud. Uso del comportamiento asincrónico no se recomienda para equipos que ejecuten IIS 6.0 ya no existe forma de limitar las solicitudes entrantes que exponen al servidor a *denegación de servicio* ataques (DOS). A partir de IIS 7.0, se ha introducido un acelerador de solicitudes simultáneas: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Con este nuevo acelerador, el procesamiento asincrónico se puede usar de forma segura.  De forma predeterminada en IIS 7.0, se registran el controlador y el módulo asincrónicos. Si se ha deshabilitado, puede habilitar manualmente el procesamiento asincrónico de las solicitudes en el archivo Web.config de la aplicación. La configuración que se use depende de la configuración de `aspNetCompatibilityEnabled`. Si ha establecido `aspNetCompatibilityEnabled` en `false`, configure el objeto `System.ServiceModel.Activation.ServiceHttpModule` tal y como se muestra en el fragmento de código de configuración siguiente.  
  
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
 [Ejemplos de hospedaje de servicio](https://msdn.microsoft.com/library/f703a3f6-0fba-418a-a92f-7ce75ccfa47e)  
 [Características de hospedaje de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201276)
