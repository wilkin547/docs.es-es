---
title: Creación de un contrato de solicitud-respuesta
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: 793f7214f8319e87c3e344990577841fc029bc55
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185031"
---
# <a name="how-to-create-a-request-reply-contract"></a>Creación de un contrato de solicitud-respuesta
Un contrato de solicitud-respuesta especifica un método que devuelve una respuesta. La respuesta se debe enviar y correlacionar con la solicitud según las condiciones de este contrato. Incluso si el método no devuelve ninguna respuesta (`void` en C#, o `Sub` en Visual Basic), la infraestructura crea y envía un mensaje vacío al autor de la llamada. Para evitar que se envíe un mensaje de respuesta vacío, use un contrato unidireccional para la operación.  
  
### <a name="to-create-a-request-reply-contract"></a>Creación de un contrato de solicitud-respuesta  
  
1. Cree una interfaz en el lenguaje de programación elegido.  
  
2. Aplique el atributo <xref:System.ServiceModel.ServiceContractAttribute> a dicha interfaz.  
  
3. Aplique el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos que pueden invocar los clientes.  
  
4. Opcional. Establezca el valor de la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `true` para evitar que se envíe un mensaje de respuesta vacío. De forma predeterminada, todas las operaciones son contratos de solicitud-respuesta.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo define un contrato para un servicio de calculadora que proporciona métodos `Add` y `Subtract`. El método `Multiply` no es parte del contrato, porque no está marcado por la clase <xref:System.ServiceModel.OperationContractAttribute> y, por tanto, los clientes no pueden acceder a él.  
  
```csharp
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);

    [OperationContract]
    int Subtract(int a, int b);

    int Multiply(int a, int b)
}
```
  
- Para obtener más información acerca de cómo <xref:System.ServiceModel.OperationContractAttribute> especificar <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> contratos de operación, vea la clase y la propiedad.  
  
- La aplicación de los atributos <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> permite la generación automática de definiciones de contrato de servicio en un Lenguaje de descripción de servicios Web (WSDL). El documento se descarga agregando `?wsdl` a la dirección base HTTP del servicio. Por ejemplo: `http://microsoft/CalculatorService?wsdl`  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.OperationContractAttribute>
- [Diseño de contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md)
- [Creación de un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
