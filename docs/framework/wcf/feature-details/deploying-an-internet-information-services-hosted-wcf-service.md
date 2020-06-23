---
title: Implementación de un servicio WFC hospedado en Internet Information Services
description: Obtenga información sobre las tareas necesarias para desarrollar e implementar un servicio WCF hospedado en IIS, empezando por comprobar la instalación de componentes.
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 886fd9b8d8cf3059b1fd8679c5dd89ee015f2adf
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245099"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Implementación de un servicio WFC hospedado en Internet Information Services

El desarrollo e implementación de un servicio de Windows Communication Foundation (WCF) que se hospeda en Internet Information Services (IIS) consta de las siguientes tareas:

- Asegúrese de que IIS, ASP.NET, WCF y el componente de activación de WCF se hayan instalado y registrado correctamente.

- Cree una nueva aplicación de IIS o reutilice una aplicación de ASP.NET existente.

- Cree un archivo. SVC para el servicio WCF.

- Implemente la implementación de servicio en la aplicación IIS.

- Configure el servicio WCF.

Para obtener un tutorial detallado sobre cómo crear un servicio WCF hospedado en IIS, consulte [How to: host a WCF Service in IIS](how-to-host-a-wcf-service-in-iis.md).

## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Asegurarse de que IIS, ASP.NET y WCF se instalen y registren correctamente

WCF, IIS y ASP.NET deben estar instalados para que los servicios WCF hospedados en IIS funcionen correctamente. Los procedimientos para instalar WCF (como parte de la .NET Framework), ASP.NET e IIS varían en función del sistema operativo. Para obtener más información sobre la instalación de WCF y el .NET Framework, consulte [instalación del .NET Framework para desarrolladores](../../install/guide-for-developers.md). Para instalar IIS en Windows 10, Abra **programas y características** en el **Panel de control** y seleccione **activar o desactivar las características de Windows**. En **características de Windows**, seleccione **Internet Information Services** y, a continuación, elija **Aceptar**.

![Características de Windows con IIS resaltado](./media/windows-features-iis.png)

Las instrucciones para instalar IIS en otros sistemas operativos se pueden encontrar en [instalación de IIS en Windows Vista y Windows 7](/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7) e [instalar IIS 8,5 en Windows Server 2012 R2](/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2).

El proceso de instalación de .NET Framework registra automáticamente WCF con IIS si IIS ya está presente en la máquina. Si IIS se instala después del .NET Framework, es necesario un paso adicional para registrar WCF con IIS y ASP.NET. Puede hacer esto de la siguiente manera, en función de su sistema operativo:

- Windows 7 y Windows Server 2003: Use la herramienta de [registro de ServiceModel (ServiceModelReg.exe)](../servicemodelreg-exe.md) para registrar WCF con IIS. Para usar esta herramienta, escriba **ServiceModelReg.exe/i/x** en el [símbolo del sistema para desarrolladores de Visual Studio](../../tools/developer-command-prompt-for-vs.md).

- Windows 7: por último, debe comprobar que ASP.NET está configurado para usar la versión 4 de .NET Framework o posterior. Para ello, ejecute la herramienta ASPNET_Regiis con la `–i` opción. Para obtener más información, consulte [ASP.net IIS registration Tool](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90)).

## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Crear una nueva aplicación de IIS o reutilizar una aplicación de ASP.NET existente

Los servicios WCF hospedados en IIS deben residir dentro de una aplicación IIS. Puede crear una nueva aplicación de IIS para hospedar servicios WCF exclusivamente. Como alternativa, puede implementar un servicio WCF en una aplicación existente que ya hospeda contenido de ASP.NET 2,0 (como páginas. aspx y servicios Web de ASP.NET [ASMX]). Para obtener más información acerca de estas opciones, consulte las secciones "hospedaje de WCF en paralelo con ASP.NET" y "hospedaje de servicios WCF en modo de compatibilidad de ASP.NET" en [servicios WCF y ASP.net](wcf-services-and-aspnet.md).

Tenga en cuenta que IIS 6,0 y versiones posteriores reinician periódicamente una aplicación de programación orientada a objetos aislada. El valor predeterminado es de 1740 minutos. El valor máximo admitido son 71.582 minutos. Este reinicio se puede deshabilitar. Para obtener más información sobre esta propiedad, vea [PeriodicRestartTime](https://docs.microsoft.com/previous-versions/iis/6.0-sdk/ms525914(v=vs.90)).

## <a name="create-an-svc-file-for-the-wcf-service"></a>Cree un archivo .svc para el servicio de WCF.

Los servicios WCF hospedados en IIS se representan como archivos de contenido especial (archivos. SVC) dentro de la aplicación IIS. Este modelo es similar a la manera en que se representan las páginas ASMX dentro de una aplicación IIS como archivos .asmx. Un archivo. SVC contiene una directiva de procesamiento específica de WCF ([ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md)) que permite a la infraestructura de hospedaje de WCF activar servicios hospedados en respuesta a los mensajes entrantes. La sintaxis más común para un archivo .svc se encuentra en la instrucción siguiente.

`<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>`

Consta de la Directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) y un atributo único, `Service` . El valor del atributo `Service` es el nombre del tipo de Common Language Runtime (CLR) de la implementación del servicio. El uso de esta directiva es básicamente equivalente a crear un host de servicio mediante el uso del código siguiente.

```csharp
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );
```

La configuración de hospedaje adicional, como el crear una lista de direcciones base, también puede realizarse. También puede utilizar un <xref:System.ServiceModel.Activation.ServiceHostFactory> personalizado para extender la directiva para el uso con soluciones de hospedaje personalizadas. Las aplicaciones IIS que hospedan servicios WCF no son responsables de administrar la creación y duración de <xref:System.ServiceModel.ServiceHost> las instancias de. La infraestructura de hospedaje de WCF administrada crea <xref:System.ServiceModel.ServiceHost> dinámicamente la instancia de necesaria cuando se recibe la primera solicitud para el archivo. SVC. La instancia no se libera hasta que se cierre explícitamente mediante código o cuando se recicle la aplicación.

