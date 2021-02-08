---
description: 'Más información acerca de cómo: controlar la creación de instancias de servicio'
title: Procedimiento para controlar la creación de instancias de servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: 014d7fb4b054a1b52c1fea671cd099267fba468c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779925"
---
# <a name="how-to-control-service-instancing"></a>Procedimiento para controlar la creación de instancias de servicio

Establecer el modo de instancia de un servicio le permite especificar cuándo se crea (y su objeto de servicio  asociado definido por el usuario) <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>. Vea la enumeración de <xref:System.ServiceModel.InstanceContextMode> para los posibles modos. Para obtener más información sobre los comportamientos, vea [configuración y extensión del tiempo de ejecución con comportamientos](../extending/configuring-and-extending-the-runtime-with-behaviors.md). Para obtener ejemplos prácticos, vea [Behaviors](../samples/behaviors.md).  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a>Para controlar la duración de instancia de servicio mediante el código  
  
1. Aplique <xref:System.ServiceModel.ServiceBehaviorAttribute> a la clase de servicio.  
  
2. Establezca la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> a uno de los siguientes valores: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, o <xref:System.ServiceModel.InstanceContextMode.Single>.  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a>Ejemplo  

 El siguiente ejemplo de código establece la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> del atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> en <xref:System.ServiceModel.InstanceContextMode.PerCall>.  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [Servicio: ejemplos de comportamientos](../samples/behaviors.md)
