---
title: Procedimiento para hospedar un servicio WCF en un servicio administrado de Windows
description: Obtenga información sobre cómo crear un servicio WCF que esté hospedado en un servicio de Windows. Esta opción de hospedaje está disponible en todas las versiones de Windows.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: 21d3dcb05e48154eb3f9f10d8308dc14bd046ae1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546346"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a>Procedimiento para hospedar un servicio WCF en un servicio administrado de Windows

En este tema se describen los pasos básicos necesarios para crear un servicio de Windows Communication Foundation (WCF) que esté hospedado en un servicio de Windows. El escenario se habilita mediante la opción de hospedaje del servicio administrado de Windows, que es un servicio WCF de ejecución prolongada hospedado fuera de Internet Information Services (IIS) en un entorno seguro que no está activado por mensaje. En su lugar, el sistema operativo controla la duración del servicio. Esta opción de hospedaje está disponible en todas las versiones de Windows.

Los servicios de Windows se pueden administrar con Microsoft.ManagementConsole.SnapIn en Microsoft Management Console (MMC) y pueden configurarse automáticamente para iniciar cuando el sistema arranca. Esta opción de hospedaje consiste en registrar el dominio de aplicación (AppDomain) que hospeda un servicio WCF como servicio administrado de Windows para que la duración del proceso del servicio se controle mediante el administrador de control de servicios (SCM) para servicios de Windows.

El código del servicio incluye una implementación del contrato de servicios, una clase de Windows Service y una clase del instalador. La clase de implementación de servicio, `CalculatorService` , es un servicio WCF. `CalculatorWindowsService` es un servicio de Windows. Para poder calificarse como servicio de Windows, la clase hereda de `ServiceBase` e implementa los métodos `OnStart` y `OnStop`. En `OnStart`, se crea <xref:System.ServiceModel.ServiceHost> para el tipo `CalculatorService` y se abre. En `OnStop`, el servicio se detiene y se elimina. El host también es responsable de proporcionar una dirección base al host de servicio, que se ha configurado en los valores de la aplicación. La clase del instalador, que hereda de <xref:System.Configuration.Install.Installer>, permite instalar el programa como un servicio de Windows mediante la herramienta Installutil.exe.

## <a name="construct-the-service-and-provide-the-hosting-code"></a>Construya el servicio y proporcione el código del hospedaje

1. Cree un nuevo proyecto de **aplicación de consola** de Visual Studio denominado **Service**.

2. Cambie el nombre del archivo Program.cs a Service.cs.

3. Cambie el espacio de nombres a `Microsoft.ServiceModel.Samples` .

4. Agregue referencias a los siguientes ensamblados:

    - System.ServiceModel.dll

    - System.ServiceProcess.dll

    - System.Configuration.Install.dll

5. Agregue las siguientes instrucciones Using a Service.cs.

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. Defina el contrato de servicio `ICalculator`, tal y como se muestra en el código siguiente.

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. Implemente el contrato de servicio en una clase denominada `CalculatorService`, tal como se muestra en el código siguiente.

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. Cree una nueva clase denominada `CalculatorWindowsService` que herede de la clase <xref:System.ServiceProcess.ServiceBase>. Agregue una variable local denominada `serviceHost` para hacer referencia a la instancia de <xref:System.ServiceModel.ServiceHost>. Defina el método `Main` que llama a `ServiceBase.Run(new CalculatorWindowsService)`.

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. Invalide el método <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> creando y abriendo una nueva instancia de <xref:System.ServiceModel.ServiceHost>, tal como se muestra en el código siguiente.

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. Invalide el método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> cerrando <xref:System.ServiceModel.ServiceHost>, tal como se muestra en el código siguiente.

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. Cree una nueva clase denominada `ProjectInstaller` que herede de <xref:System.Configuration.Install.Installer> y que esté marcada con el <xref:System.ComponentModel.RunInstallerAttribute> establecido en `true`. Esto permite a la herramienta Installutil.exe instalar el servicio de Windows.

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. Quite la clase `Service` generada al crear el proyecto.

13. Agregue un archivo de configuración de aplicación al proyecto. Reemplace el contenido del archivo por el XML de configuración siguiente.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.serviceModel>    <services>
          <!-- This section is optional with the new configuration model
               introduced in .NET Framework 4. -->
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"
                   behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
            <endpoint address=""
                      binding="wsHttpBinding"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />
          </service>
        </services>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceMetadata httpGetEnabled="true"/>
              <serviceDebug includeExceptionDetailInFaults="False"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>
      </system.serviceModel>
    </configuration>
    ```

     Haga clic con el botón derecho en el archivo App.config en el **Explorador de soluciones** y seleccione **propiedades**. En **Copiar en el directorio de salida** , seleccione **copiar si es posterior**.

     Este ejemplo especifica puntos de conexión explícitamente en el archivo de configuración. Si no agrega ningún punto de conexión al servicio, el tiempo de ejecución agregará los puntos de conexión predeterminados. En este ejemplo, dado que el servicio tiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> establecido en `true`, el servicio también tiene habilitada la publicación de metadatos. Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../samples/simplified-configuration-for-wcf-services.md).

## <a name="install-and-run-the-service"></a>Instale y ejecute el servicio.

1. Compile la solución para crear el ejecutable `Service.exe`.

2. Abra Símbolo del sistema para desarrolladores para Visual Studio y navegue hasta el directorio del proyecto. Escriba `installutil bin\service.exe` en el símbolo del sistema para instalar el servicio de Windows.

     Escriba `services.msc` en el símbolo del sistema para tener acceso al Administrador de control de servicios (SCM). El servicio de Windows debería aparecer en Servicios como "WCFWindowsServiceSample". El servicio WCF solo puede responder a los clientes si el servicio de Windows se está ejecutando. Para iniciar el servicio, haga clic con el botón secundario en el SCM y seleccione "iniciar" o escriba **net start WCFWindowsServiceSample** en el símbolo del sistema.

3. Si realiza cambios en el servicio, debe detenerlo primero y desinstalarlo. Para detener el servicio, haga clic con el botón secundario en el SCM y seleccione "STOP" o **escriba net stop WCFWindowsServiceSample** en el símbolo del sistema. Tenga en cuenta que si detiene el servicio de Windows y, a continuación, ejecuta un cliente, se produce una excepción <xref:System.ServiceModel.EndpointNotFoundException> cuando un cliente intenta tener acceso al servicio. Para desinstalar el tipo de servicio de Windows **InstallUtil/u bin\service.exe** en el símbolo del sistema.

## <a name="example"></a>Ejemplo

A continuación se muestra una lista completa del código que se usa en este tema:

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

Como la opción de "autohospedaje", el entorno de hospedaje de servicio de Windows requiere que algún código de hospedaje se escriba como parte de la aplicación. El servicio se implementa como una aplicación de consola y contiene su propio código de hospedaje. En otros entornos de hospedaje, como el del Servicio de activación de procesos de Windows (WAS) en Internet Information Services (IIS), no es necesario que los programadores escriban código de hospedaje.

## <a name="see-also"></a>Vea también

- [Configuración simplificada](../simplified-configuration.md)
- [Hospedaje en una aplicación administrada](hosting-in-a-managed-application.md)
- [Servicios de hospedaje](../hosting-services.md)
- [Características de hospedaje de Windows Server AppFabric](/previous-versions/appfabric/ee677189(v=azure.10))
