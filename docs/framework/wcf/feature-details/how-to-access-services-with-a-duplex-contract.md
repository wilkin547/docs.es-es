---
title: Procedimiento Servicios de Access con un contrato dúplex
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: 366fd9d6aa220bcbec1ee8fb2a04d1b84755800a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855145"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Procedimiento Servicios de Access con un contrato dúplex

Una característica de Windows Communication Foundation (WCF) es la capacidad para crear un servicio que usa un patrón de mensajería dúplex. Este patrón permite a un servicio comunicarse con el cliente mediante una devolución de llamada. En este tema muestra los pasos para crear a un cliente de WCF en una clase de cliente que implementa la interfaz de devolución de llamada.

Un enlace dual expone la dirección IP del cliente al servicio. El cliente debería utilizar la seguridad para asegurarse de que solo se conecta a servicios de confianza.

Para ver un tutorial sobre la creación de un servicio WCF básico y un cliente, consulte [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md).

## <a name="to-access-a-duplex-service"></a>Obtención de acceso a un servicio dúplex

1. Cree un servicio que contenga dos interfaces. La primera interfaz es para el servicio, la segunda es para la devolución de llamada. Para obtener más información acerca de cómo crear un servicio dúplex, vea [Cómo: Crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).

2. Ejecute el servicio.

3. Use la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar contratos (interfaces) para el cliente. Para obtener información acerca de cómo hacerlo, vea [Cómo: Crear un cliente](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).

4. Implemente la interfaz de devolución de llamada en la clase de cliente, tal y como se muestra en el siguiente ejemplo.

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
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. Cree una instancia de la clase <xref:System.ServiceModel.InstanceContext>. El constructor necesita una instancia de la clase cliente.

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. Cree una instancia del cliente WCF mediante el constructor que requiere un <xref:System.ServiceModel.InstanceContext> objeto. El segundo parámetro del constructor es el nombre de un punto de conexión encontrado en el archivo de configuración.

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. Llamar a los métodos del cliente WCF según sea necesario.

## <a name="example"></a>Ejemplo

El siguiente ejemplo de código muestra cómo crear una clase de cliente que tenga acceso a un contrato dúplex.

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a>Vea también

- [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md)
- [Cómo: Crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Cómo: Crear un cliente](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Cómo: Uso de ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
