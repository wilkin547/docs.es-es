---
title: Cómo implementar un contrato de servicio de Windows Communication Foundation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: d8d1712e6fcc844a3606403efc3c2648ddcc9c65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499316"
---
# <a name="how-to-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="d4619-102">Cómo implementar un contrato de servicio de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d4619-102">How to: Implement a Windows Communication Foundation Service Contract</span></span>
<span data-ttu-id="d4619-103">Esta es la segunda de las seis tareas necesarias para crear un servicio básico de Windows Communication Foundation (WCF) y un cliente que puede llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="d4619-103">This is the second of six tasks required to create a basic Windows Communication Foundation (WCF) service and a client that can call the service.</span></span> <span data-ttu-id="d4619-104">Para obtener información general de las seis tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.</span><span class="sxs-lookup"><span data-stu-id="d4619-104">For an overview of all six tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="d4619-105">El siguiente paso para crear una aplicación de WCF es implementar la interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="d4619-105">The next step in creating a WCF application is to implement the service interface.</span></span> <span data-ttu-id="d4619-106">Esto implica la creación de una clase denominada `CalculatorService` que implemente la interfaz `ICalculator` definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d4619-106">This involves creating a class called `CalculatorService` that implements the user-defined `ICalculator` interface..</span></span>  
  
### <a name="to-implement-a-wcf-service-contract"></a><span data-ttu-id="d4619-107">Para implementar un contrato de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="d4619-107">To implement a WCF service contract</span></span>  
  
1.  <span data-ttu-id="d4619-108">Abra el archivo Service1.cs o Service1.vb y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4619-108">Open the Service1.cs or Service1.vb file and add the following code:</span></span>  
  
    ```csharp  
    //Service1.cs  
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
  
    ```vb
    ‘Service1.vb  
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
  
     <span data-ttu-id="d4619-109">Cada método implementa la operación de la calculadora y escribe texto en la consola para simplificar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="d4619-109">Each method implements the calculator operation and writes some text to the console to make testing easier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4619-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4619-110">Example</span></span>  
 <span data-ttu-id="d4619-111">El siguiente ejemplo de código muestra la interfaz que define el contrato de servicio y la implementación de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d4619-111">The following code shows both the interface that defines the contract and the implementation of the interface.</span></span>  
  
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
  
```vb
‘IService.vb  
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
  
 <span data-ttu-id="d4619-112">Ahora, el contrato de servicio se ha creado e implementado.</span><span class="sxs-lookup"><span data-stu-id="d4619-112">Now the service contract is created and implemented.</span></span> <span data-ttu-id="d4619-113">Compile la solución para asegurarse de que no hay ningún error de compilación y, a continuación, continúe con [Cómo: hospedar y ejecutar un servicio básico](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md) para ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="d4619-113">Build the solution to ensure there are no compilation errors and then proceed to [How to: Host and Run a Basic Service](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md) to run the service.</span></span> <span data-ttu-id="d4619-114">Para obtener información de solución de problemas, consulte [el Tutorial de introducción de la solución de problemas](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d4619-114">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d4619-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d4619-115">Compiling the Code</span></span>  
 <span data-ttu-id="d4619-116">Si se utiliza Visual Studio, en el menú Generar haga clic en generar solución (o presione CTRL + MAYÚS + B).</span><span class="sxs-lookup"><span data-stu-id="d4619-116">If you are using Visual Studio, on the Build menu click Build Solution (or press CTRL+SHIFT+B).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4619-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4619-117">See Also</span></span>  
 [<span data-ttu-id="d4619-118">Introducción</span><span class="sxs-lookup"><span data-stu-id="d4619-118">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="d4619-119">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="d4619-119">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