Para obtener más información sobre la sintaxis de los archivos. SVC, vea [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md).

## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Implementación de la implementación de servicio en la aplicación IIS

Los servicios WCF hospedados en IIS usan el mismo modelo de compilación dinámica que ASP.NET 2,0. Al igual que con ASP.NET, puede implementar el código de implementación para servicios WCF hospedados en IIS de varias maneras en varias ubicaciones, como se indica a continuación:

- Como un archivo .dll precompilado ubicado en la caché global de ensamblados (GAC) o en el directorio \bin de la aplicación. Los binarios precompilados no se actualizan hasta que se implementa una nueva versión de la biblioteca de clases.

- Como archivos de código fuente no compilados ubicados en el directorio \ App_Code de la aplicación. Los archivos de código fuente ubicados en este directorio se solicitan dinámicamente al procesar la primera solicitud de la aplicación. Cualquier cambio en los archivos del directorio \App_Code hace que se recicle y recompile la aplicación al completo cuando se recibe la siguiente solicitud.

- Como código sin compilar colocado directamente en el archivo. SVC. El código de implementación también se puede ubicar en línea en el archivo. SVC del servicio, después de la \@ Directiva de ServiceHost. Los cambios realizados en el código integrado hacen que la aplicación se recicle y vuelva a compilarse cuando se recibe la siguiente solicitud.

Para obtener más información sobre el modelo de compilación de ASP.NET 2,0, consulte [información general sobre la compilación de ASP.net](https://docs.microsoft.com/previous-versions/aspnet/ms178466(v=vs.100)).

## <a name="configure-the-wcf-service"></a>Configuración del servicio WCF

Los servicios WCF hospedados en IIS almacenan su configuración en el archivo de Web.config de aplicaciones. Los servicios hospedados en IIS utilizan los mismos elementos de configuración y la misma sintaxis que los servicios WCF hospedados fuera de IIS. Sin embargo, las siguientes restricciones son únicas del entorno de hospedaje de IIS:

- Direcciones base para servicios hospedados en IIS.

- Las aplicaciones que hospedan servicios WCF fuera de IIS pueden controlar la dirección base de los servicios que hospedan pasando un conjunto de identificadores URI de dirección base al <xref:System.ServiceModel.ServiceHost> constructor o proporcionando un [\<host>](../../configure-apps/file-schema/wcf/host.md) elemento en la configuración del servicio. Los servicios hospedados en IIS no tienen la capacidad de controlar sus direcciones base; la dirección base de un servicio hospedado en IIS es la dirección de su archivo .svc.

### <a name="endpoint-addresses-for-iis-hosted-services"></a>Direcciones de extremos para servicios hospedados en IIS

Cuando se hospeda en IIS, las direcciones de extremo siempre se considera que son relativas a la dirección del archivo .svc que representa al servicio. Por ejemplo, si la dirección base de un servicio WCF es `http://localhost/Application1/MyService.svc` con la siguiente configuración de extremo:

```xml
<endpoint address="anotherEndpoint" />
```

Esto proporciona un extremo que se puede alcanzar en `http://localhost/Application1/MyService.svc/anotherEndpoint` .

Del mismo modo, el elemento de configuración de extremo que utiliza una cadena vacía como dirección relativa proporciona un extremo accesible en `http://localhost/Application1/MyService.svc` , que es la dirección base.

```xml
<endpoint address="" />
```

Siempre debe utilizar direcciones de extremo relativas para los extremos de servicio hospedados en IIS. Proporcionar una dirección de extremo completa (por ejemplo, `http://localhost/MyService.svc` ) puede provocar errores en la implementación del servicio si la dirección del extremo no señala a la aplicación IIS que hospeda el servicio que expone el extremo. El uso de direcciones de extremo relativas para servicios hospedados evita estos posibles conflictos.

### <a name="available-transports"></a>Transportes disponibles

Los servicios WCF hospedados en IIS 5,1 e IIS 6,0 están restringidos al uso de la comunicación basada en HTTP. En estas plataformas de IIS, configurar un servicio hospedado para utilizar un enlace no HTTP genera un error durante la activación del servicio. Para IIS 7,0, los transportes admitidos son HTTP, net. TCP, net. Pipe, net. MSMQ y MSMQ. FormatName para la compatibilidad con versiones anteriores de las aplicaciones MSMQ existentes.

### <a name="http-transport-security"></a>Seguridad de transporte HTTP

Los servicios WCF hospedados en IIS pueden utilizar la seguridad de transporte HTTP (por ejemplo, esquemas de autenticación HTTPS y HTTP, como Basic, Digest y autenticación integrada de Windows) siempre que el directorio virtual de IIS que contiene el servicio admita esos valores. Los valores de seguridad de transporte HTTP de un enlace del extremo hospedado deben coincidir con los valores de seguridad de transporte del directorio virtual de IIS que lo contenga.

Por ejemplo, un punto de conexión de WCF configurado para usar la autenticación HTTP implícita debe residir en un directorio virtual de IIS que también esté configurado para permitir la autenticación implícita de HTTP. Las combinaciones no coincidentes de la configuración de IIS y del punto de conexión de WCF producen un error durante la activación del servicio.

## <a name="see-also"></a>Vea también

- [Hospedaje en Internet Information Services](hosting-in-internet-information-services.md)
- [Procedimientos recomendados de hospedaje de Internet Information Services](internet-information-services-hosting-best-practices.md)
- [Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
