---
title: Implementación de un servicio WFC hospedado en Internet Information Services
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 59f18d8487deb52f5ecb5b5c814ec9bdbc74e2cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Implementación de un servicio WFC hospedado en Internet Information Services
Desarrollar e implementar un servicio de Windows Communication Foundation (WCF) que se hospeda en Internet Information Services (IIS) consta de las siguientes tareas:  
  
-   Asegúrese de que IIS, ASP.NET, WCF y el componente de activación de WCF están correctamente instalados y registrados.  
  
-   Cree una nueva aplicación de IIS o reutilice una aplicación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] existente.  
  
-   Cree un archivo .svc para el servicio WCF.  
  
-   Implemente la implementación de servicio en la aplicación IIS.  
  
-   Configurar el servicio WCF.  
  
 Para obtener un tutorial detallado sobre cómo crear un servicio WCF hospedado en IIS, consulte [Cómo: hospedar un servicio WCF en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Asegurarse de que IIS, ASP.NET y WCF se instalen y registren correctamente  
 Deben instalarse WCF, IIS y ASP.NET para que los servicios WCF hospedado en IIS funcionen correctamente. Los procedimientos para instalar WCF (como parte de la [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET e IIS varían según la versión de sistema operativo que se va a usar. Para obtener más información acerca de cómo instalar WCF y la [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], consulte [instalador Web de Microsoft .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=201185). Puede encontrar instrucciones para la instalación de IIS en [Installing IIS 7 on Windows Vista and Windows 7](http://go.microsoft.com/fwlink/?LinkId=201188)(Instalación de IIS 7 en Windows Vista y Windows 7).  
  
 El proceso de instalación para el [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] registra automáticamente WCF con IIS si IIS ya está presente en el equipo. Si se instaló IIS después de la [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], se requiere un paso adicional para registrar WCF en IIS y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Puede hacer esto de la siguiente manera, en función de su sistema operativo:  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)], Windows 7, y [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: usar el [herramienta de registro de ServiceModel (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) herramienta para registrar WCF con IIS: para usar esta herramienta, escriba **ServiceModelReg.exe /i /x** en Visual Studio símbolo del sistema. Puede abrir este símbolo del sistema haciendo clic en el botón Inicio, y seleccionando **Todos los programas**, **Microsoft Visual Studio 2012**, **Visual Studio Tools**y **Símbolo del sistema de Visual Studio (2010)**.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]: instale el subcomponente Componentes de activación de Windows Communication Foundation de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. Para ello, en el Panel de Control, haga clic en **agregar o quitar programas** y, a continuación, **agregar\/quitar componentes de Windows**. Esto activa el **Asistente para componentes de Windows**.  
  
-   Windows 7:  
  
 Finalmente debe comprobar que ASP.NET se configura para utilizar la versión 4 de .NET Framework. Para ello, se ejecuta la herramienta ASPNET_Regiis con la opción –i. Para obtener más información, vea [herramienta de registro de IIS de ASP.NET](http://go.microsoft.com/fwlink/?LinkId=201186)  
  
## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Crear una nueva aplicación de IIS o reutilizar una aplicación de ASP.NET existente  
 Servicios WCF hospedados en IIS deben residir dentro de una aplicación de IIS. Puede crear una nueva aplicación de IIS para hospedar los servicios WCF exclusivamente. O bien, puede implementar un servicio WCF en una aplicación existente que ya hospeda [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] contenido (como páginas .aspx y servicios Web ASP.NET [ASMX]). Para obtener más información acerca de estas opciones, consulte la "hospedaje WCF Side-by-Side con ASP.NET" y "Servicios WCF de hospedaje en el modo de compatibilidad ASP.NET" secciones en [servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
 Observe que [!INCLUDE[iis601](../../../../includes/iis601-md.md)] y versiones posteriores reinician periódicamente una aplicación de programación orientada a objetos aislada. El valor predeterminado es de 1740 minutos. El valor máximo admitido son 71.582 minutos. Este reinicio se puede deshabilitar. Para obtener más información acerca de esta propiedad, vea la [PeriodicRestartTime](http://go.microsoft.com/fwlink/?LinkId=109968).  
  
## <a name="create-an-svc-file-for-the-wcf-service"></a>Cree un archivo .svc para el servicio de WCF.  
 Los servicios WCF hospedados en IIS se representan como archivos de contenido especial (archivos .svc) dentro de la aplicación de IIS. Este modelo es similar a la manera en que se representan las páginas ASMX dentro de una aplicación IIS como archivos .asmx. Un archivo .svc contiene una directiva de procesamiento específicas de WCF ([@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)) que permite que la infraestructura de hospedaje de WCF activar servicios hospedados en respuesta a los mensajes entrantes. La sintaxis más común para un archivo .svc se encuentra en la instrucción siguiente.  
  
```  
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>  
```  
  
 Consta de la directiva [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) y un atributo único, `Service`. El valor del atributo `Service` es el nombre del tipo de Common Language Runtime (CLR) de la implementación del servicio. El uso de esta directiva es básicamente equivalente a crear un host de servicio mediante el uso del código siguiente.  
  
```  
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );  
```  
  
 La configuración de hospedaje adicional, como el crear una lista de direcciones base, también puede realizarse. También puede utilizar un <xref:System.ServiceModel.Activation.ServiceHostFactory> personalizado para extender la directiva para el uso con soluciones de hospedaje personalizadas. Las aplicaciones de IIS que hospedan servicios WCF no son responsables de administrar la creación y duración de <xref:System.ServiceModel.ServiceHost> instancias. La infraestructura de hospedaje administrada de WCF crea necesaria <xref:System.ServiceModel.ServiceHost> instancia dinámicamente cuando se recibe la primera solicitud para el archivo .svc. La instancia no se libera hasta que se cierre explícitamente mediante código o cuando se recicle la aplicación.  
  
 Para obtener más información sobre la sintaxis de los archivos .svc, consulte [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).  
  
## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Implementación de la implementación de servicio en la aplicación IIS  
 Los servicios WCF hospedados en IIS usan el mismo modelo de compilación dinámica como [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]. Al igual que con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], puede implementar el código de implementación de servicios WCF hospedado por IIS de varias maneras en varias ubicaciones, como se indica a continuación:  
  
-   Como un archivo .dll precompilado ubicado en la caché global de ensamblados (GAC) o en el directorio \bin de la aplicación. Los binarios precompilados no se actualizan hasta que se implementa una nueva versión de la biblioteca de clases.  
  
-   Como archivos de código fuente sin compilar situados en el directorio \App_Code de la aplicación. Los archivos de código fuente ubicados en este directorio se solicitan dinámicamente al procesar la primera solicitud de la aplicación. Cualquier cambio en los archivos del directorio \App_Code hace que se recicle y recompile la aplicación al completo cuando se recibe la siguiente solicitud.  
  
-   Como código sin compilar colocado directamente en el archivo .svc. El código de implementación también se puede encontrar integrado en el archivo .svc del servicio, después de la @ServiceHost directiva. Los cambios realizados en el código integrado hacen que la aplicación se recicle y vuelva a compilarse cuando se recibe la siguiente solicitud.  
  
 Para obtener más información sobre la [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] modelo de compilación, consulte [información general sobre la compilación de ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94773).  
  
## <a name="configure-the-wcf-service"></a>Configuración del servicio WCF  
 Servicios WCF hospedados en IIS almacenan su configuración en el archivo Web.config de aplicaciones. Servicios hospedados en IIS utilizan los mismos elementos de configuración y sintaxis como servicios WCF hospedados fuera de IIS. Sin embargo, las siguientes restricciones son únicas del entorno de hospedaje de IIS:  
  
-   Direcciones base para servicios hospedados en IIS.  
  
-   Las aplicaciones de servicios de hospedaje de WCF fuera de IIS pueden controlar la dirección base de los servicios que hospedan pasando un conjunto de base de dirección URI para el <xref:System.ServiceModel.ServiceHost> constructor, o proporcionando un [ \<host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) elemento en el configuración del servicio. Los servicios hospedados en IIS no tienen la capacidad de controlar sus direcciones base; la dirección base de un servicio hospedado en IIS es la dirección de su archivo .svc.  
  
### <a name="endpoint-addresses-for-iis-hosted-services"></a>Direcciones de extremos para servicios hospedados en IIS  
 Cuando se hospeda en IIS, las direcciones de extremo siempre se considera que son relativas a la dirección del archivo .svc que representa al servicio. Por ejemplo, si la dirección base de un servicio WCF es http://localhost/Application1/MyService.svc con la siguiente configuración de punto de conexión.  
  
```xml  
<endpoint address="anotherEndpoint" .../>  
```  
  
 Esto proporciona un punto de conexión que se puede alcanzar en "http://localhost/Application1/MyService.svc/anotherEndpoint".  
  
 De forma similar, el elemento de configuración de punto de conexión que utiliza una cadena vacía como la dirección relativa proporciona un punto de conexión alcanzable en http://localhost/Application1/MyService.svc, que es la dirección base.  
  
```xml  
<endpoint address="" ... />  
```  
  
 Siempre debe utilizar direcciones de extremo relativas para los extremos de servicio hospedados en IIS. Proporcionar una dirección de extremo completa (por ejemplo, http://localhost/MyService.svc) puede provocar errores en la implementación del servicio si la dirección del extremo no apunta a la aplicación de IIS que hospeda el servicio que expone el extremo. El uso de direcciones de extremo relativas para servicios hospedados evita estos posibles conflictos.  
  
### <a name="available-transports"></a>Transportes disponibles  
 Los servicios WCF hospedados en IIS 5.1 y [!INCLUDE[iis601](../../../../includes/iis601-md.md)] están limitados a utilizar la comunicación basada en HTTP. En estas plataformas de IIS, configurar un servicio hospedado para utilizar un enlace no HTTP genera un error durante la activación del servicio. Para [!INCLUDE[iisver](../../../../includes/iisver-md.md)], entre los transportes admitidos se incluyen HTTP, Net.TCP, Net.Pipe, Net.MSMQ y msmq.formatname para la compatibilidad con versiones anteriores con respecto a aplicaciones MSMQ existentes.  
  
### <a name="http-transport-security"></a>Seguridad de transporte HTTP  
 Servicios WCF hospedados en IIS pueden hacer uso de HTTP (por ejemplo, HTTP y HTTPS esquemas de autenticación como básica, implícita y autenticación integrada de Windows) de seguridad de transporte siempre que el directorio virtual de IIS que contiene el servicio admita los Configuración. Los valores de seguridad de transporte HTTP de un enlace del extremo hospedado deben coincidir con los valores de seguridad de transporte del directorio virtual de IIS que lo contenga.  
  
 Por ejemplo, un extremo de WCF configurado para usar la autenticación implícita HTTP debe residir en un directorio virtual de IIS que también esté configurado para permitir la autenticación implícita HTTP. Las combinaciones de configuración de IIS y la configuración de punto de conexión WCF produce un error durante la activación del servicio.  
  
## <a name="see-also"></a>Vea también  
 [Hospedaje en Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Procedimientos recomendados de hospedaje de Internet Information Services](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
