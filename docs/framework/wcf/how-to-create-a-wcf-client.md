---
title: 'Tutorial: Crear un cliente de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184109"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Tutorial: Crear un cliente de Windows Communication Foundation

En este tutorial se describe la cuarta de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a](getting-started-tutorial.md)las aplicaciones de Windows Communication Foundation .

La siguiente tarea para crear una aplicación WCF es crear un cliente mediante la recuperación de metadatos de un servicio WCF. Use Visual Studio para agregar una referencia de servicio, que obtiene los metadatos del extremo MEX del servicio. A continuación, Visual Studio genera un archivo de código fuente administrado para un proxy de cliente en el idioma que ha elegido. También crea un archivo de configuración de cliente (*App.config*). Este archivo permite a la aplicación cliente conectarse al servicio en un punto de conexión.

> [!NOTE]
> Si llama a un servicio WCF desde un proyecto de biblioteca de clases en Visual Studio, use la característica **Agregar referencia** de servicio para generar automáticamente un proxy y un archivo de configuración asociado. Sin embargo, dado que los proyectos de biblioteca de clases no usan este archivo de configuración, debe agregar la configuración del archivo de configuración generado al archivo *App.config* para el ejecutable que llama a la biblioteca de clases.

> [!NOTE]
> Como alternativa, use la herramienta Utilidad de metadatos de [ServiceModel](#servicemodel-metadata-utility-tool) en lugar de Visual Studio para generar la clase de proxy y el archivo de configuración.

La aplicación cliente usa la clase de proxy generada para comunicarse con el servicio. Este procedimiento se describe en [Tutorial: Usar un cliente](how-to-use-a-wcf-client.md).

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Crear y configurar un proyecto de aplicación de consola para el cliente WCF.
> - Agregue una referencia de servicio al servicio WCF para generar la clase de proxy y los archivos de configuración.

## <a name="create-a-windows-communication-foundation-client"></a>Crear un cliente de Windows Communication Foundation

1. Cree un proyecto de aplicación de consola en Visual Studio:

    1. En el menú **Archivo,** seleccione **Abrir** > **proyecto/solución** y vaya a la solución **GettingStarted** que creó anteriormente (*GettingStarted.sln*). Seleccione **Abrir**.

    2. En el menú **Ver** , seleccione **Explorador de soluciones**.

    3. En la ventana **Explorador** de soluciones, seleccione la solución **GettingStarted** (nodo superior) y, a continuación, seleccione **Agregar** > **nuevo proyecto** en el menú contextual.

    4. En la ventana **Agregar nuevo proyecto,** en el lado izquierdo, seleccione la categoría Escritorio de **Windows** en **Visual C** o **Visual Basic**.

    5. Seleccione la plantilla Aplicación de **consola (.NET Framework)** y escriba *GettingStartedClient* para **El nombre**. Seleccione **Aceptar**.

2. Agregue una referencia en el proyecto <xref:System.ServiceModel> **GettingStartedClient** al ensamblado:

    1. En el **Explorador** de soluciones ventana, seleccione el **referencias** carpeta en el **GettingStartedClient** proyecto y, a continuación, seleccione **agregar referencia** en el menú contextual.

    2. En la ventana **Agregar referencia,** en **Ensamblados** en el lado izquierdo de la ventana, seleccione **Framework**.

    3. Busque y seleccione **System.ServiceModel**y, a continuación, elija **Aceptar**.

    4. Guarde la solución seleccionando **Guardar archivo** > **todo**.

3. Agregue una referencia de servicio al servicio de calculadora:

   1. En el **Explorador** de soluciones ventana, seleccione el **referencias** carpeta en el **GettingStartedClient** proyecto y, a continuación, seleccione **agregar referencia** de servicio en el menú contextual.

   2. En la ventana **Agregar referencia de servicio,** seleccione **Detectar**.

      El servicio CalculatorService se inicia y Visual Studio lo muestra en el cuadro **Servicios.**

   3. Seleccione **CalculatorService** para expandirlo y mostrar los contratos de servicio implementados por el servicio. Deje el **espacio de nombres** predeterminado y elija **Ok**.

      Visual Studio agrega un nuevo elemento en la carpeta **Servicios conectados** en el **GettingStartedClient** proyecto.

### <a name="servicemodel-metadata-utility-tool"></a>Herramienta de utilidad de metadatos de ServiceModel

En los ejemplos siguientes se muestra cómo usar opcionalmente la herramienta Delación de metadatos de [ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el archivo de clase de proxy. Esta herramienta genera el archivo de clase de proxy y el archivo *App.config.* En los ejemplos siguientes se muestra cómo generar el proxy en C- y Visual Basic, respectivamente:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>Archivo de configuración del cliente

Después de crear el cliente, Visual Studio crea el archivo de configuración **App.config** en el proyecto **GettingStartedClient,** que debe ser similar al ejemplo siguiente:

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

En la [ \<](../configure-apps/file-schema/wcf/endpoint-element.md) [ \<sección system.serviceModel>,](../configure-apps/file-schema/wcf/system-servicemodel.md) observe el extremo>elemento. El elemento ** &lt;endpoint&gt; ** define el punto de conexión que el cliente utiliza para tener acceso al servicio de la siguiente manera:

- Dirección: `http://localhost:8000/GettingStarted/CalculatorService`. Dirección del extremo.
- Contrato de `ServiceReference1.ICalculator`servicio: . El contrato de servicio controla la comunicación entre el cliente WCF y el servicio. Visual Studio generó este contrato cuando usó su **función Agregar referencia** de servicio. Es esencialmente una copia del contrato que definió en el gettingStartedLib proyecto.
- Encuadernación: <xref:System.ServiceModel.WSHttpBinding>. El enlace especifica HTTP como el transporte, la seguridad interoperable y otros detalles de configuración.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha aprendido a:
> [!div class="checklist"]
>
> - Crear y configurar un proyecto de aplicación de consola para el cliente WCF.
> - Agregue una referencia de servicio al servicio WCF para generar la clase de proxy y los archivos de configuración para la aplicación cliente.

Vaya al siguiente tutorial para aprender a usar el cliente generado.

> [!div class="nextstepaction"]
> [Tutorial: Usar un cliente WCF](how-to-use-a-wcf-client.md)
