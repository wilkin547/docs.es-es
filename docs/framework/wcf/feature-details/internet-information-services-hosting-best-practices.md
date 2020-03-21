---
title: Procedimientos recomendados de hospedaje de Internet Information Services
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: 3be9d4c81f891ad898099ba9041a09b16388b7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184714"
---
# <a name="internet-information-services-hosting-best-practices"></a>Procedimientos recomendados de hospedaje de Internet Information Services
En este tema se describen algunos procedimientos recomendados para hospedar servicios de Windows Communication Foundation (WCF).  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementación de servicios WCF como DLL  
 Implementar un servicio WCF como un archivo DLL que se implementa en el directorio .bin de una aplicación web le permite reutilizar el servicio fuera del modelo de aplicación web, por ejemplo, en un entorno de prueba que puede no tener Internet Information Services (IIS) implementado.  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Hosts de servicio de aplicaciones hospedadas en IIS  
 No utilice las API de autohospedaje imperativas para crear nuevos hosts de servicio que escuchen en transportes de red no admitidos de forma nativa por el entorno de hospedaje de IIS (por ejemplo, IIS 6.0 para hospedar servicios TCP, porque la comunicación TCP no se admite de forma nativa en IIS 6.0). Éste enfoque no se recomienda. Los hosts de servicio creados de manera imperativa no se conocen dentro del entorno de hospedaje de IIS. El punto crítico es que el procesamiento realizado por servicios creados imperativamente no se tiene en cuenta por parte de IIS cuando determina si el grupo de aplicaciones de hospedaje está inactivo. El resultado es que las aplicaciones que tienen hosts de servicio creados de esta manera imperativa tienen un entorno de hospedaje de IIS que elimina de manera agresiva los procesos de host de IIS.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URI y extremos hospedados en IIS  
 Los puntos de conexión para un servicio hospedado en IIS se deberían configurar utilizando Identificadores uniformes de recursos relativos (URI), no direcciones absolutas. Esto garantiza que la dirección de punto de conexión cae dentro del conjunto de direcciones URI que pertenecen a la aplicación de hospedaje y asegura que la activación basada en mensaje ocurre tal y como se esperaba.  
  
## <a name="state-management-and-process-recycling"></a>Administración de estado y reciclaje de procesos  
 El entorno de hospedaje de IIS se optimiza para servicios que no mantienen el estado local en memoria. IIS recicla el proceso del host en respuesta a diversos eventos externos e internos, produciendo que se pierda cualquier estado volátil almacenado exclusivamente en memoria. Los servicios hospedados en IIS deberían almacenar su estado externo al proceso (por ejemplo, en una base de datos) o en una caché en memoria que se puede recrear con facilidad si tiene lugar un evento de reciclaje de aplicación.  
  
