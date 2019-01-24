---
title: Procedimiento Crear un generador de canales y utilizarlo para crear y gestionar canales
ms.date: 03/30/2017
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
ms.openlocfilehash: 37ba8db3084f8d90aab33a08f6b52ddaee4545f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649536"
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a>Procedimiento Crear un generador de canales y utilizarlo para crear y gestionar canales
La clase <xref:System.ServiceModel.DuplexChannelFactory%601> proporciona los medios para crear y gestionar los canales dúplex de distintos tipos que los clientes utilizan para enviar y recibir mensajes a y desde los puntos de conexión de servicio.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo crear un generador de canales y cómo usarlo para crear y gestionar canales.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.DuplexChannelFactory%601>
