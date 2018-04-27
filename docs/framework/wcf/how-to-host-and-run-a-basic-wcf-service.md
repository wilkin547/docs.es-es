---
title: Procedimiento para hospedar y ejecutar un servicio básico de Windows Communication Foundation
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a13e5a0044c51700acce6b123688868443f635ae
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Procedimiento para hospedar y ejecutar un servicio básico de Windows Communication Foundation
Es la tercera de las seis tareas necesarias para crear una aplicación de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Para obtener información general de las seis de las tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.  
  
 Este tema describe cómo hospedar un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] en una aplicación de consola. Este procedimiento consta de los siguientes pasos:  
  
-   Cree un proyecto de aplicación de consola para hospedar el servicio.  
  
-   Crear un host del servicio para el servicio.  
  
-   Habilitar el intercambio de metadatos  
  
-   Abrir el host del servicio.  
  
 En el ejemplo que se ofrece después del procedimiento, se proporciona una lista completa del código escrito en esta tarea.  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a>Para crear una nueva aplicación de consola para hospedar el servicio  
  
1.  Crear un nuevo proyecto de aplicación de consola con el botón secundario en la solución introducción, seleccionar, **agregar**, **nuevo proyecto**. En el **Agregar nuevo proyecto** cuadro de diálogo en el lado izquierdo del cuadro de diálogo, seleccione **Windows** en **C#** o **VB**. En la sección central del cuadro de diálogo Seleccionar **aplicación de consola**. Asigne al proyecto el nombre GettingStartedHost.  
  
2.  Establezca la plataforma de destino del proyecto GettingStartedHost en .NET Framework 4.5 haciendo clic en **GettingStartedHost** en el Explorador de soluciones y seleccionando **propiedades**. En el cuadro desplegable etiquetado **.NET Framework de destino** seleccione **.NET Framework 4.5**. Establecer la plataforma de destino de un proyecto VB es algo diferente, en el cuadro de diálogo de propiedades de proyecto GettingStartedHost, haga clic en el **compilar** pestaña en el lado izquierdo de la pantalla y, a continuación, haga clic en el **avanzadas a compilar Opciones de** situado en la esquina inferior izquierda del cuadro de diálogo. A continuación, seleccione **.NET Framework 4.5** en el cuadro desplegable etiquetado **.NET Framework de destino**.  
  
     Establecer la plataforma de destino hará que [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] para volver a cargar la solución, presione **Aceptar** cuando se le solicite.  
  
3.  Agregue una referencia al proyecto GettingStartedLib al proyecto GettingStartedHost haciendo clic en el **referencias** carpeta bajo el proyecto GettingStartedHost en el Explorador de soluciones y seleccione **Agregar referencia** . En el **Agregar referencia** cuadro de diálogo, seleccione **solución** en el lado izquierdo del cuadro de diálogo y seleccione GettingStartedLib en la sección central del cuadro de diálogo y haga clic en **agregar**. Esto hace que los tipos definidos en GettingStartedLib estén disponibles para el proyecto GettingStartedHost.  
  
4.  Agregue una referencia a System.ServiceModel al proyecto GettingStartedHost haciendo clic en el **referencia** carpeta bajo el proyecto GettingStartedHost en el Explorador de soluciones y seleccione **agregar** Referencia. En el **Agregar referencia** diálogo seleccione **Framework** en el lado izquierdo del cuadro de diálogo. En el cuadro de texto Ensamblados de búsqueda, escriba `System.ServiceModel`. En la sección central del cuadro de diálogo Seleccionar **System.ServiceModel**, haga clic en el **agregar** y haga clic en el **cerrar** botón. Guarde la solución haciendo clic en el botón Guardar todo debajo del menú principal.  
  
### <a name="to-host-the-service"></a>Para hospedar el servicio  
  
