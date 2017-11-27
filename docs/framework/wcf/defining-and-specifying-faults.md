---
title: "Definición y especificación de errores"
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
helpviewer_keywords:
- handling faults [WCF], specifying
- handling faults [WCF], defining
ms.assetid: c00c84f1-962d-46a7-b07f-ebc4f80fbfc1
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 71df440ee9234071d0ab21cc3c18c5b080279bf4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="defining-and-specifying-faults"></a>Definición y especificación de errores
Los errores de SOAP transmiten información de condición de error desde un servicio a un cliente y, en caso de comunicación dúplex, desde un cliente a un servicio de una manera interoperable. Este tema describe cuándo y cómo definir contenido personalizado de error y especificar qué operaciones pueden devolverlos. [!INCLUDE[crabout](../../../includes/crabout-md.md)]cómo un servicio o cliente dúplex, puede enviar los errores y cómo una aplicación cliente o servicio administra estos errores, vea [enviar y recibir errores](../../../docs/framework/wcf/sending-and-receiving-faults.md). Para obtener información general de control de errores en [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] las aplicaciones, vea [especificar y control de errores en contactos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## <a name="overview"></a>Información general  
 Los errores de SOAP declarados son aquéllos en los que una operación tiene <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> que especifica un tipo de error de SOAP personalizado. Los errores de SOAP no declarados son aquéllos que no se especifican en el contrato para una operación. Este tema le ayuda a identificar esas condiciones de error y crear un contrato de error para su servicio, que los clientes pueden utilizar para administrar correctamente esas condiciones de error cuando sean notificadas por errores de SOAP personalizados. Las tareas básicas son, en orden:  
  
1.  Defina las condiciones que un cliente de su servicio debería saber.  
  
2.  Defina el contenido personalizado de los errores de SOAP para esas condiciones de error.  
  
3.  Marque sus operaciones para que los errores de SOAP específicos que inician se expongan a los clientes en WSDL.  
  
### <a name="defining-error-conditions-that-clients-should-know-about"></a>Definir Condiciones de error que los clientes deberían saber  
 Los errores de SOAP son mensajes descritos públicamente que llevan información de error para una operación determinada. Dado que se describen junto con otros mensajes de la operación en WSDL, los clientes saben y, por consiguiente, esperan controlar dichos errores al invocar una operación. Sin embargo, dado que los servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se escriben en código administrado, decidir qué condiciones de error en código administrado se convertirán en errores y se devolverán al cliente le proporciona la oportunidad de separar las condiciones de error y errores en su servicio de la conversación del error formal que usted tiene con un cliente.  
  
 Por ejemplo, el ejemplo de código siguiente muestra una operación que toma dos enteros y devuelve otro entero. Aquí, se pueden producir varias excepciones, por lo que al diseñar el contrato del error, debe determinar qué condiciones de error son importantes para su cliente. En este caso, el servicio debería detectar la excepción <xref:System.DivideByZeroException?displayProperty=nameWithType>.  
  
```csharp  
[ServiceContract]  
public class CalculatorService  
{  
    [OperationContract]   
    int Divide(int a, int b)  
    {  
      if (b==0) throw new Exception("Division by zero!");  
      return a/b;  
    }  
}  
```  
  
```vb  
<ServiceContract> _  
Public Class CalculatorService  
    <OperationContract]> _  
    Public Function Divide(ByVal a As Integer, ByVal b As Integer) _  
       As Integer  
      If (b==0) Then   
            Throw New Exception("Division by zero!")  
      Return a/b  
    End Function  
End Class  
```  
  
 En el ejemplo anterior, la operación puede devolver un error de SOAP personalizado, específico de dividir por cero, un error personalizado específico a las operaciones de matemática, pero con información específica a dividir por cero, varios errores para varias situaciones de error diferentes, o ningún error de SOAP en absoluto.  
  
### <a name="define-the-content-of-error-conditions"></a>Definir el contenido de condiciones de error  
 Una vez identificada una condición de error como una que puede devolver un error de SOAP personalizado de forma útil, el paso siguiente es definir los contenidos de ese error y garantizar que se puede serializar la estructura de contenido. El ejemplo de código de la sección anterior muestra un error específico en una operación `Divide`, pero si hay otras operaciones en el servicio `Calculator`, a continuación, un error de SOAP personalizado único puede informar el cliente de todas las condiciones de error de la calculadora, `Divide` incluido. El ejemplo de código siguiente muestra la creación de un error de SOAP personalizado, `MathFault`, que puede notificar los errores realizados utilizando todas las operaciones de matemática, incluso `Divide`. Mientras que la clase puede especificar una operación (la propiedad `Operation` ) y un valor que describe el problema (la propiedad `ProblemType` ), la clase y estas propiedades deben ser serializables para ser transferidas al cliente en un error de SOAP personalizado. Por consiguiente, <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType> y los atributos <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType> se utilizan para hacer el tipo y sus propiedades serializables y tan interoperable como sea posible.  
  
 [!code-csharp[Faults#2](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#2)]
 [!code-vb[Faults#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#2)]  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Cómo garantizar que sus datos es serializable, vea [especificación de transferencia de datos en contratos de servicio](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md). Para obtener una lista de la serialización puede admitir que <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> proporciona, consulte [tipos admitidos por el serializador de contratos de datos](../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
### <a name="mark-operations-to-establish-the-fault-contract"></a>Marcar operaciones para establecer el contrato de error  
 Una vez definida una estructura de datos serializable que se devuelve como parte de un error de SOAP personalizado, el último paso es marcar su contrato de operación como iniciar un error de SOAP de ese tipo. Para ello, utilice el atributo <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> y pase el tipo del tipo de datos personalizado que ha construido. El ejemplo de código siguiente muestra cómo usar el atributo <xref:System.ServiceModel.FaultContractAttribute> para especificar que la operación `Divide` puede devolver un error de SOAP del tipo `MathFault`. Otras operaciones basadas en matemáticas, ahora, también pueden especificar que pueden devolver un `MathFault`.  
  
 [!code-csharp[Faults#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#1)]
 [!code-vb[Faults#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#1)]  
  
 Una operación puede especificar que devuelve más de un error personalizado marcando esa operación con más de un atributo <xref:System.ServiceModel.FaultContractAttribute>.  
  
 El paso siguiente, para implementar el contrato de error en la implementación de la operación, se describe en el tema [enviar y recibir errores](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
#### <a name="soap-wsdl-and-interoperability-considerations"></a>SOAP, WSDL y consideraciones de la interoperabilidad  
 En algunas circunstancias, sobre todo al interoperar con otras plataformas, puede ser importante para controlar la manera en que aparece un error en un mensaje SOAP o la manera en el que se describe en los metadatos de WSDL.  
  
 El atributo <xref:System.ServiceModel.FaultContractAttribute> tiene una propiedad <xref:System.ServiceModel.FaultContractAttribute.Name%2A> que permite controlar el nombre del elemento de error WSDL que se genera en los metadatos para ese error.  
  
 Según la norma de SOAP, un error puede tener `Action`, `Code`y `Reason`. `Action` es controlado por la propiedad <xref:System.ServiceModel.FaultContractAttribute.Action%2A>. La propiedad <xref:System.ServiceModel.FaultException.Code%2A> y la propiedad <xref:System.ServiceModel.FaultException.Reason%2A> son ambas propiedades de la clase <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>, que es la clase primaria del <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> genérico. Una propiedad `Code` incluye un miembro <xref:System.ServiceModel.FaultCode.SubCode%2A>.  
  
 Al tener acceso a servicios que generan errores, ciertas limitaciones existen. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] solo admite errores con los tipos de detalle que el esquema describe y que son compatibles con los contratos de datos. Por ejemplo, tal y como se ha mencionado, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] no admite errores que utilizan los atributos XML en sus tipos de datos o errores con más de un elemento de nivel superior en la sección de datos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [Especificación y gestión de errores en contratos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)  
 [Envío y recepción de errores](../../../docs/framework/wcf/sending-and-receiving-faults.md)  
 [Cómo declarar errores en contratos de servicio](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md)  
 [Descripción de los niveles de protección](../../../docs/framework/wcf/understanding-protection-level.md)  
 [Cómo establecerla propiedad ProtectionLevel Property](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md)  
 [Transferencia de datos especificando en contratos de servicio](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)
