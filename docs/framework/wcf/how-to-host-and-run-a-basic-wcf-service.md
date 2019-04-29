---
title: 'Tutorial: Hospedar y ejecutar un servicio básico de Windows Communication Foundation'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: ad9536b1f27ba3945bf76d0474de4825033a1e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929108"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Tutorial: Hospedar y ejecutar un servicio básico de Windows Communication Foundation

Este tutorial describen lo tercio de cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general de los tutoriales, consulte [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).

La siguiente tarea para crear una aplicación de WCF que se va a hospedar un servicio WCF en una aplicación de consola. Un servicio WCF que expone uno o varios *extremos*, cada uno de los cuales expone una o varias operaciones de servicio. Un extremo de servicio especifica la información siguiente: 
- Una dirección donde se encuentra el servicio.
- Un enlace que contiene la información que describe cómo un cliente debe comunicarse con el servicio. 
- Un contrato que define la funcionalidad que proporciona el servicio a sus clientes.

En este tutorial aprenderá a:
> [!div class="checklist"]
> - Crear y configurar un proyecto de aplicación de consola para hospedar un servicio WCF.
> - Agregue código para hospedar el servicio WCF.
> - Actualice el archivo de configuración.
> - Inicie el servicio WCF y compruebe se está ejecutando.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Crear y configurar un proyecto de aplicación de consola para hospedar el servicio

1. Cree un proyecto de aplicación de consola en Visual Studio: 
 
    1. Desde el **archivo** menú, seleccione **abierto** > **proyecto/solución** y vaya a la **GettingStarted** solución ha creado anteriormente (*GettingStarted.sln*). Seleccione **abierto**.

    2. Desde el **vista** menú, seleccione **el Explorador de soluciones**.
    
    3. En el **el Explorador de soluciones** ventana, seleccione el **GettingStarted** (nodo superior) de la solución y, a continuación, seleccione **agregar** > **denuevoproyecto** en el menú contextual. 

    4. En el **Agregar nuevo proyecto** ventana, en el lado izquierdo, seleccione el **Windows Desktop** categoría **Visual C#**  o **Visual Basic**. 

    5. Seleccione el **aplicación de consola (.NET Framework)** plantilla y escriba *GettingStartedHost* para el **nombre**. Seleccione **Aceptar**.

2. Agregue una referencia en el **GettingStartedHost** proyecto a la **GettingStartedLib** proyecto: 

    1. En el **el Explorador de soluciones** ventana, seleccione el **referencias** carpeta bajo la **GettingStartedHost** proyecto y, a continuación, seleccione **Agregar referencia** en el menú contextual. 

    2. En el **Agregar referencia** cuadro de diálogo, en **proyectos** en el lado izquierdo de la ventana, seleccione **solución**. 
 
    3. Seleccione **GettingStartedLib** en la sección central de la ventana y, a continuación, seleccione **Aceptar**. 

       Esta acción impide que los tipos definidos en el **GettingStartedLib** proyecto esté disponible para el **GettingStartedHost** proyecto.

3. Agregue una referencia en el **GettingStartedHost** proyecto a la <xref:System.ServiceModel> ensamblado: 

    1. En el **el Explorador de soluciones** ventana, seleccione el **referencias** carpeta bajo la **GettingStartedHost** proyecto y, a continuación, seleccione **Agregar referencia** en el menú contextual.
    
    2. En el **Agregar referencia** ventana, en **ensamblados** en el lado izquierdo de la ventana, seleccione **Framework**. 

    3. Seleccione **System.ServiceModel**y, a continuación, seleccione **Aceptar**. 
    
    4. Guarde la solución seleccionando **archivo** > **guardar todo**.

## <a name="add-code-to-host-the-service"></a>Agregue código para hospedar el servicio

Para hospedar el servicio, agregue código para realizar los pasos siguientes: 
   1. Crear un URI para la dirección base.
   2. Cree una instancia de clase para hospedar el servicio.
   3. Crear un extremo de servicio.
   4. Habilitar el intercambio de metadatos
   5. Abra el host de servicio para escuchar los mensajes entrantes.
  
Realice los cambios siguientes en el código:

