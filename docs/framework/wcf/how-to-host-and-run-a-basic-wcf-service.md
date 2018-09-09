---
title: Procedimiento para hospedar y ejecutar un servicio básico de Windows Communication Foundation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: e2bf16bd07c7ac9d918a4ae95d7f4aa185d436ec
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227186"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Procedimiento para hospedar y ejecutar un servicio básico de Windows Communication Foundation
Esta es la tercera de las seis tareas necesarias para crear una aplicación de Windows Communication Foundation (WCF). Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 En este tema se describe cómo hospedar un servicio de Windows Communication Foundation (WCF) en una aplicación de consola. Este procedimiento consta de los siguientes pasos:  
  
-   Cree un proyecto de aplicación de consola para hospedar el servicio.  
  
-   Crear un host del servicio para el servicio.  
  
-   Habilitar el intercambio de metadatos  
  
-   Abrir el host del servicio.  
  
 En el ejemplo que se ofrece después del procedimiento, se proporciona una lista completa del código escrito en esta tarea.  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a>Para crear una nueva aplicación de consola para hospedar el servicio  
  
1.  Cree un proyecto de aplicación de consola haciendo clic con el botón derecho en la solución Introducción, y seleccionando **Agregar**, **Nuevo proyecto**. En la parte izquierda del cuadro de diálogo **Agregar nuevo proyecto**, seleccione **Windows** en **C#** o **VB**. En la sección central del cuadro de diálogo, seleccione **Aplicación de consola**. Asigne al proyecto el nombre GettingStartedHost.  
  
2.  Establezca la plataforma de destino del proyecto GettingStartedHost en .NET Framework 4.5 haciendo clic con el botón derecho en **GettingStartedHost** en el Explorador de soluciones y seleccionando **Propiedades**. En el cuadro desplegable **Plataforma de destino**, seleccione **.NET Framework 4.5**. Establecer la plataforma de destino de un proyecto de VB es algo diferente; en el cuadro de diálogo de propiedades del proyecto GettingStartedHost, haga clic en la pestaña **Compilar** en el lado izquierdo de la pantalla y, después, haga clic en el botón **Opciones de compilación avanzadas** en la esquina izquierda inferior del cuadro de diálogo. Después, seleccione **.NET Framework 4.5** en el cuadro desplegable con la etiqueta **Plataforma de destino**.  
  
     Establecer la plataforma de destino hará que [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] recargue la solución; haga clic en **Aceptar** cuando se le pida.  
  
3.  Agregue una referencia al proyecto GettingStartedLib al proyecto GettingStartedHost haciendo clic con el botón derecho en la carpeta **Referencias** bajo el proyecto GettingStartedHost en el Explorador de soluciones y seleccione **Agregar referencia**. En el lado izquierdo del cuadro de diálogo **Agregar referencia**, seleccione **Solución** y seleccione GettingStartedLib en la sección central del cuadro de diálogo y haga clic en **Agregar**. Esto hace que los tipos definidos en GettingStartedLib estén disponibles para el proyecto GettingStartedHost.  
  
