---
title: Procedimiento para crear un generador de canales y usarlo para crear y administrar canales
ms.date: 03/30/2017
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
ms.openlocfilehash: 6ed10cb92af03440848bd29302f8240698d0cbae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039395"
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a>Procedimiento para crear un generador de canales y usarlo para crear y administrar canales
La clase <xref:System.ServiceModel.DuplexChannelFactory%601> proporciona los medios para crear y gestionar los canales dúplex de distintos tipos que los clientes utilizan para enviar y recibir mensajes a y desde los extremos de servicio.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo crear un generador de canales y cómo usarlo para crear y gestionar canales.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.DuplexChannelFactory%601>
