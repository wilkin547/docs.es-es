---
title: 'Tutorial: Crear a un cliente de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 39f63b22257fb67d9caa5f84c886ead161508a33
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625824"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Tutorial: Crear a un cliente de Windows Communication Foundation

Este tutorial describe la cuarta de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general de los tutoriales, consulte [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).

La siguiente tarea para crear una aplicación de WCF es crear a un cliente mediante la recuperación de metadatos de un servicio WCF. Usar Visual Studio para agregar una referencia de servicio, que obtiene los metadatos del punto de conexión MEX del servicio. Visual Studio, a continuación, genera un archivo de código fuente administrado para un proxy de cliente en el idioma que haya elegido. También crea un archivo de configuración de cliente (*App.config*). Este archivo permite que la aplicación cliente para conectarse al servicio en un punto de conexión. 

> [!NOTE]
> Si se llama a un servicio WCF desde un proyecto de biblioteca de clases en Visual Studio, utilice el **Add Service Reference** característica para generar automáticamente un proxy y el archivo de configuración asociada. Sin embargo, dado que los proyectos de biblioteca de clases no usan este archivo de configuración, deberá agregar la configuración en el archivo de configuración generado para el *App.config* archivo para el archivo ejecutable que llama a la biblioteca de clases.

> [!NOTE]
> Como alternativa, use el [herramienta de utilidad de metadatos de ServiceModel](#servicemodel-metadata-utility-tool) en lugar de Visual Studio para generar el archivo de clase y la configuración de proxy.

La aplicación cliente usa la clase de proxy generada para comunicarse con el servicio. Este procedimiento se describe en [Tutorial: Usar un cliente](how-to-use-a-wcf-client.md).

En este tutorial aprenderá a:
> [!div class="checklist"]
> - Crear y configurar un proyecto de aplicación de consola para el cliente de WCF.
> - Agregue una referencia de servicio al servicio WCF para generar los archivos de clase y la configuración de proxy.

## <a name="create-a-windows-communication-foundation-client"></a>Crear a un cliente de Windows Communication Foundation

1. Cree un proyecto de aplicación de consola en Visual Studio: 

    1. Desde el **archivo** menú, seleccione **abierto** > **proyecto/solución** y vaya a la **GettingStarted** solución ha creado anteriormente (*GettingStarted.sln*). Seleccione **abierto**.

    2. Desde el **vista** menú, seleccione **el Explorador de soluciones**.

    3. En el **el Explorador de soluciones** ventana, seleccione el **GettingStarted** (nodo superior) de la solución y, a continuación, seleccione **agregar** > **denuevoproyecto** en el menú contextual. 
    
    4. En el **Agregar nuevo proyecto** ventana, en el lado izquierdo, seleccione el **Windows Desktop** categoría **Visual C#**  o **Visual Basic**. 

    5. Seleccione el **aplicación de consola (.NET Framework)** plantilla y escriba *GettingStartedClient* para el **nombre**. Seleccione **Aceptar**.

2. Agregue una referencia en el **GettingStartedClient** proyecto a la <xref:System.ServiceModel> ensamblado: 

    1. En el **el Explorador de soluciones** ventana, seleccione el **referencias** carpeta bajo la **GettingStartedClient** proyecto y, a continuación, seleccione **Agregar referencia** en el menú contextual. 

    2. En el **Agregar referencia** ventana, en **ensamblados** en el lado izquierdo de la ventana, seleccione **Framework**.
    
    3. Busque y seleccione **System.ServiceModel**y, a continuación, elija **Aceptar**. 

    4. Guarde la solución seleccionando **archivo** > **guardar todo**.

3. Agregue una referencia de servicio al servicio de calculadora:

   1. En el **el Explorador de soluciones** ventana, seleccione el **referencias** carpeta bajo la **GettingStartedClient** proyecto y, a continuación, seleccione **Add Service Reference**  en el menú contextual.

   2. En el **Add Service Reference** ventana, seleccione **Discover**.

      El servicio se inicia CalculatorService y Visual Studio lo muestra en el **servicios** cuadro.

   3. Seleccione **CalculatorService** para expandirlo y mostrar los contratos de servicio implementados por el servicio. Deje el valor predeterminado **Namespace** y elija **Aceptar**.

      Visual Studio agrega un elemento nuevo bajo el **Connected Services** carpeta en el **GettingStartedClient** proyecto. 

### <a name="servicemodel-metadata-utility-tool"></a>Herramienta de utilidad de metadatos de ServiceModel

Los ejemplos siguientes muestran cómo utilizar opcionalmente la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el archivo de clase de proxy. Esta herramienta genera el archivo de clase de proxy y el *App.config* archivo. Los ejemplos siguientes muestran cómo generar el proxy en C# y Visual Basic, respectivamente:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>Archivo de configuración de cliente

Después de crear el cliente, Visual Studio crea el **App.config** archivo de configuración en el **GettingStartedClient** proyecto, que debe ser similar al ejemplo siguiente:

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

En el [ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) sección, tenga en cuenta la [ \<punto de conexión >](../configure-apps/file-schema/wcf/endpoint-element.md) elemento. El **&lt;extremo&gt;** elemento define el punto de conexión que el cliente utiliza para tener acceso al servicio como sigue:
- Dirección: `http://localhost:8000/GettingStarted/CalculatorService`. Dirección del extremo.
- Contrato de servicio: `ServiceReference1.ICalculator`. El contrato de servicio controla la comunicación entre el cliente de WCF y el servicio. Este contrato generada por Visual Studio cuando usó su **Add Service Reference** función. Es básicamente una copia del contrato que define en el proyecto GettingStartedLib. 
- Enlace: <xref:System.ServiceModel.WSHttpBinding>. El enlace especifica HTTP como transporte, seguridad interoperable y otros detalles de configuración.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> - Crear y configurar un proyecto de aplicación de consola para el cliente de WCF.
> - Agregue una referencia de servicio al servicio WCF para generar los archivos de clase y la configuración de proxy para la aplicación cliente.

En el siguiente tutorial para aprender a usar al cliente generado.

> [!div class="nextstepaction"]
> [Tutorial: Usar a un cliente de WCF](how-to-use-a-wcf-client.md)