4.  Agregue una referencia a System.ServiceModel al proyecto GettingStartedHost haciendo clic con el botón derecho en la carpeta **Referencia** bajo el proyecto GettingStartedHost en el Explorador de soluciones y seleccione **Agregar referencia**. En el lado izquierdo del cuadro de diálogo **Agregar referencia**, seleccione **Framework**. En el cuadro de texto Ensamblados de búsqueda, escriba `System.ServiceModel`. En la sección central del cuadro de diálogo, seleccione **System.ServiceModel**, haga clic en el botón **Agregar** y después en el botón **Cerrar**. Guarde la solución haciendo clic en el botón Guardar todo debajo del menú principal.  
  
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
  
    1.  Paso 1 - Crea una instancia de la clase Uri para contener la dirección base del servicio. Los servicios se identifican mediante una dirección URL que contiene una dirección base y un URI opcional. Se da formato a la dirección base como sigue: [transporte]://[nombre de equipo o dominio][:nº de puerto opcional]/[segmento opcional de URI]La dirección base para el servicio de calculadora usa el transporte HTTP, localhost, el puerto 8000 y el segmento de URI "GettingStarted".  
  
    2.  Paso 2 - Crea una instancia de la clase <xref:System.ServiceModel.ServiceHost> para hospedar el servicio. El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.  
  
    3.  Paso 3 - Crea una nueva instancia de <xref:System.ServiceModel.Description.ServiceEndpoint>. Un punto de conexión de servicio consta de una dirección, un enlace y un contrato de servicio. Por tanto, el constructor <xref:System.ServiceModel.Description.ServiceEndpoint> toma el tipo de interfaz del contrato de servicio, un enlace y una dirección. El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio. El enlace usado en este ejemplo es <xref:System.ServiceModel.WSHttpBinding>, que es un enlace integrado que se emplea para conectarse a extremos que son conformes a las especificaciones de WS-*. Para obtener más información sobre los enlaces de WCF, vea [Información general de enlaces de Windows Communication Foundation](../../../docs/framework/wcf/bindings-overview.md). La dirección se anexa a la dirección base para identificar el punto de conexión. La dirección especificada en este código es "CalculatorService", por lo que es la dirección completa para el punto de conexión `"http://localhost:8000/GettingStarted/CalculatorService"`.  
  
        > [!IMPORTANT]
        >  Agregar un punto de conexión de servicio es opcional cuando se usa .NET Framework 4.0 o posterior. En estas versiones, si no se agrega ningún punto de conexión en el código o en la configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementada por el servicio. Para obtener más información sobre los puntos de conexión predeterminados, vea [Especificación de una dirección de punto de conexión](../../../docs/framework/wcf/specifying-an-endpoint-address.md). Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
    4.  Paso 4 - Habilita el intercambio de metadatos. Los clientes usarán intercambio de metadatos para generar los servidores proxy que se usarán para llamar a las operaciones de servicio. Para habilitar el intercambio de metadatos, cree una instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, establezca su propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true` y agregue el comportamiento a la colección <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` de la instancia de <xref:System.ServiceModel.ServiceHost>.  
  
    5.  Paso 5 - Abre <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes. Observe que el código espera que el usuario presione ENTRAR. Si no lo hace, la aplicación se cerrará inmediatamente y el servicio se cerrará. Observe también que se usa un bloque try/catch. Una vez creada la instancia de <xref:System.ServiceModel.ServiceHost>, el resto del código se coloca en un bloque try/catch. Para obtener más información sobre cómo detectar de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost>, vea [Evitar problemas mediante una declaración de instrucción](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
> [!IMPORTANT]
> Edición de App.config en GettingStartedLib para reflejar los cambios realizados en el código: 
> 1. Cambie la línea 14 a `<service name="GettingStartedLib.CalculatorService">`
> 2. Cambie la línea 17 a `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
> 3. Cambie la línea 22 en `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`
        
### <a name="to-verify-the-service-is-working"></a>Para comprobar si el servicio funciona  
  
1.  Ejecute la aplicación de consola GettingStartedHost desde [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]. Al ejecutarse en [!INCLUDE[wv](../../../includes/wv-md.md)] y sistemas operativos posteriores, el servicio se debe ejecutar con privilegios de administrador. Dado que Visual se ejecutó con privilegios de administrador, GettingStartedHost también se ejecuta con esos privilegios. También puede iniciar un nuevo símbolo del sistema con privilegios de administrador y ejecutar service.exe desde allí.  
  
2.  Abra Internet Explorer y busque la página de depuración del servicio en `http://localhost:8000/GettingStarted/CalculatorService`.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo incluye el contrato de servicios y la implementación de los pasos anteriores del tutorial y hospeda el servicio en una aplicación de consola.  
  
 Para compilar esto con un compilador de la línea de comandos, compile IService1.cs y Service1.cs en una biblioteca de clases haciendo referencia a `System.ServiceModel.dll`. Y compile Program.cs en una aplicación de consola.  
  
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
>  Servicios como este requieren permiso para registrar las direcciones HTTP en el equipo para la realización de escuchas. Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP. Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md). Cuando se ejecuta en Visual Studio, service.exe se debe ejecutar con privilegios de administrador.  
  
 Ahora, el servicio se está ejecutando. Continúe hasta [Creación de un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Para obtener información de solución de problemas, vea [Solución de problemas con el tutorial de introducción](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)