> [!NOTE]
> Los protocolos que WCF usa para la confiabilidad y la seguridad de la capa de mensajes hacen uso del estado volátil en memoria. Las sesiones confiables de WCF y las sesiones de seguridad pueden finalizar inesperadamente debido a los reciclajes de aplicaciones. Las aplicaciones hospedadas en IIS que hacen uso de estos protocolos deben depender de algo distinto de la clave de sesión proporcionada por WCF para correlacionar el estado de la capa de aplicación (por ejemplo, una construcción de capa de aplicación o un encabezado de correlación personalizado) o deshabilitar Reciclaje de procesos de IIS para la aplicación hospedada.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Optimización del rendimiento en escenarios de nivel medio  
 Para obtener un rendimiento óptimo en un *escenario de nivel intermedio,* un servicio que llama a otros servicios en respuesta a los mensajes entrantes, cree una instancia del cliente de servicio WCF en el servicio remoto una vez y reutilícelo en varias solicitudes entrantes. La creación de instancias de clientes de servicio WCF es una operación costosa en relación con realizar una llamada de servicio en una instancia de cliente preexistente y los escenarios de nivel intermedio producen mejoras de rendimiento distintas al almacenar en caché los clientes remotos entre las solicitudes. Los clientes de servicio WCF son seguros para subprocesos, por lo que no es necesario sincronizar el acceso a un cliente a través de varios subprocesos.  
  
 Los escenarios de nivel medio también generan ganancias de rendimiento utilizando API asincrónicas generadas por la opción `svcutil /a`. La `/a` opción hace que la herramienta de utilidad de `BeginXXX/EndXXX` metadatos de [ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) genere métodos para cada operación de servicio, lo que permite que se realicen llamadas potencialmente de larga ejecución a servicios remotos en subprocesos en segundo plano.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF en escenarios multitarjeta o de varios nombres  
 Puede implementar servicios WCF dentro de una granja de servidores web IIS, `http://www.contoso.com`donde un conjunto de equipos comparten un `http://www.contoso.com` nombre externo común (como `http://machine1.internal.contoso.com` `http://machine2.internal.contoso.com`) pero se tratan individualmente con diferentes nombres de host (por ejemplo, puede dirigir el tráfico a dos equipos diferentes denominados y ). Este escenario de implementación es totalmente compatible con WCF, pero requiere una configuración especial del sitio Web IIS que hospeda los servicios WCF para mostrar el nombre de host correcto (externo) en los metadatos del servicio (lenguaje de descripción de servicios web).  
  
 Para asegurarse de que el nombre de host correcto aparece en los metadatos de servicio que WCF genera, configure la identidad predeterminada para el sitio Web IIS que hospeda los servicios WCF para usar un nombre de host explícito. Por ejemplo, los equipos `www.contoso.com` que residen dentro de la granja de servidores deben usar un \*enlace de sitio IIS de *:80:www.contoso.com para HTTP y :443:www.contoso.com para HTTPS.  
  
 Puede configurar los enlaces de sitio web de IIS utilizando el complemento de Microsoft Management Console (MMC).  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>Los grupos de aplicaciones que se ejecutan en contextos de usuario diferentes sobrescriben los ensamblados desde otras cuentas en la carpeta temporal  
 Para asegurarse de que los grupos de aplicaciones que se ejecutan en contextos de usuario diferentes no pueden sobrescribir ensamblados de otras cuentas de la carpeta de archivos ASP.NET temporales, use diferentes identidades y carpetas temporales para diferentes aplicaciones. Por ejemplo, si tiene dos aplicaciones virtuales /Application1 y / Application2, puede crear dos grupos de aplicaciones, A y B, con dos identidades diferentes. El grupo de aplicaciones A se puede ejecutar bajo una identidad de usuario (user1), mientras que el grupo de aplicaciones B se puede ejecutar bajo otra identidad de usuario (user2) y configurar /Application1 para que use A y /Application2 para que use B.  
  
 En Web.config, puede configurar la \< system.web/compilation/@tempFolder carpeta temporal mediante>. Para /Application1, puede ser "c:-tempForUser1" y para application2 puede ser "c:-tempForUser2". Conceda el permiso de escritura correspondiente a estas carpetas para las dos identidades.  
  
 A continuación, user2 no puede cambiar la carpeta de generación de código para /application2 (bajo c:\tempForUser1).  
  
## <a name="enabling-asynchronous-processing"></a>Habilitar el procesamiento asincrónico  
 De forma predeterminada, los mensajes enviados a un servicio WCF hospedado en IIS 6.0 y versiones anteriores se procesan de forma sincrónica. ASP.NET llamadas a WCF en su propio subproceso (el subproceso de trabajo de ASP.NET) y WCF usa otro subproceso para procesar la solicitud. WCF acapara el subproceso de trabajo de ASP.NET hasta que este complete su procesamiento. Esto lleva a un procesamiento sincrónico de las solicitudes. El procesamiento de solicitudes de forma asincrónica permite una mayor escalabilidad porque reduce el número de subprocesos necesarios para procesar una solicitud: WCF no se mantiene en el subproceso ASP.NET mientras se procesa la solicitud. No se recomienda el uso de comportamiento asincrónico para equipos que ejecutan IIS 6.0 porque no hay manera de limitar las solicitudes entrantes que abren el servidor a ataques *de denegación de servicio* (DOS). A partir de IIS 7.0, se ha introducido un acelerador de solicitudes simultáneas: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Con este nuevo acelerador, el procesamiento asincrónico se puede usar de forma segura.  De forma predeterminada en IIS 7.0, se registran el controlador y el módulo asincrónicos. Si se ha deshabilitado, puede habilitar manualmente el procesamiento asincrónico de las solicitudes en el archivo Web.config de la aplicación. La configuración que se use depende de la configuración de `aspNetCompatibilityEnabled`. Si ha establecido `aspNetCompatibilityEnabled` en `false`, configure el objeto `System.ServiceModel.Activation.ServiceHttpModule` tal y como se muestra en el fragmento de código de configuración siguiente.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de hospedaje de servicio](../samples/hosting.md)
- [Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
