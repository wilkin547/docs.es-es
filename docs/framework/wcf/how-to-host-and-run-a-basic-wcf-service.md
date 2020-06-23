---
title: 'Tutorial: hospedar y ejecutar un servicio de Windows Communication Foundation básico'
description: Obtenga información sobre cómo hospedar un servicio WCF en una aplicación de consola como parte de una serie de artículos que le ayudarán a empezar a crear una aplicación WCF.
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 5318991087e71430523681d601d3b38c4513027b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246135"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Tutorial: hospedar y ejecutar un servicio de Windows Communication Foundation básico

En este tutorial se describe el tercer de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).

La siguiente tarea para crear una aplicación WCF es hospedar un servicio WCF en una aplicación de consola. Un servicio WCF expone uno o más *puntos de conexión*, cada uno de los cuales expone una o más operaciones de servicio. Un punto de conexión de servicio especifica la siguiente información:

- Una dirección donde puede encontrar el servicio.
- Un enlace que contiene la información que describe cómo un cliente debe comunicarse con el servicio.
- Un contrato que define la funcionalidad que proporciona el servicio a sus clientes.

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Cree y configure un proyecto de aplicación de consola para hospedar un servicio WCF.
> - Agregue código para hospedar el servicio WCF.
> - Actualice el archivo de configuración.
> - Inicie el servicio WCF y compruebe que se está ejecutando.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Crear y configurar un proyecto de aplicación de consola para hospedar el servicio

1. Cree un proyecto de aplicación de consola en Visual Studio:

    1. En el menú **archivo** , seleccione **abrir**  >  **proyecto o solución** y busque la solución **gettingstarted** que creó anteriormente (*gettingstarted. sln*). seleccione **Open**(Abrir).

    2. En el menú **Ver** , seleccione **Explorador de soluciones**.

    3. En la ventana **Explorador de soluciones** , seleccione la solución **gettingstarted** (nodo superior) y, a continuación, seleccione **Agregar**  >  **nuevo proyecto** en el menú contextual.

    4. En la ventana **Agregar nuevo proyecto** , en el lado izquierdo, seleccione la categoría **escritorio de Windows** en **Visual C#** o **Visual Basic**.

    5. Seleccione la plantilla **aplicación de consola (.NET Framework)** y escriba *GettingStartedHost* para el **nombre**. Seleccione **Aceptar**.

2. Agregue una referencia en el proyecto **GettingStartedHost** al proyecto **GettingStartedLib** :

    1. En la ventana **Explorador de soluciones** , seleccione la carpeta **referencias** en el proyecto **GettingStartedHost** y, a continuación, seleccione **Agregar referencia** en el menú contextual.

    2. En el cuadro de diálogo **Agregar referencia** , en **proyectos** en el lado izquierdo de la ventana, seleccione **solución**.

    3. Seleccione **GettingStartedLib** en la sección central de la ventana y, a continuación, seleccione **Aceptar**.

       Esta acción hace que los tipos definidos en el proyecto **GettingStartedLib** estén disponibles para el proyecto **GettingStartedHost** .

3. Agregue una referencia en el proyecto **GettingStartedHost** al <xref:System.ServiceModel> ensamblado:

    1. En la ventana **Explorador de soluciones** , seleccione la carpeta **referencias** en el proyecto **GettingStartedHost** y, a continuación, seleccione **Agregar referencia** en el menú contextual.

    2. En la ventana **Agregar referencia** , en **ensamblados** en el lado izquierdo de la ventana, seleccione **marco de trabajo**.

    3. Seleccione **System. ServiceModel**y, después, haga clic en **Aceptar**.

    4. Guarde la solución seleccionando **archivo**  >  **guardar todo**.

## <a name="add-code-to-host-the-service"></a>Agregar código para hospedar el servicio

Para hospedar el servicio, agregue código para realizar los pasos siguientes:

1. Cree un URI para la dirección base.
2. Cree una instancia de clase para hospedar el servicio.
3. Cree un punto de conexión de servicio.
4. Habilitar el intercambio de metadatos
5. Abra el host del servicio para escuchar los mensajes entrantes.
  
Realice los siguientes cambios en el código:

1. Abra el archivo **Program.CS** o **Module1. VB** en el proyecto **GettingStartedHost** y reemplace su código por el código siguiente:

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb);

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```

    Para obtener información sobre cómo funciona este código, vea [pasos del programa de hospedaje de servicios](#service-hosting-program-steps).

2. Actualice las propiedades del proyecto:

   1. En la ventana **Explorador de soluciones** , seleccione la carpeta **GettingStartedHost** y, a continuación, seleccione **propiedades** en el menú contextual.

   2. En la página Propiedades de **GettingStartedHost** , seleccione la pestaña **aplicación** :

      - En el caso de los proyectos de C#, seleccione **GettingStartedHost. Program** en la lista **objeto de inicio** .

      - Para proyectos de Visual Basic, seleccione **Service. Program** en la lista **objeto de inicio** .

   3. En el menú **archivo** , seleccione **guardar todo**.

## <a name="verify-the-service-is-working"></a>Comprobar que el servicio funciona

1. Compile la solución y, a continuación, ejecute la aplicación de consola **GettingStartedHost** desde Visual Studio.

    El servicio se debe ejecutar con privilegios de administrador. Como abrió Visual Studio con privilegios de administrador, al ejecutar **GettingStartedHost** en Visual Studio, la aplicación se ejecuta también con privilegios de administrador. Como alternativa, puede abrir un nuevo símbolo del sistema como administrador (seleccione **más**  >  **Ejecutar como administrador** en el menú contextual) y ejecute **GettingStartedHost.exe** dentro de él.

2. Abra un explorador Web y vaya a la página del servicio en `http://localhost:8000/GettingStarted/CalculatorService` .

   > [!NOTE]
   > Los servicios como este requieren el permiso adecuado para registrar las direcciones HTTP en el equipo para realizar escuchas. Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP. Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](feature-details/configuring-http-and-https.md).

## <a name="service-hosting-program-steps"></a>Pasos del programa de hospedaje del servicio

Los pasos del código que agregó para hospedar el servicio se describen a continuación:

- **Paso 1**: cree una instancia de la `Uri` clase para que contenga la dirección base del servicio. Una dirección URL que contiene una dirección base tiene un URI opcional que identifica un servicio. La dirección base tiene el formato siguiente: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>` . La dirección base para el servicio de calculadora usa el transporte HTTP, localhost, el puerto 8000 y el segmento del URI, GettingStarted.

- **Paso 2**: crear una instancia de la <xref:System.ServiceModel.ServiceHost> clase, que se utiliza para hospedar el servicio. El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.

- **Paso 3**: crear una <xref:System.ServiceModel.Description.ServiceEndpoint> instancia de. Un extremo de servicio consta de una dirección, un enlace y un contrato de servicio. El <xref:System.ServiceModel.Description.ServiceEndpoint> constructor se compone del tipo de interfaz del contrato de servicio, un enlace y una dirección. El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio. El enlace para este ejemplo es <xref:System.ServiceModel.WSHttpBinding> , que es un enlace integrado y se conecta a puntos de conexión que cumplen con las especificaciones de WS-*. Para obtener más información sobre los enlaces de WCF, consulte [información general](bindings-overview.md)sobre los enlaces de WCF. La dirección se anexa a la dirección base para identificar el extremo. El código especifica la dirección como CalculatorService y la dirección completa del extremo como `http://localhost:8000/GettingStarted/CalculatorService` .

    > [!IMPORTANT]
    > Para .NET Framework versión 4 y versiones posteriores, la adición de un punto de conexión de servicio es opcional. Para estas versiones, si no agrega el código o la configuración, WCF agrega un extremo predeterminado para cada combinación de dirección base y contrato implementada por el servicio. Para obtener más información sobre los puntos de conexión predeterminados, vea [especificar una dirección de extremo](specifying-an-endpoint-address.md). Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [configuración simplificada](simplified-configuration.md) y [configuración simplificada para servicios WCF](samples/simplified-configuration-for-wcf-services.md).

- **Paso 4**: habilitar el intercambio de metadatos. Los clientes utilizan el intercambio de metadatos para generar servidores proxy para llamar a las operaciones de servicio. Para habilitar el intercambio de metadatos, cree una <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instancia de, establezca su <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> propiedad en `true` y agregue el `ServiceMetadataBehavior` objeto a la <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> colección de la <xref:System.ServiceModel.ServiceHost> instancia.

- **Paso 5**: Abra <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes. La aplicación espera a que presione **entrar**. Una vez que se crea una instancia de la aplicación <xref:System.ServiceModel.ServiceHost> , se ejecuta un bloque try/catch. Para obtener más información sobre cómo detectar de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost> , vea [usar Close y Abort para liberar los recursos de cliente de WCF](samples/use-close-abort-release-wcf-client-resources.md).

> [!IMPORTANT]
> Cuando se agrega una biblioteca de servicios WCF, Visual Studio la hospeda automáticamente si se inicia un host de servicio. Para evitar conflictos, puede evitar que Visual Studio hospede la biblioteca de servicios de WCF.
>
> 1. Seleccione el proyecto **GettingStartedLib** en **Explorador de soluciones** y elija **propiedades** en el menú contextual.
> 2. Seleccione **Opciones de WCF** y desactive **iniciar host de servicio WCF al depurar otro proyecto en la misma solución**.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha aprendido a:
> [!div class="checklist"]
>
> - Cree y configure un proyecto de aplicación de consola para hospedar un servicio WCF.
> - Agregue código para hospedar el servicio WCF.
> - Actualice el archivo de configuración.
> - Inicie el servicio WCF y compruebe que se está ejecutando.

Avance al siguiente tutorial para aprender a crear un cliente de WCF.

> [!div class="nextstepaction"]
> [Tutorial: crear un cliente WCF](how-to-create-a-wcf-client.md)