-   Abra el archivo Program.cs o Module.vb y escriba el código siguiente:  
  
    ```csharp
    // program.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
    using GettingStartedLib;  
    using System.ServiceModel.Description;   
  
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
    'Module1.vb  
    Imports System  
    Imports System.ServiceModel  
    Imports System.ServiceModel.Description  
    Imports GettingStartedLibVB.GettingStartedLib  
  
    Module Service  
  
        Class Program  
            Shared Sub Main()  
                ' Step 1 Create a URI to serve as the base address  
                Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
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
  
    1.  Paso 1 - Crea una instancia de la clase Uri para contener la dirección base del servicio. Los servicios se identifican mediante una dirección URL que contiene una dirección base y un URI opcional. Da formato a la dirección base es como sigue: [Transporte] :// [nombre de equipo o dominio] [: opcional º de puerto] / [segmento opcional de URI] la dirección base para el servicio de calculadora usa el transporte HTTP, localhost, puerto 8000 y el segmento de URI "GettingStarted"  
  
    2.  Paso 2 - Crea una instancia de la clase <xref:System.ServiceModel.ServiceHost> para hospedar el servicio. El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.  
  
    3.  Paso 3-crea una <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` instancia. Un punto de conexión de servicio consta de una dirección, un enlace y un contrato de servicio. El <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` constructor toma, por tanto, el tipo de interfaz de contrato de servicio, un enlace y una dirección. El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio. El enlace usado en este ejemplo es <xref:System.ServiceModel.WSHttpBinding>, que es un enlace integrado que se emplea para conectarse a extremos que son conformes a las especificaciones de WS-*. Para obtener más información sobre los enlaces de WCF, vea [información general de enlaces de WCF](../../../docs/framework/wcf/bindings-overview.md). La dirección se anexa a la dirección base para identificar el punto de conexión. La dirección especificada en este código es "CalculatorService", por lo que es la dirección completa para el extremo `"http://localhost:8000/GettingStarted/CalculatorService"` agregar un extremo de servicio es opcional cuando se usa .NET Framework 4.0 o posterior. En estas versiones, si no se agrega ningún punto de conexión en el código o en la configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementada por el servicio. Para obtener más información sobre predeterminado vea extremos [al especificar una dirección de punto de conexión](../../../docs/framework/wcf/specifying-an-endpoint-address.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] los puntos de conexión, enlaces y comportamientos predeterminados, consulte [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
        > [!IMPORTANT]
        >  Agregar un punto de conexión de servicio es opcional cuando se usa .NET Framework 4.0 o posterior. En estas versiones, si no se agrega ningún punto de conexión en el código o en la configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementada por el servicio. Para obtener más información sobre predeterminado vea extremos [al especificar una dirección de punto de conexión](../../../docs/framework/wcf/specifying-an-endpoint-address.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] los puntos de conexión, enlaces y comportamientos predeterminados, consulte [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
    4.  Paso 4 - Habilita el intercambio de metadatos. Los clientes usarán intercambio de metadatos para generar los servidores proxy que se usarán para llamar a las operaciones de servicio. Para habilitar el intercambio de metadatos, cree un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> de la instancia, establézcala del <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> propiedad `true`y agregar el comportamiento a la <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  --> `System.ServiceModel.ServiceHost.Behaviors%2A` colección de la <xref:System.ServiceModel.ServiceHost> instancia.  
  
    5.  Paso 5 - Abre <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes. Observe que el código espera que el usuario presione ENTRAR. Si no lo hace, la aplicación se cerrará inmediatamente y el servicio se cerrará. Observe también que se usa un bloque try/catch. Una vez creada la instancia de <xref:System.ServiceModel.ServiceHost>, el resto del código se coloca en un bloque try/catch. Para obtener más información sobre la detección de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost>, consulte [evitar problemas con la instrucción Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)  
  
### <a name="to-verify-the-service-is-working"></a>Para comprobar si el servicio funciona  
  
1.  Ejecute la aplicación de consola GettingStartedHost desde [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]. Al ejecutarse en [!INCLUDE[wv](../../../includes/wv-md.md)] y sistemas operativos posteriores, el servicio se debe ejecutar con privilegios de administrador. Dado que Visual Studio se ejecuta con privilegios de administrador, GettingStartedHost también se ejecuta con privilegios de administrador. También puede iniciar un nuevo símbolo del sistema con privilegios de administrador y ejecutar service.exe desde allí.  
  
2.  Abra Internet Explorer y busque la página de depuración del servicio en `http://localhost:8000/GettingStarted/CalculatorService`.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo incluye el contrato de servicios y la implementación de los pasos anteriores del tutorial y hospeda el servicio en una aplicación de consola.  
  
 Para compilar esto con un compilador de línea de comandos, compile IService1.cs y Service1.cs en una biblioteca de clase hace referencia a `System.ServiceModel.dll`. Y compile Program.cs en una aplicación de consola.  
  
```csharp
// IService1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
//Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
using GettingStartedLib;  
using System.ServiceModel.Description;   
  
namespace GettingStartedHost  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Uri baseAddress = new Uri("http://localhost:8000/ServiceModelSamples/Service");  
  
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
'IService1.vb  
Imports System  
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
'Service1.vb  
Imports System  
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
'Module1.vb  
Imports System  
Imports System.ServiceModel  
Imports System.ServiceModel.Description  
Imports GettingStartedLibVB.GettingStartedLib  
  
Module Service  
  
    Class Program  
        Shared Sub Main()  
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
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
>  Servicios como este requieren permiso para registrar las direcciones HTTP en el equipo para la realización de escuchas. Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP. [!INCLUDE[crabout](../../../includes/crabout-md.md)] Cómo configurar las reservas de espacio de nombres, consulte [configurar HTTP y HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md). Cuando se ejecutan en Visual Studio, se debe ejecutar service.exe con privilegios de administrador.  
  
 Ahora, el servicio se está ejecutando. Continúe con [Cómo: crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Para obtener información de solución de problemas, consulte [el Tutorial de introducción de la solución de problemas](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)
