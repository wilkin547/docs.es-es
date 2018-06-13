---
title: 'Cómo: Obtener acceso a los servicios con un contrato dúplex'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: c0022e6ce3a63c1f497eeee82ca959cec1046cec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490157"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Cómo: Obtener acceso a los servicios con un contrato dúplex
Una característica de Windows Communication Foundation (WCF) es la capacidad para crear un servicio que utiliza un patrón de mensajería dúplex. Este patrón permite a un servicio comunicarse con el cliente mediante una devolución de llamada. En este tema se muestra los pasos para crear a un cliente WCF en una clase de cliente que implementa la interfaz de devolución de llamada.  
  
 Un enlace dual expone la dirección IP del cliente al servicio. El cliente debería utilizar la seguridad para asegurarse de que solo se conecta a servicios de confianza.  
  
 Para obtener un tutorial sobre cómo crear un servicio WCF básico y un cliente, consulte [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md).  
  
### <a name="to-access-a-duplex-service"></a>Obtención de acceso a un servicio dúplex  
  
1.  Cree un servicio que contenga dos interfaces. La primera interfaz es para el servicio, la segunda es para la devolución de llamada. Para obtener más información acerca de cómo crear un servicio dúplex, consulte [Cómo: crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
2.  Ejecute el servicio.  
  
3.  Use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar contratos (interfaces) para el cliente. Para obtener información acerca de cómo hacerlo, consulte [Cómo: crear un cliente](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
4.  Implemente la interfaz de devolución de llamada en la clase de cliente, tal y como se muestra en el siguiente ejemplo.  
  
    ```csharp  
    public class CallbackHandler : ICalculatorDuplexCallback  
    {  
        public void Result(double result)  
        {  
            Console.WriteLine("Result ({0})", result);  
        }  
        public void Equation(string equation)  
        {  
            Console.WriteLine("Equation({0})", equation);  
        }  
    }  
    ```  
  
    ```vb  
    Public Class CallbackHandler   
    Implements ICalculatorDuplexCallback  
       Public Sub Result (ByVal result As Double)  
          Console.WriteLine("Result ({0})", result)  
       End Sub  
        Public Sub Equation(ByVal equation As String)  
            Console.Writeline("Equation({0})", equation)  
        End Sub  
    End Class  
    ```  
  
5.  Cree una instancia de la clase <xref:System.ServiceModel.InstanceContext>. El constructor necesita una instancia de la clase cliente.  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  Cree una instancia del cliente WCF mediante el constructor que requiere un <xref:System.ServiceModel.InstanceContext> objeto. El segundo parámetro del constructor es el nombre de un punto de conexión encontrado en el archivo de configuración.  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  Llamar a los métodos del cliente WCF según sea necesario.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código muestra cómo crear una clase de cliente que tenga acceso a un contrato dúplex.  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Creación de un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Cómo crear un cliente](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Uso de ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
