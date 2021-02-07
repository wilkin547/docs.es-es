---
description: 'Más información acerca de cómo: crear un servicio que requiere sesiones'
title: Procedimiento para crear un servicio que requiere sesiones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
ms.openlocfilehash: 362aee23437bb7f45af5a265a9d3ef47bf62915c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734469"
---
# <a name="how-to-create-a-service-that-requires-sessions"></a>Procedimiento para crear un servicio que requiere sesiones

Las sesiones crean un estado compartido entre dos o más extremos que habilita características útiles como las devoluciones de llamada, la seguridad de saltos múltiples y asociaciones entre clientes e instancias de servicio. Para obtener más información acerca de las sesiones en aplicaciones de Windows Communication Foundation (WCF), consulte [uso de sesiones](../using-sessions.md).  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>Especificar que un contrato requiere su enlace para admitir sesiones  
  
1. Crear un contrato de servicio que contenga al menos una operación. Para obtener un ejemplo de cómo crear un contrato de servicios, consulte [Cómo: definir un contrato de servicio](../how-to-define-a-wcf-service-contract.md).  
  
2. Modifique el <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> que declara el contrato estableciendo la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> en:  
  
    - <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> si este contrato se debe ejecutar dentro de una sesión.  
  
    - <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> si este contrato puede ejecutarse dentro de una sesión.  
  
    - <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> si este contrato no se debe ejecutar dentro de una sesión.  
  
3. Configure su extremo de servicio para que use un enlace que admita sesiones. El siguiente ejemplo de configuración muestra el uso de <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, que admite una sesión WS`-`ReliableMessaging.  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="example"></a>Ejemplo  

 El siguiente código de ejemplo muestra cómo especificar un requisito de sesión del nivel de contrato y utilizar un archivo de configuración para admitir ese requisito con el enlace <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
