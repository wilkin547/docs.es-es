---
title: 'Cómo: obtener acceso a los servicios con un contrato dúplex'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: bc42792b827b49265a0b1addf959de2fa1a041e3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597220"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Cómo: obtener acceso a los servicios con un contrato dúplex

Una característica de Windows Communication Foundation (WCF) es la capacidad de crear un servicio que usa un patrón de mensajería dúplex. Este patrón permite a un servicio comunicarse con el cliente mediante una devolución de llamada. En este tema se muestran los pasos para crear un cliente WCF en una clase de cliente que implementa la interfaz de devolución de llamada.

Un enlace dual expone la dirección IP del cliente al servicio. El cliente debería utilizar la seguridad para asegurarse de que solo se conecta a servicios de confianza.

Para ver un tutorial sobre la creación de un servicio y un cliente de WCF básico, consulte [Introducción tutorial](../getting-started-tutorial.md).

## <a name="to-access-a-duplex-service"></a>Obtención de acceso a un servicio dúplex

1. Cree un servicio que contenga dos interfaces. La primera interfaz es para el servicio, la segunda es para la devolución de llamada. Para obtener más información sobre cómo crear un servicio dúplex, consulte [Cómo: crear un contrato dúplex](how-to-create-a-duplex-contract.md).

2. Ejecute el servicio.

3. Use la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para generar contratos (interfaces) para el cliente. Para obtener información sobre cómo hacerlo, consulte [Cómo: crear un cliente](../how-to-create-a-wcf-client.md).

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

7. Llame a los métodos del cliente WCF según sea necesario.

## <a name="example"></a>Ejemplo

El siguiente ejemplo de código muestra cómo crear una clase de cliente que tenga acceso a un contrato dúplex.

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a>Vea también

- [Tutorial de Introducción](../getting-started-tutorial.md)
- [Procedimiento para crear un contrato dúplex](how-to-create-a-duplex-contract.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Cómo crear un cliente](../how-to-create-a-wcf-client.md)
- [Procedimiento para usar ChannelFactory](how-to-use-the-channelfactory.md)
