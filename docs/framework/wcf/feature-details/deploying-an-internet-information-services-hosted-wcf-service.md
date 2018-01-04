---
title: "Implementación de un servicio WFC hospedado en Internet Information Services"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 869e3b81e94e6efaa8d6cd9f4f021b52b6b43f48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Implementación de un servicio WFC hospedado en Internet Information Services
El desarrollo e implementación de un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que se hospeda en Internet Information Services (IIS) consta de las tareas siguientes:  
  
-   Asegurarse de que IIS, ASP.NET, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]y el componente de activación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se instalan y registran correctamente.  
  
-   Cree una nueva aplicación de IIS o reutilice una aplicación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] existente.  
  
-   Cree un archivo .svc para el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
-   Implemente la implementación de servicio en la aplicación IIS.  
  
-   Configure el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
 Para acceder a una guía detallada sobre la creación de un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedado en IIS, consulte [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Asegurarse de que IIS, ASP.NET y WCF se instalen y registren correctamente  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], IIS y ASP.NET se deben instalar para que los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS funcionen correctamente. Los procedimientos para instalar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (como parte de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET e IIS varían en función de la versión del sistema operativo que use. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo instalar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], consulte [Microsoft .NET Framework 4 (instalador web)](http://go.microsoft.com/fwlink/?LinkId=201185). Puede encontrar instrucciones para la instalación de IIS en [Installing IIS 7 on Windows Vista and Windows 7](http://go.microsoft.com/fwlink/?LinkId=201188)(Instalación de IIS 7 en Windows Vista y Windows 7).  
  
 El proceso de instalación del [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] registra automáticamente a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con IIS si IIS ya está presente en el equipo. Si IIS se instala después del [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], se requiere un paso adicional para registrar a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con IIS y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Puede hacer esto de la siguiente manera, en función de su sistema operativo:  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)], Windows 7, y [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: usar el [herramienta de registro de ServiceModel (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) herramienta para registrar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con IIS: para usar esta herramienta, escriba **ServiceModelReg.exe /i /x** en el símbolo del sistema de Visual Studio. Puede abrir este símbolo del sistema haciendo clic en el botón Inicio, y seleccionando **Todos los programas**, **Microsoft Visual Studio 2012**, **Visual Studio Tools**y **Símbolo del sistema de Visual Studio (2010)**.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]: instale el subcomponente Componentes de activación de Windows Communication Foundation de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. Para ello, en el Panel de Control, haga clic en **agregar o quitar programas** y, a continuación, **agregar\/quitar componentes de Windows**. Esto activa el **Asistente para componentes de Windows**.  
  
-   Windows 7:  
  
 Finalmente debe comprobar que ASP.NET se configura para utilizar la versión 4 de .NET Framework. Para ello, se ejecuta la herramienta ASPNET_Regiis con la opción –i. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Herramienta de registro de IIS en ASP.NET](http://go.microsoft.com/fwlink/?LinkId=201186)  
  
## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Crear una nueva aplicación de IIS o reutilizar una aplicación de ASP.NET existente  
 Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS deben residir dentro de una aplicación IIS. Puede crear una nueva aplicación IIS para hospedar exclusivamente servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] . O bien, puede implementar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en una aplicación existente que ya hospeda contenido de [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] (como páginas .aspx y servicios web ASP.NET [ASMX]). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] estas opciones, vea las secciones que describen el hospedaje de WCF en paralelo con ASP.NET y el de servicios WCF en el modo de compatibilidad de ASP.NET de [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
 Observe que [!INCLUDE[iis601](../../../../includes/iis601-md.md)] y versiones posteriores reinician periódicamente una aplicación de programación orientada a objetos aislada. El valor predeterminado es de 1740 minutos. El valor máximo admitido son 71.582 minutos. Este reinicio se puede deshabilitar. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] esta propiedad, consulte [PeriodicRestartTime](http://go.microsoft.com/fwlink/?LinkId=109968).  
  
## <a name="create-an-svc-file-for-the-wcf-service"></a>Cree un archivo .svc para el servicio de WCF.  
 Los servicios de[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS se representan como archivos de contenido especial (archivos .svc) dentro de la aplicación IIS. Este modelo es similar a la manera en que se representan las páginas ASMX dentro de una aplicación IIS como archivos .asmx. Un archivo .svc contiene una directiva de procesamiento específica de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]([@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)) que permite a la infraestructura de hospedaje de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] activar servicios hospedados en respuesta a los mensajes entrantes. La sintaxis más común para un archivo .svc se encuentra en la instrucción siguiente.  
  
```  
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>  
```  
  
 Consta de la directiva [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) y un atributo único, `Service`. El valor del atributo `Service` es el nombre del tipo de Common Language Runtime (CLR) de la implementación del servicio. El uso de esta directiva es básicamente equivalente a crear un host de servicio mediante el uso del código siguiente.  
  
```  
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );  
```  
  
 La configuración de hospedaje adicional, como el crear una lista de direcciones base, también puede realizarse. También puede utilizar un <xref:System.ServiceModel.Activation.ServiceHostFactory> personalizado para extender la directiva para el uso con soluciones de hospedaje personalizadas. Las aplicaciones IIS que hospedan servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no son responsables de administrar la creación y duración de las instancias de <xref:System.ServiceModel.ServiceHost> . La infraestructura de hospedaje de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] administrada crea dinámicamente la instancia de <xref:System.ServiceModel.ServiceHost> necesaria cuando se recibe la primera solicitud para el archivo .svc. La instancia no se libera hasta que se cierre explícitamente mediante código o cuando se recicle la aplicación.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] la sintaxis de los archivos .svc, vea [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).  
  
## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Implementación de la implementación de servicio en la aplicación IIS  
 Los servicios de[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS usan el mismo modelo de compilación dinámica que [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]. Al igual que con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], puede implementar el código de implementación para servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS de varias maneras en varias ubicaciones, tal y como sigue:  
  
-   Como un archivo .dll precompilado ubicado en la caché global de ensamblados (GAC) o en el directorio \bin de la aplicación. Los binarios precompilados no se actualizan hasta que se implementa una nueva versión de la biblioteca de clases.  
  
-   Como archivos de código fuente sin compilar situados en el directorio \App_Code de la aplicación. Los archivos de código fuente ubicados en este directorio se solicitan dinámicamente al procesar la primera solicitud de la aplicación. Cualquier cambio en los archivos del directorio \App_Code hace que se recicle y recompile la aplicación al completo cuando se recibe la siguiente solicitud.  
  
-   Como código sin compilar colocado directamente en el archivo .svc. El código de implementación también se puede encontrar integrado en el archivo .svc del servicio, después de la @ServiceHost directiva. Los cambios realizados en el código integrado hacen que la aplicación se recicle y vuelva a compilarse cuando se recibe la siguiente solicitud.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] el modelo de compilación de [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] , consulte [Información general sobre la compilación de ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94773).  
  
## <a name="configure-the-wcf-service"></a>Configuración del servicio WCF  
 Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS almacenan su configuración en el archivo Web.config de aplicaciones. Los servicios hospedados en IIS utilizan los mismos elementos de configuración y sintaxis que los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados fuera de IIS. Sin embargo, las siguientes restricciones son únicas del entorno de hospedaje de IIS:  
  
-   Direcciones base para servicios hospedados en IIS.  
  
-   Las aplicaciones que hospedan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicios fuera de IIS pueden controlar la dirección base de los servicios que hospedan pasando un conjunto de direcciones base URI para el <xref:System.ServiceModel.ServiceHost> constructor, o proporcionando un [ \<host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) elemento de la configuración del servicio. Los servicios hospedados en IIS no tienen la capacidad de controlar sus direcciones base; la dirección base de un servicio hospedado en IIS es la dirección de su archivo .svc.  
  
### <a name="endpoint-addresses-for-iis-hosted-services"></a>Direcciones de extremos para servicios hospedados en IIS  
 Cuando se hospeda en IIS, las direcciones de extremo siempre se considera que son relativas a la dirección del archivo .svc que representa al servicio. Por ejemplo, si la dirección base de un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es http://localhost/Application1/MyService.svc con la siguiente configuración de extremo.  
  
```xml  
<endpoint address="anotherEndpoint" .../>  
```  
  
 Esto proporciona un extremo que se puede alcanzar en "http://localhost/Application1/MyService.svc/anotherEndpoint".  
  
 De forma similar, el elemento de configuración de extremo que utiliza una cadena vacía como dirección relativa proporciona un extremo alcanzable en http://localhost/Application1/MyService.svc, que es la dirección base.  
  
```xml  
<endpoint address="" ... />  
```  
  
 Siempre debe utilizar direcciones de extremo relativas para los extremos de servicio hospedados en IIS. Proporcionar una dirección de extremo completa (por ejemplo, http://localhost/MyService.svc) puede llevar a errores en la implementación del servicio si la dirección del extremo no señala a la aplicación IIS que hospeda el servicio que expone el extremo. El uso de direcciones de extremo relativas para servicios hospedados evita estos posibles conflictos.  
  
### <a name="available-transports"></a>Transportes disponibles  
 Los de servicios[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS 5.1 e [!INCLUDE[iis601](../../../../includes/iis601-md.md)] están limitados a utilizar la comunicación basada en HTTP. En estas plataformas de IIS, configurar un servicio hospedado para utilizar un enlace no HTTP genera un error durante la activación del servicio. Para [!INCLUDE[iisver](../../../../includes/iisver-md.md)], entre los transportes admitidos se incluyen HTTP, Net.TCP, Net.Pipe, Net.MSMQ y msmq.formatname para la compatibilidad con versiones anteriores con respecto a aplicaciones MSMQ existentes.  
  
### <a name="http-transport-security"></a>Seguridad de transporte HTTP  
 Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS pueden utilizar la seguridad del transporte HTTP (por ejemplo, esquemas de autenticación HTTP y HTTPS, como la autenticación básica, implícita e integrada de Windows) siempre que el directorio virtual de IIS que contiene el servicio admita esos valores. Los valores de seguridad de transporte HTTP de un enlace del extremo hospedado deben coincidir con los valores de seguridad de transporte del directorio virtual de IIS que lo contenga.  
  
 Por ejemplo, un extremo de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configurado para utilizar la autenticación implícita de HTTP debe residir en un directorio virtual de IIS que también esté configurado para permitir la autenticación implícita HTTP. Las combinaciones que no coincidan de los valores de IIS y los valores de extremos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] producen un error durante la activación del servicio.  
  
## <a name="see-also"></a>Vea también  
 [Hospedaje en Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Procedimientos recomendados de hospedaje de Internet Information Services](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
