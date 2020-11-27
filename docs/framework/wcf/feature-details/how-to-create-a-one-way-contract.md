---
title: Procedimiento para crear un contrato unidireccional
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85084cd9-31cc-4e95-b667-42ef01336622
ms.openlocfilehash: 7f0285ba4824ac842b3644d0834782139fd90657
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268695"
---
# <a name="how-to-create-a-one-way-contract"></a>Procedimiento para crear un contrato unidireccional

En este tema se muestran los pasos básicos para crear métodos que utilizan un contrato unidireccional. Tales métodos invocan operaciones en un servicio de Windows Communication Foundation (WCF) desde un cliente pero no esperan una respuesta. Se puede utilizar este tipo de contrato, por ejemplo, para publicar notificaciones a muchos suscriptores. También puede utilizar los contratos unidireccionales al crear un contrato dúplex (bidireccional), que permita a los clientes y servidores comunicarse entre sí independientemente de modo que cualquiera de ellos pueda iniciar una llamada al otro. Esto puede permitir, en particular, al servidor que realice llamadas unidireccionales al cliente que el cliente puede tratar como eventos. Para obtener información detallada sobre cómo especificar métodos unidireccionales, vea la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> y la clase <xref:System.ServiceModel.OperationContractAttribute>.  
  
 Para obtener más información sobre la creación de una aplicación cliente para un contrato dúplex, consulte [Cómo: obtener acceso a servicios con One-Way y Request-Reply contratos](how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md). Para obtener un ejemplo funcional, vea el ejemplo [unidireccional](../samples/one-way.md) .  
  
### <a name="to-create-a-one-way-contract"></a>Creación de un contrato unidireccional  
  
1. Cree el contrato de servicios aplicando la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz que define los métodos que el servicio va a implementar.  
  
2. Indique qué métodos de la interfaz puede invocar un cliente aplicándoles la clase <xref:System.ServiceModel.OperationContractAttribute>.  
  
3. Designe operaciones que no deban tener ningún resultado (ningún valor devuelto y ningún parámetro out o ref) como unidireccionales mediante el establecimiento de la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `true`. Observe que las operaciones que llevan la clase <xref:System.ServiceModel.OperationContractAttribute> satisfacen de forma predeterminada un contrato de solicitud-respuesta porque la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> es `false` de forma predeterminada. Así que debe especificar explícitamente el valor de la propiedad de atributo para que sea `true` si desea un contrato unidireccional para el método.  
  
## <a name="example"></a>Ejemplo  

 El siguiente ejemplo de código define un contrato para un servicio que incluye varios métodos unidireccionales. Todos los métodos tienen contratos unidireccionales excepto `Equals`, que tiene como valor predeterminado solicitud-respuesta y devuelve un resultado.  
  
 [!code-csharp[S_Service_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Diseño e implementación de servicios](../designing-and-implementing-services.md)
- [Cómo definir un contrato de servicios](../how-to-define-a-wcf-service-contract.md)
- [De sesión](../samples/session.md)
- [Procedimiento para crear un contrato dúplex](how-to-create-a-duplex-contract.md)
