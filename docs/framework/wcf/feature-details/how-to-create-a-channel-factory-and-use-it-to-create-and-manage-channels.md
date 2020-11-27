---
title: Procedimiento para crear un generador de canales y usarlo para crear y administrar canales
ms.date: 03/30/2017
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
ms.openlocfilehash: 44b0f45d1a340b8e8229ded827ad3ded738ae677
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256786"
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a>Procedimiento para crear un generador de canales y usarlo para crear y administrar canales

La clase <xref:System.ServiceModel.DuplexChannelFactory%601> proporciona los medios para crear y gestionar los canales dúplex de distintos tipos que los clientes utilizan para enviar y recibir mensajes a y desde los extremos de servicio.  
  
## <a name="example"></a>Ejemplo  

 El código siguiente muestra cómo crear un generador de canales y cómo usarlo para crear y gestionar canales.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.DuplexChannelFactory%601>
