---
title: Procedimientos recomendados de hospedaje de Internet Information Services
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: 419b272ea3926d215ae2eed0add699af4101e648
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258769"
---
# <a name="internet-information-services-hosting-best-practices"></a>Procedimientos recomendados de hospedaje de Internet Information Services

En este tema se describen algunas prácticas recomendadas para hospedar servicios de Windows Communication Foundation (WCF).  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementación de servicios WCF como DLL  

 La implementación de un servicio WCF como un archivo DLL que se implementa en el directorio \bin de una aplicación web permite volver a usar el servicio fuera del modelo de aplicación Web, por ejemplo, en un entorno de prueba que puede no tener Internet Information Services (IIS) implementado.  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Hosts de servicio de aplicaciones hospedadas en IIS  

 No use las API de autohospedarias imperativas para crear nuevos hosts de servicio que escuchen en transportes de red no admitidos de forma nativa por el entorno de hospedaje de IIS (por ejemplo, IIS 6,0 para hospedar servicios TCP, ya que la comunicación TCP no se admite de forma nativa en IIS 6,0). No se recomienda este enfoque. Los hosts de servicio creados de manera imperativa no se conocen dentro del entorno de hospedaje de IIS. El punto crítico es que el procesamiento realizado por servicios creados imperativamente no se tiene en cuenta por parte de IIS cuando determina si el grupo de aplicaciones de hospedaje está inactivo. El resultado es que las aplicaciones que tienen hosts de servicio creados de esta manera imperativa tienen un entorno de hospedaje de IIS que elimina de manera agresiva los procesos de host de IIS.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URI y extremos hospedados en IIS  

 Los puntos de conexión para un servicio hospedado en IIS se deberían configurar utilizando Identificadores uniformes de recursos relativos (URI), no direcciones absolutas. Esto garantiza que la dirección de punto de conexión cae dentro del conjunto de direcciones URI que pertenecen a la aplicación de hospedaje y asegura que la activación basada en mensaje ocurre tal y como se esperaba.  
  
## <a name="state-management-and-process-recycling"></a>Administración de estado y reciclaje de procesos  

 El entorno de hospedaje de IIS se optimiza para servicios que no mantienen el estado local en memoria. IIS recicla el proceso del host en respuesta a diversos eventos externos e internos, produciendo que se pierda cualquier estado volátil almacenado exclusivamente en memoria. Los servicios hospedados en IIS deberían almacenar su estado externo al proceso (por ejemplo, en una base de datos) o en una caché en memoria que se puede recrear con facilidad si tiene lugar un evento de reciclaje de aplicación.  
  
