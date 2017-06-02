---
title: "Implementaci&#243;n de contratos de servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Implementación de contratos de servicio [WCF]"
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Implementaci&#243;n de contratos de servicio
Un servicio es una clase que expone la funcionalidad disponible a los clientes en uno o más extremos.Para crear un servicio, escriba una clase que implemente un contrato [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].Hay dos maneras de hacerlo.Puede definir el contrato separadamente como una interfaz y, a continuación, crear una clase que implemente esa interfaz.También puede crear la clase y el contrato directamente colocando el atributo <xref:System.ServiceModel.ServiceContractAttribute> en la misma clase y el atributo <xref:System.ServiceModel.OperationContractAttribute> en los métodos disponibles para los clientes del servicio.  
  
## Crear una clase de servicio  
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
  
 De forma alternativa, un servicio puede exponer un contrato directamente.A continuación, se muestra un ejemplo de una clase de servicio que define e implementa un contrato `MathService`.  
  
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
  
 Tenga en cuenta que los servicios anteriores exponen contratos diferentes porque los nombres del contrato son diferentes.En el primer caso, el contrato expuesto se denomina "`IMath`" mientras que, en el segundo caso, el contrato se denomina" `MathService`".  
  
 Puede establecer algunas cosas en el servicio y niveles de implementación de operación, como simultaneidad y creación de instancias.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Diseño e implementación de servicios](../../../docs/framework/wcf/designing-and-implementing-services.md).  
  
 Después de implementar un contrato de servicios, debe crear uno o más extremos para el servicio.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Información general acerca de la creación de puntos finales](../../../docs/framework/wcf/endpoint-creation-overview.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo ejecutar un servicio, vea [Servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).  
  
## Vea también  
 [Diseño e implementación de servicios](../../../docs/framework/wcf/designing-and-implementing-services.md)   
 [Cómo: Crear un servicio con una clase de contrato](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)   
 [Procedimiento para crear un servicio con una interfaz de contrato](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)   
 [Especificación del comportamiento en tiempo de ejecución del servicio](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)