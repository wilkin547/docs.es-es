---
title: Cómo hospedar y ejecutar un servicio básico de Windows Communication Foundation
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 73633c2c6119204f2fb608b32ae794a2e07b27d0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747079"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Cómo hospedar y ejecutar un servicio básico de Windows Communication Foundation

Esta es la tercera de las seis tareas necesarias para crear una aplicación de Windows Communication Foundation (WCF). Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](getting-started-tutorial.md).

En este tema se describe cómo hospedar un servicio de Windows Communication Foundation (WCF) en una aplicación de consola. Este procedimiento consta de los siguientes pasos:

- Cree un proyecto de aplicación de consola para hospedar el servicio.

- Crear un host del servicio para el servicio.

- Habilitar el intercambio de metadatos

- Abrir el host del servicio.

En el ejemplo que se ofrece después del procedimiento, se proporciona una lista completa del código escrito en esta tarea.

## <a name="create-a-new-console-application-to-host-the-service"></a>Cree una nueva aplicación de consola para hospedar el servicio

1. Crear un nuevo proyecto de aplicación de consola en Visual Studio con el botón secundario en la solución introducción y seleccionando **agregar** > **nuevo proyecto**. En el **Agregar nuevo proyecto** cuadro de diálogo, en el lado izquierdo, seleccione el **Windows Desktop** categoría **Visual C#** o **Visual Basic**. Seleccione el **aplicación de consola (.NET Framework)** plantilla y, a continuación, denomine el proyecto **GettingStartedHost**.

2. Agregue una referencia al proyecto GettingStartedLib al proyecto GettingStartedHost. Haga doble clic en el **referencias** carpeta bajo el proyecto GettingStartedHost en **el Explorador de soluciones**y, a continuación, seleccione **Agregar referencia**. En el **Agregar referencia** cuadro de diálogo, seleccione **solución** en el lado izquierdo del cuadro de diálogo, seleccione GettingStartedLib en la sección central del cuadro de diálogo y, a continuación, elija **agregar**. Esto hace que los tipos definidos en GettingStartedLib estén disponibles para el proyecto GettingStartedHost.

3. Agregue una referencia a System.ServiceModel al proyecto GettingStartedHost. Haga clic en el **referencias** carpeta bajo el proyecto GettingStartedHost en **el Explorador de soluciones** y seleccione **Agregar referencia**. En el **Agregar referencia** cuadro de diálogo, seleccione **Framework** en el lado izquierdo del cuadro de diálogo **ensamblados**. Busque y seleccione **System.ServiceModel**y, a continuación, elija **Aceptar**. Guarde la solución seleccionando **archivo** > **guardar todo**.

## <a name="host-the-service"></a>El servicio de host

Abra el archivo Program.cs o Module.vb y escriba el código siguiente:

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
            // Step 1 Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 Create a ServiceHost instance
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 Start the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 Create a URI to serve as the base address
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted")

            ' Step 2 Create a ServiceHost instance
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
           Try

                ' Step 3 Add a service endpoint
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 Enable metadata exchange.
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 Start the service
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

**Paso 1** -crea una instancia de la clase de Uri que contenga la dirección base del servicio. Los servicios se identifican mediante una dirección URL que contiene una dirección base y un URI opcional. Se da formato a la dirección base como sigue: [transporte]://[nombre de equipo o dominio][:nº de puerto opcional]/[segmento opcional de URI]La dirección base para el servicio de calculadora usa el transporte HTTP, localhost, el puerto 8000 y el segmento de URI "GettingStarted".

**Paso 2** : crea una instancia de la <xref:System.ServiceModel.ServiceHost> clase para hospedar el servicio. El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.

**Paso 3** – crea un <xref:System.ServiceModel.Description.ServiceEndpoint> instancia. Un extremo de servicio consta de una dirección, un enlace y un contrato de servicio. Por tanto, el constructor <xref:System.ServiceModel.Description.ServiceEndpoint> toma el tipo de interfaz del contrato de servicio, un enlace y una dirección. El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio. El enlace usado en este ejemplo es <xref:System.ServiceModel.WSHttpBinding>, que es un enlace integrado que se emplea para conectarse a puntos de conexión que son conformes a las especificaciones de WS-*. Para obtener más información sobre los enlaces de WCF, vea [Información general de enlaces de Windows Communication Foundation](bindings-overview.md). La dirección se anexa a la dirección base para identificar el extremo. La dirección especificada en este código es "CalculatorService", por lo que es la dirección completa para el punto de conexión `"http://localhost:8000/GettingStarted/CalculatorService"`.

