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
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a><span data-ttu-id="bd589-102">Procedimiento para crear un generador de canales y usarlo para crear y administrar canales</span><span class="sxs-lookup"><span data-stu-id="bd589-102">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>

<span data-ttu-id="bd589-103">La clase <xref:System.ServiceModel.DuplexChannelFactory%601> proporciona los medios para crear y gestionar los canales dúplex de distintos tipos que los clientes utilizan para enviar y recibir mensajes a y desde los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="bd589-103">The <xref:System.ServiceModel.DuplexChannelFactory%601> class provides the means to create and manage duplex channels of different types that clients use to send and receive messages to and from service endpoints.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd589-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd589-104">Example</span></span>  

 <span data-ttu-id="bd589-105">El código siguiente muestra cómo crear un generador de canales y cómo usarlo para crear y gestionar canales.</span><span class="sxs-lookup"><span data-stu-id="bd589-105">The following code shows how to create a channel factory and use it to create and manage channels.</span></span>  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bd589-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd589-106">See also</span></span>

- <xref:System.ServiceModel.DuplexChannelFactory%601>
