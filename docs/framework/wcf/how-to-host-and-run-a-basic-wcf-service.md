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
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184080"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Tutorial: Hospedar y ejecutar un servicio básico de Windows Communication Foundation

En este tutorial se describe la tercera de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a](getting-started-tutorial.md)las aplicaciones de Windows Communication Foundation .

La siguiente tarea para crear una aplicación WCF es hospedar un servicio WCF en una aplicación de consola. Un servicio WCF expone uno o varios *extremos,* cada uno de los cuales expone una o varias operaciones de servicio. Un punto de conexión de servicio especifica la siguiente información:

- Una dirección donde se puede encontrar el servicio.
- Un enlace que contiene la información que describe cómo un cliente debe comunicarse con el servicio.
- Un contrato que define la funcionalidad que el servicio proporciona a sus clientes.

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Crear y configurar un proyecto de aplicación de consola para hospedar un servicio WCF.
> - Agregue código para hospedar el servicio WCF.
> - Actualice el archivo de configuración.
> - Inicie el servicio WCF y compruebe que se está ejecutando.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Crear y configurar un proyecto de aplicación de consola para hospedar el servicio

1. Cree un proyecto de aplicación de consola en Visual Studio:

    1. En el menú **Archivo,** seleccione **Abrir** > **proyecto/solución** y vaya a la solución **GettingStarted** que creó anteriormente (*GettingStarted.sln*). Seleccione **Abrir**.

    2. En el menú **Ver** , seleccione **Explorador de soluciones**.

    3. En la ventana **Explorador** de soluciones, seleccione la solución **GettingStarted** (nodo superior) y, a continuación, seleccione **Agregar** > **nuevo proyecto** en el menú contextual.

    4. En la ventana **Agregar nuevo proyecto,** en el lado izquierdo, seleccione la categoría Escritorio de **Windows** en **Visual C** o **Visual Basic**.

    5. Seleccione la plantilla Aplicación de **consola (.NET Framework)** y escriba *GettingStartedHost* para **el nombre**. Seleccione **Aceptar**.

2. Agregue una referencia en el proyecto **GettingStartedHost** al proyecto **GettingStartedLib:**

    1. En la ventana **Explorador** de soluciones, seleccione la carpeta **Referencias** en el proyecto **GettingStartedHost** y, a continuación, seleccione **Agregar referencia** en el menú contextual.

    2. En el cuadro de diálogo **Agregar referencia,** en **Proyectos** en el lado izquierdo de la ventana, seleccione **Solución**.

    3. Seleccione **GettingStartedLib** en la sección central de la ventana y, a continuación, seleccione **Aceptar**.

       Esta acción hace que los tipos definidos en el **GettingStartedLib** proyecto disponible para el **GettingStartedHost** proyecto.

3. Agregue una referencia en el proyecto <xref:System.ServiceModel> **GettingStartedHost** al ensamblado:

    1. En la ventana **Explorador** de soluciones, seleccione la carpeta **Referencias** en el proyecto **GettingStartedHost** y, a continuación, seleccione **Agregar referencia** en el menú contextual.

    2. En la ventana **Agregar referencia,** en **Ensamblados** en el lado izquierdo de la ventana, seleccione **Framework**.

    3. Seleccione **System.ServiceModel**y, a continuación, seleccione **Aceptar**.

    4. Guarde la solución seleccionando **Guardar archivo** > **todo**.

## <a name="add-code-to-host-the-service"></a>Agregar código para hospedar el servicio

Para hospedar el servicio, agregue código para realizar los pasos siguientes:

1. Cree un URI para la dirección base.
2. Cree una instancia de clase para hospedar el servicio.
3. Cree un punto de conexión de servicio.
4. Habilitar el intercambio de metadatos
5. Abra el host de servicio para escuchar los mensajes entrantes.
  
Realice los siguientes cambios en el código:

1. Abra el **archivo Program.cs** o **Module1.vb** en el proyecto **GettingStartedHost** y reemplace su código por el código siguiente:

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

    Para obtener información sobre cómo funciona este código, consulte [Pasos](#service-hosting-program-steps)del programa de hospedaje de servicios.

2. Actualice las propiedades del proyecto:

   1. En la ventana Explorador de **soluciones,** seleccione la carpeta **GettingStartedHost** y, a continuación, seleccione **Propiedades** en el menú contextual.

   2. En la página de propiedades **GettingStartedHost,** seleccione la pestaña **Aplicación:**

      - En el caso de los proyectos de C, seleccione **GettingStartedHost.Program** en la lista **de objetos** de inicio.

      - Para proyectos de Visual Basic, seleccione **Service.Program** en la lista Objetos de **inicio.**

   3. En el menú **Archivo,** seleccione **Guardar todo**.

## <a name="verify-the-service-is-working"></a>Verifique que el servicio esté funcionando

1. Compile la solución y, a continuación, ejecute la aplicación de consola **GettingStartedHost** desde dentro de Visual Studio.

    El servicio debe ejecutarse con privilegios de administrador. Dado que abrió Visual Studio con privilegios de administrador, al ejecutar **GettingStartedHost** en Visual Studio, la aplicación también se ejecuta con privilegios de administrador. Como alternativa, puede abrir un nuevo símbolo del sistema como administrador (seleccione **Más** > **ejecución como administrador** en el menú contextual) y ejecutar **GettingStartedHost.exe** dentro de él.

2. Abra un navegador web y vaya a `http://localhost:8000/GettingStarted/CalculatorService`la página del servicio en .

   > [!NOTE]
   > Servicios como este requieren el permiso adecuado para registrar direcciones HTTP en el equipo para escucharlas. Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP. Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](feature-details/configuring-http-and-https.md).