1. Abra el **Program.cs** o **Module1.vb** de archivos en el **GettingStartedHost** del proyecto y reemplace su código con el código siguiente:

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
                    selfHost.Description.Behaviors.Add(smb)    ;

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
    
    Para obtener información sobre cómo funciona este código, consulte [servicio de hospedaje de los pasos del programa](#service-hosting-program-steps).

2. Actualice las propiedades del proyecto:

   1. En el **el Explorador de soluciones** ventana, seleccione el **GettingStartedHost** carpeta y, a continuación, seleccione **propiedades** en el menú contextual.

   2. En el **GettingStartedHost** página de propiedades, seleccione la **aplicación** pestaña:

      - Para C# proyectos, seleccionados **GettingStartedHost.Program** desde el **objeto Startup** lista.

      - Para proyectos de Visual Basic, seleccione **Service.Program** desde el **objeto Startup** lista.

   3. Desde el **archivo** menú, seleccione **guardar todo**.

## <a name="verify-the-service-is-working"></a>Compruebe que el servicio funciona.

1. Compile la solución y, a continuación, ejecute el **GettingStartedHost** consola de aplicación desde Visual Studio. 

    El servicio se debe ejecutar con privilegios de administrador. Dado que al abrir Visual Studio con privilegios de administrador, al ejecutar **GettingStartedHost** en Visual Studio, la aplicación se ejecuta con privilegios de administrador también. Como alternativa, puede abrir un nuevo símbolo del sistema como administrador (seleccione **más** > **ejecutar como administrador** en el menú contextual) y ejecute **GettingStartedHost.exe**  dentro de él.

2. Abra un explorador web y vaya a la página del servicio en `http://localhost:8000/GettingStarted/CalculatorService`.
   
   > [!NOTE]
   > Servicios como este requieren el permiso adecuado para registrar las direcciones HTTP en el equipo para realizar escuchas. Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP. Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](feature-details/configuring-http-and-https.md). 

## <a name="service-hosting-program-steps"></a>Pasos de programa de hospedaje de servicio

Los pasos en el código agregado para hospedar el servicio se describen como sigue:

- **Paso 1**: Cree una instancia de la `Uri` clase para contener la dirección base del servicio. Una dirección URL que contiene una dirección base tiene un URI opcional que identifica un servicio. La dirección base es el siguiente formato: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`. La dirección base para el servicio de calculadora usa el transporte HTTP, localhost, puerto 8000 y el segmento del URI, GettingStarted.

- **Paso 2**: Cree una instancia de la <xref:System.ServiceModel.ServiceHost> (clase), que se utiliza para hospedar el servicio. El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.

- **Paso 3**: Cree una instancia <xref:System.ServiceModel.Description.ServiceEndpoint>. Un extremo de servicio consta de una dirección, un enlace y un contrato de servicio. El <xref:System.ServiceModel.Description.ServiceEndpoint> constructor se compone de una dirección, un enlace y el tipo de interfaz de contrato de servicio. El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio. El enlace para este ejemplo es <xref:System.ServiceModel.WSHttpBinding>, que es un enlace integrado y se conecta a puntos de conexión que cumplen con WS-* especificaciones. Para obtener más información sobre los enlaces de WCF, vea [información general sobre los enlaces de WCF](bindings-overview.md). Anexe la dirección a la dirección base para identificar el punto de conexión. El código especifica la dirección como CalculatorService y la dirección completa para el punto de conexión como `http://localhost:8000/GettingStarted/CalculatorService`.

    > [!IMPORTANT]
    > Para .NET Framework versión 4 y versiones posteriores, la adición de un extremo de servicio es opcional. Para estas versiones, si no agrega el código o configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementado por el servicio. Para obtener más información sobre los puntos de conexión predeterminados, consulte [especificando una dirección de extremo](specifying-an-endpoint-address.md). Para obtener más información acerca de los puntos de conexión de forma predeterminada, los enlaces y comportamientos, consulte [configuración simplificada](simplified-configuration.md) y [configuración simplificada para los servicios WCF](samples/simplified-configuration-for-wcf-services.md).

- **Paso 4**: Habilitar el intercambio de metadatos Los clientes usan el intercambio de metadatos para generar a los servidores proxy para llamar a las operaciones de servicio. Para habilitar el intercambio de metadatos, cree un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> de instancia, establezca su <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> propiedad a `true`y agregue el `ServiceMetadataBehavior` objeto a la <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> colección de la <xref:System.ServiceModel.ServiceHost> instancia.

- **Paso 5**: Abra <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes. La aplicación espera a que presione **ENTRAR**. Una vez que crea una instancia de la aplicación <xref:System.ServiceModel.ServiceHost>, ejecuta un bloque try/catch. Para obtener más información sobre cómo detectar de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost>, consulte [uso cierre y anulación para liberar los recursos del cliente WCF](samples/use-close-abort-release-wcf-client-resources.md).

> [!IMPORTANT]
> Cuando se agrega una biblioteca de servicios WCF, Visual Studio se hospeda automáticamente si depura iniciando un host de servicio. Para evitar conflictos, puede impedir que Visual Studio hospeda la biblioteca de servicios WCF. 
> 1. Seleccione el **GettingStartedLib** proyecto **el Explorador de soluciones** y elija **propiedades** en el menú contextual.
> 2. Seleccione **opciones WCF** y desactive la opción **iniciar Host del servicio WCF al depurar otro proyecto en la misma solución**.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> - Crear y configurar un proyecto de aplicación de consola para hospedar un servicio WCF.
> - Agregue código para hospedar el servicio WCF.
> - Actualice el archivo de configuración.
> - Inicie el servicio WCF y compruebe se está ejecutando.

En el siguiente tutorial para aprender a crear a un cliente WCF.

> [!div class="nextstepaction"]
> [Tutorial: Crear a un cliente WCF](how-to-create-a-wcf-client.md)
