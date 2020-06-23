---
title: 'Tutorial: creación de un cliente de Windows Communication Foundation'
description: Obtenga información sobre cómo crear un cliente mediante la recuperación de metadatos desde un servicio WCF como parte de una serie de artículos que le ayudarán a empezar a crear una aplicación WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: d5a2a2b5175c9e34eaf1dbaff20ac57f34117c4e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246329"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Tutorial: creación de un cliente de Windows Communication Foundation

En este tutorial se describe el cuarto de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).

La siguiente tarea para crear una aplicación WCF es crear un cliente mediante la recuperación de los metadatos de un servicio WCF. Use Visual Studio para agregar una referencia de servicio, que obtiene los metadatos del punto de conexión MEX del servicio. A continuación, Visual Studio genera un archivo de código fuente administrado para un proxy de cliente en el idioma elegido. También crea un archivo de configuración de cliente (*App.config*). Este archivo permite a la aplicación cliente conectarse al servicio en un extremo.

> [!NOTE]
> Si llama a un servicio WCF desde un proyecto de biblioteca de clases en Visual Studio, use la característica **Agregar referencia de servicio** para generar automáticamente un proxy y el archivo de configuración asociado. Sin embargo, dado que los proyectos de biblioteca de clases no usan este archivo de configuración, debe agregar la configuración del archivo de configuración generado al archivo *App.config* para el ejecutable que llama a la biblioteca de clases.

> [!NOTE]
> Como alternativa, use la [herramienta de utilidad de metadatos de ServiceModel](#servicemodel-metadata-utility-tool) en lugar de Visual Studio para generar la clase de proxy y el archivo de configuración.

La aplicación cliente usa la clase de proxy generada para comunicarse con el servicio. Este procedimiento se describe en [Tutorial: usar un cliente](how-to-use-a-wcf-client.md).

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Cree y configure un proyecto de aplicación de consola para el cliente de WCF.
> - Agregue una referencia de servicio al servicio WCF para generar la clase de proxy y los archivos de configuración.

## <a name="create-a-windows-communication-foundation-client"></a>Creación de un cliente de Windows Communication Foundation

1. Cree un proyecto de aplicación de consola en Visual Studio:

    1. En el menú **archivo** , seleccione **abrir**  >  **proyecto o solución** y busque la solución **gettingstarted** que creó anteriormente (*gettingstarted. sln*). seleccione **Open**(Abrir).

    2. En el menú **Ver** , seleccione **Explorador de soluciones**.

    3. En la ventana **Explorador de soluciones** , seleccione la solución **gettingstarted** (nodo superior) y, a continuación, seleccione **Agregar**  >  **nuevo proyecto** en el menú contextual.

    4. En la ventana **Agregar nuevo proyecto** , en el lado izquierdo, seleccione la categoría **escritorio de Windows** en **Visual C#** o **Visual Basic**.

    5. Seleccione la plantilla **aplicación de consola (.NET Framework)** y escriba *GettingStartedClient* para el **nombre**. Seleccione **Aceptar**.

2. Agregue una referencia en el proyecto **GettingStartedClient** al <xref:System.ServiceModel> ensamblado:

    1. En la ventana **Explorador de soluciones** , seleccione la carpeta **referencias** en el proyecto **GettingStartedClient** y, a continuación, seleccione **Agregar referencia** en el menú contextual.

    2. En la ventana **Agregar referencia** , en **ensamblados** en el lado izquierdo de la ventana, seleccione **marco de trabajo**.

    3. Busque y seleccione **System. ServiceModel**y, después, elija **Aceptar**.

    4. Guarde la solución seleccionando **archivo**  >  **guardar todo**.

3. Agregue una referencia de servicio al servicio de calculadora:

   1. En la ventana **Explorador de soluciones** , seleccione la carpeta **referencias** en el proyecto **GettingStartedClient** y, a continuación, seleccione **Agregar referencia de servicio** en el menú contextual.

   2. En la ventana **Agregar referencia de servicio** , seleccione **detectar**.

      El servicio CalculatorService se inicia y Visual Studio lo muestra en el cuadro **servicios** .

   3. Seleccione **CalculatorService** para expandirlo y mostrar los contratos de servicio implementados por el servicio. Deje el **espacio de nombres** predeterminado y elija **Aceptar**.

      Visual Studio agrega un nuevo elemento en la carpeta **servicios conectados** del proyecto **GettingStartedClient** .

### <a name="servicemodel-metadata-utility-tool"></a>Herramienta de utilidad de metadatos de ServiceModel

En los siguientes ejemplos se muestra cómo usar opcionalmente la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el archivo de clase de proxy. Esta herramienta genera el archivo de clase de proxy y el archivo de *App.config* . En los siguientes ejemplos se muestra cómo generar el proxy en C# y Visual Basic, respectivamente:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>Archivo de configuración del cliente

Después de crear el cliente, Visual Studio crea el archivo de configuración de **App.config** en el proyecto **GettingStartedClient** , que debe ser similar al ejemplo siguiente:

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

En la [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) sección, observe el [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) elemento. El elemento de ** &lt; punto de conexión &gt; ** define el extremo que el cliente usa para tener acceso al servicio de la siguiente manera:

- Dirección: `http://localhost:8000/GettingStarted/CalculatorService` . Dirección del extremo.
- Contrato de servicio: `ServiceReference1.ICalculator` . El contrato de servicio controla la comunicación entre el cliente de WCF y el servicio. Visual Studio generó este contrato cuando se usaba su **Agregar referencia de servicio** función. Básicamente es una copia del contrato que definió en el proyecto GettingStartedLib.
- Enlace: <xref:System.ServiceModel.WSHttpBinding> . El enlace especifica HTTP como el transporte, la seguridad interoperable y otros detalles de configuración.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha aprendido a:
> [!div class="checklist"]
>
> - Cree y configure un proyecto de aplicación de consola para el cliente de WCF.
> - Agregue una referencia de servicio al servicio WCF para generar la clase de proxy y los archivos de configuración para la aplicación cliente.

Avance al siguiente tutorial para aprender a usar el cliente generado.

> [!div class="nextstepaction"]
> [Tutorial: uso de un cliente WCF](how-to-use-a-wcf-client.md)