> [!IMPORTANT]
> Agregar un punto de conexión de servicio es opcional cuando se usa .NET Framework 4.0 o posterior. En estas versiones, si no se agrega ningún punto de conexión en el código o en la configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementada por el servicio. Para obtener más información sobre los puntos de conexión predeterminados, vea [Especificación de una dirección de punto de conexión](specifying-an-endpoint-address.md). Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](./samples/simplified-configuration-for-wcf-services.md).

**Paso 4** : habilitar el intercambio de metadatos. Los clientes usarán intercambio de metadatos para generar los servidores proxy que se usarán para llamar a las operaciones de servicio. Para habilitar el intercambio de metadatos, cree una instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, establezca su propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true` y agregue el comportamiento a la colección <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> de la instancia de <xref:System.ServiceModel.ServiceHost>.

**Paso 5** : abra el <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes. Observe que el código espera que el usuario presione ENTRAR. Si no lo hace, la aplicación se cerrará inmediatamente y el servicio se cerrará. Observe también que se usa un bloque try/catch. Una vez creada la instancia de <xref:System.ServiceModel.ServiceHost>, el resto del código se coloca en un bloque try/catch. Para obtener más información sobre cómo detectar de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost>, consulte [uso cierre y anulación para liberar los recursos del cliente WCF](samples/use-close-abort-release-wcf-client-resources.md)

> [!IMPORTANT]
> Cuando se agrega una biblioteca de servicios WCF, Visual Studio puede alojar automáticamente cuando se depura iniciando un host de servicio. Para evitar conflictos puede deshabilitar esta. 
> 1. Abra las propiedades de proyecto GettingStartedLib.
> 2. Vaya a **opciones WCF** y desactive la opción **iniciar cuando se depura el Host de servicio de WCF**.

## <a name="verify-the-service-is-working"></a>Compruebe que el servicio funciona.

1. Ejecutar la consola GettingStartedHost aplicación desde Visual Studio.

   El servicio se debe ejecutar con privilegios de administrador. Dado que Visual Studio se ha abierto con privilegios de administrador, GettingStartedHost también se ejecuta con privilegios de administrador. También puede abrir un nuevo símbolo del sistema mediante **ejecutar como administrador** y ejecute service.exe desde allí.

2. Abra un explorador web y vaya a la página de depuración del servicio en `http://localhost:8000/GettingStarted/`. **Tenga en cuenta. Final de la barra diagonal es significativo.**

## <a name="example"></a>Ejemplo

El siguiente ejemplo incluye el contrato de servicios y la implementación de los pasos anteriores del tutorial y hospeda el servicio en una aplicación de consola.

Para compilar esto con un compilador de línea de comandos, compile IService1.cs y Service1.cs en una biblioteca de clases que hace referencia a `System.ServiceModel.dll`. Compile Program.cs como una aplicación de consola.

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
        public interface ICalculator
        {
            [OperationContract]
            double Add(double n1, double n2);
            [OperationContract]
            double Subtract(double n1, double n2);
            [OperationContract]
            double Multiply(double n1, double n2);
            [OperationContract]
            double Divide(double n1, double n2);
        }
}
```

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

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
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 of the hosting procedure: Create ServiceHost
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 of the hosting procedure: Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 of the hosting procedure: Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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

Namespace GettingStartedLib

    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
    Public Interface ICalculator

        <OperationContract()> _
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
End Namespace
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

            ' Step 2 of the hosting procedure: Create ServiceHost
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
            Try

                ' Step 3 of the hosting procedure: Add a service endpoint.
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 of the hosting procedure: Enable metadata exchange.
                ' Enable metadata exchange
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

> [!NOTE]
> Servicios como este requieren permiso para registrar las direcciones HTTP en el equipo para la realización de escuchas. Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP. Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](feature-details/configuring-http-and-https.md). Cuando se ejecuta en Visual Studio, service.exe se debe ejecutar con privilegios de administrador.

## <a name="next-steps"></a>Pasos siguientes

Ahora, el servicio se está ejecutando. En la siguiente tarea, creará a un cliente de WCF.

> [!div class="nextstepaction"]
> [Cómo: Crear a un cliente WCF](how-to-create-a-wcf-client.md)

Para obtener información de solución de problemas, vea [Solución de problemas con el tutorial de introducción](troubleshooting-the-getting-started-tutorial.md).

## <a name="see-also"></a>Vea también

- [Introducción](samples/getting-started-sample.md)
- [Probar internamente](samples/self-host.md)
- [Servicios de hospedaje](hosting-services.md)
