---
title: "Cómo: Obtener acceso a los servicios con un contrato dúplex"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4c273e674fb7cb0f2801d9858d598baab5973a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Cómo: Obtener acceso a los servicios con un contrato dúplex
Una característica de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es la capacidad de crear un servicio que utilice un patrón de mensajería dúplex. Este patrón permite a un servicio comunicarse con el cliente mediante una devolución de llamada. En este tema se muestran los pasos para crear un cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en una clase de cliente que implementa la interfaz de devolución de llamada.  
  
 Un enlace dual expone la dirección IP del cliente al servicio. El cliente debería utilizar la seguridad para asegurarse de que solo se conecta a servicios de confianza.  
  
 Para obtener un tutorial sobre cómo crear un basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio y el cliente, vea [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md).  
  
### <a name="to-access-a-duplex-service"></a>Obtención de acceso a un servicio dúplex  
  
1.  Cree un servicio que contenga dos interfaces. La primera interfaz es para el servicio, la segunda es para la devolución de llamada. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]creación de un servicio dúplex, consulte [Cómo: crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
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
  
6.  Cree una instancia de cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante el constructor que requiere un objeto <xref:System.ServiceModel.InstanceContext>. El segundo parámetro del constructor es el nombre de un extremo encontrado en el archivo de configuración.  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  Llame a los métodos de cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] según sea necesario.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código muestra cómo crear una clase de cliente que tenga acceso a un contrato dúplex.  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Cómo: crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Cómo crear un cliente](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Cómo: utilizar ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
