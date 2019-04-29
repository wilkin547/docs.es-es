---
title: Implementación de contratos de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: 766e0c4d30a4fa0eed9ce154ca932f5371a43211
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928641"
---
# <a name="implementing-service-contracts"></a>Implementación de contratos de servicio
Un servicio es una clase que expone la funcionalidad disponible a los clientes en uno o más puntos de conexión. Para crear un servicio, escribir una clase que implementa un contrato de Windows Communication Foundation (WCF). Hay dos maneras de hacerlo. Puede definir el contrato separadamente como una interfaz y, a continuación, crear una clase que implemente esa interfaz. También puede crear la clase y el contrato directamente colocando el atributo <xref:System.ServiceModel.ServiceContractAttribute> en la misma clase y el atributo <xref:System.ServiceModel.OperationContractAttribute> en los métodos disponibles para los clientes del servicio.  
  
## <a name="creating-a-service-class"></a>Crear una clase de servicio  
 A continuación, se muestra un ejemplo de un servicio que implementa un contrato `IMath` que se ha definido separadamente.  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]   
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 De forma alternativa, un servicio puede exponer un contrato directamente. A continuación, se muestra un ejemplo de una clase de servicio que define e implementa un contrato `MathService`.  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 Tenga en cuenta que los servicios anteriores exponen contratos diferentes porque los nombres del contrato son diferentes. En el primer caso, el contrato expuesto se denomina "`IMath`" mientras que, en el segundo caso, el contrato se denomina" `MathService`".  
  
 Puede establecer algunas cosas en el servicio y niveles de implementación de operación, como simultaneidad y creación de instancias. Para obtener más información, consulte [diseño e implementación de servicios](../../../docs/framework/wcf/designing-and-implementing-services.md).  
  
 Después de implementar un contrato de servicios, debe crear uno o más puntos de conexión para el servicio. Para obtener más información, consulte [Introducción a la creación de punto de conexión](../../../docs/framework/wcf/endpoint-creation-overview.md). Para obtener más información sobre cómo ejecutar un servicio, consulte [servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="see-also"></a>Vea también

- [Diseño e implementación de servicios](../../../docs/framework/wcf/designing-and-implementing-services.md)
- [Cómo: Crear un servicio con una clase de contrato](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [Cómo: Crear un servicio con una interfaz de contrato](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [Especificación del comportamiento en tiempo de ejecución del servicio](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