## <a name="service-hosting-program-steps"></a>Pasos del programa de alojamiento de servicios

Los pasos del código que agregó para hospedar el servicio se describen de la siguiente manera:

- **Paso 1:** Cree una `Uri` instancia de la clase para contener la dirección base del servicio. Una dirección URL que contiene una dirección base tiene un URI opcional que identifica un servicio. La dirección base tiene el `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`siguiente formato: . La dirección base del servicio de calculadora utiliza el transporte HTTP, localhost, puerto 8000 y el segmento URI, GettingStarted.

- **Paso 2:** Cree una <xref:System.ServiceModel.ServiceHost> instancia de la clase, que se utiliza para hospedar el servicio. El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.

- **Paso 3**: <xref:System.ServiceModel.Description.ServiceEndpoint> Crear una instancia. Un extremo de servicio consta de una dirección, un enlace y un contrato de servicio. El <xref:System.ServiceModel.Description.ServiceEndpoint> constructor se compone del tipo de interfaz de contrato de servicio, un enlace y una dirección. El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio. El enlace para <xref:System.ServiceModel.WSHttpBinding>este ejemplo es , que es un enlace integrado y se conecta a los extremos que se ajustan a las especificaciones WS-*. Para obtener más información acerca de los enlaces WCF, vea [información general sobre enlaces WCF](bindings-overview.md). Anexe la dirección a la dirección base para identificar el punto de conexión. El código especifica la dirección como CalculatorService y la `http://localhost:8000/GettingStarted/CalculatorService`dirección completa para el punto de conexión como .

    > [!IMPORTANT]
    > Para .NET Framework versión 4 y versiones posteriores, agregar un punto de conexión de servicio es opcional. Para estas versiones, si no agrega el código o la configuración, WCF agrega un extremo predeterminado para cada combinación de dirección base y contrato implementado por el servicio. Para obtener más información acerca de los puntos de conexión predeterminados, consulte [Especificación de una dirección](specifying-an-endpoint-address.md)de punto de conexión . Para obtener más información acerca de los extremos, enlaces y comportamientos predeterminados, vea [Configuración simplificada](simplified-configuration.md) y [Configuración simplificada para servicios WCF.](samples/simplified-configuration-for-wcf-services.md)

- **Paso 4**: Habilitar el intercambio de metadatos. Los clientes usan el intercambio de metadatos para generar servidores proxy para llamar a las operaciones de servicio. Para habilitar el intercambio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> de metadatos, `true`cree una `ServiceMetadataBehavior` instancia, <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> establezca su <xref:System.ServiceModel.ServiceHost> <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> propiedad en y agregue el objeto a la colección de la instancia.

- **Paso 5** <xref:System.ServiceModel.ServiceHost> : Abrir para escuchar los mensajes entrantes. La aplicación espera a que pulse **Intro**. Después de <xref:System.ServiceModel.ServiceHost>que la aplicación crea una instancia, ejecuta un bloque try/catch. Para obtener más información acerca de <xref:System.ServiceModel.ServiceHost>cómo detectar de forma segura las excepciones producidas por , vea [usar cerrar y anular para liberar recursos](samples/use-close-abort-release-wcf-client-resources.md)de cliente WCF .

> [!IMPORTANT]
> Al agregar una biblioteca de servicios WCF, Visual Studio la hospeda automáticamente si la depura inicia iniciando un host de servicio. Para evitar conflictos, puede evitar que Visual Studio hosmeque la biblioteca de servicios WCF.
>
> 1. Seleccione el **GettingStartedLib** proyecto en **el Explorador** de soluciones y elija **propiedades** en el menú contextual.
> 2. Seleccione **Opciones de WCF** y desactive Iniciar host de servicio WCF al depurar otro proyecto en la misma **solución.**

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha aprendido a:
> [!div class="checklist"]
>
> - Crear y configurar un proyecto de aplicación de consola para hospedar un servicio WCF.
> - Agregue código para hospedar el servicio WCF.
> - Actualice el archivo de configuración.
> - Inicie el servicio WCF y compruebe que se está ejecutando.

Avance al siguiente tutorial para aprender a crear un cliente WCF.

> [!div class="nextstepaction"]
> [Tutorial: Crear un cliente WCF](how-to-create-a-wcf-client.md)