> [!NOTE]
> Los protocolos que WCF usa para la confiabilidad y la seguridad del nivel de mensaje usan el estado volátil en memoria. Las sesiones confiables de WCF y las sesiones de seguridad pueden finalizar de forma inesperada debido a los reciclajes de la aplicación. Las aplicaciones hospedadas en IIS que hacen uso de estos protocolos deben depender de algo distinto de la clave de sesión proporcionada por WCF para correlacionar el estado de la capa de aplicación (por ejemplo, una construcción de capa de aplicación o un encabezado de correlación personalizado) o deshabilitar el reciclaje de procesos de IIS para la aplicación hospedada.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Optimización del rendimiento en escenarios de nivel medio  

 Para obtener un rendimiento óptimo en un *escenario de nivel intermedio*(un servicio que llama a otros servicios en respuesta a los mensajes entrantes), cree una instancia del cliente de servicio de WCF para el servicio remoto una vez y reutilícelo en varias solicitudes entrantes. La creación de instancias de clientes de servicio WCF es una operación costosa en relación con la realización de una llamada de servicio en una instancia de cliente existente, y los escenarios de nivel medio generan diferencias de rendimiento distintas al almacenar en caché los clientes remotos en todas las solicitudes. Los clientes del servicio WCF son seguros para subprocesos, por lo que no es necesario sincronizar el acceso a un cliente a través de varios subprocesos.  
  
 Los escenarios de nivel medio también generan ganancias de rendimiento utilizando API asincrónicas generadas por la opción `svcutil /a`. La `/a` opción hace que la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) genere `BeginXXX/EndXXX` métodos para cada operación de servicio, lo que permite realizar llamadas de ejecución prolongada a servicios remotos en subprocesos en segundo plano.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF en escenarios multitarjeta o de varios nombres  

 Puede implementar servicios WCF dentro de una granja de servidores Web de IIS, en la que un conjunto de equipos comparte un nombre externo común (como `http://www.contoso.com` ), pero que se direccionan individualmente mediante distintos nombres de host (por ejemplo, `http://www.contoso.com` puede dirigir el tráfico a dos equipos diferentes denominados `http://machine1.internal.contoso.com` y `http://machine2.internal.contoso.com` ). Este escenario de implementación es totalmente compatible con WCF, pero requiere una configuración especial del sitio web de IIS que hospeda los servicios WCF para mostrar el nombre de host (externo) correcto en los metadatos del servicio (lenguaje de descripción de servicios web).  
  
 Para asegurarse de que el nombre de host correcto aparece en los metadatos de servicio que genera WCF, configure la identidad predeterminada del sitio web de IIS que hospeda los servicios WCF para que use un nombre de host explícito. Por ejemplo, los equipos que residen dentro de la `www.contoso.com` granja deben usar un enlace de sitio de IIS de *: 80: www. contoso. com para http y \* : 443: www. contoso. com para HTTPS.  
  
 Puede configurar los enlaces de sitio web de IIS utilizando el complemento de Microsoft Management Console (MMC).  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>Los grupos de aplicaciones que se ejecutan en contextos de usuario diferentes sobrescriben los ensamblados desde otras cuentas en la carpeta temporal  

 Para asegurarse de que los grupos de aplicaciones que se ejecutan en distintos contextos de usuario no pueden sobrescribir ensamblados de otras cuentas en la carpeta Temporary ASP.NET files, utilice identidades y carpetas temporales diferentes para las diferentes aplicaciones. Por ejemplo, si tiene dos aplicaciones virtuales /Application1 y / Application2, puede crear dos grupos de aplicaciones, A y B, con dos identidades diferentes. El grupo de aplicaciones A se puede ejecutar bajo una identidad de usuario (user1), mientras que el grupo de aplicaciones B se puede ejecutar bajo otra identidad de usuario (user2) y configurar /Application1 para que use A y /Application2 para que use B.  
  
 En Web.config, puede configurar la carpeta temporal mediante \<system.web/compilation/@tempFolder> . En el caso de/application1, puede ser "c:\tempForUser1" y para Application2 puede ser "c:\tempForUser2". Conceda el permiso de escritura correspondiente a estas carpetas para las dos identidades.  
  
 A continuación, user2 no puede cambiar la carpeta de generación de código para /application2 (bajo c:\tempForUser1).  
  
## <a name="enabling-asynchronous-processing"></a>Habilitar el procesamiento asincrónico  

 De forma predeterminada, los mensajes enviados a un servicio WCF hospedado en IIS 6,0 y versiones anteriores se procesan de forma sincrónica. ASP.NET llama a WCF en su propio subproceso (el subproceso de trabajo de ASP.NET) y WCF usa otro subproceso para procesar la solicitud. WCF acapara el subproceso de trabajo de ASP.NET hasta que este complete su procesamiento. Esto lleva a un procesamiento sincrónico de las solicitudes. El procesamiento de solicitudes de forma asincrónica permite una mayor escalabilidad, ya que reduce el número de subprocesos necesarios para procesar una solicitud: WCF no mantiene el subproceso ASP.NET mientras procesa la solicitud. No se recomienda el uso del comportamiento asincrónico en equipos que ejecutan IIS 6,0 porque no hay ninguna manera de limitar las solicitudes entrantes que abren el servidor a ataques *de denegación de servicio* (dos). A partir de IIS 7.0, se ha introducido un acelerador de solicitudes simultáneas: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Con este nuevo acelerador, el procesamiento asincrónico se puede usar de forma segura.  De forma predeterminada en IIS 7.0, se registran el controlador y el módulo asincrónicos. Si se ha deshabilitado, puede habilitar manualmente el procesamiento asincrónico de las solicitudes en el archivo Web.config de la aplicación. La configuración que se use depende de la configuración de `aspNetCompatibilityEnabled`. Si ha establecido `aspNetCompatibilityEnabled` en `false`, configure el objeto `System.ServiceModel.Activation.ServiceHttpModule` tal y como se muestra en el fragmento de código de configuración siguiente.  
  
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

- [Ejemplos de hospedaje de servicio](../samples/hosting.md)
- [Características de hospedaje de Windows Server AppFabric](/previous-versions/appfabric/ee677189(v=azure.10))
