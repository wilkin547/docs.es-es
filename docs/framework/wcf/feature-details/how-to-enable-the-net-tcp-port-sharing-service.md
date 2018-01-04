---
title: "Cómo habilitar el servicio de uso compartido de puertos Net.TCP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9f1c57f067fa7c8bece3acaf0d51303b31d13bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="33ab9-102">Cómo habilitar el servicio de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="33ab9-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="33ab9-103"> utiliza un servicio de Windows llamado Servicio de uso compartido de puertos de Net.TCP para facilitar el uso compartido de puertos TCP por varios procesos.</span><span class="sxs-lookup"><span data-stu-id="33ab9-103"> uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="33ab9-104">Este servicio se instala como parte de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], pero el servicio no está habilitado de forma predeterminada como precaución de seguridad, por lo que debe habilitarse manualmente antes de su primer uso.</span><span class="sxs-lookup"><span data-stu-id="33ab9-104">This service is installed as part of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="33ab9-105">En este tema se describe cómo configurar el Servicio de uso compartido de puertos Net.TCP mediante el complemento de Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="33ab9-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="33ab9-106">Después de habilitar el servicio de uso compartido de puertos Net.TCP e iniciarla manualmente, consulte [Cómo: configurar un servicio de WCF para utilizar el uso compartido de puertos](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) para obtener información acerca de cómo configurar el servicio para utilizar este servicio.</span><span class="sxs-lookup"><span data-stu-id="33ab9-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="33ab9-107">Para obtener un ejemplo que utiliza el uso compartido de puertos net.tcp://, consulte el [ejemplo de uso compartido de puertos Net.TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="33ab9-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="33ab9-108">Habilitación del servicio de uso compartido de puertos Net.TCP mediante MMC</span><span class="sxs-lookup"><span data-stu-id="33ab9-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1.  <span data-ttu-id="33ab9-109">En el menú Inicio, abra la consola de administración de servicios, ya sea abriendo una ventana de símbolo del sistema y escribiendo `services.msc` o abriendo ejecutar y escriba `services.msc` en el cuadro Abrir.</span><span class="sxs-lookup"><span data-stu-id="33ab9-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2.  <span data-ttu-id="33ab9-110">En el **nombre** columna de la lista de servicios, haga clic en el **servicio de uso compartido de puertos Net.Tcp**y seleccione **propiedades** en el menú.</span><span class="sxs-lookup"><span data-stu-id="33ab9-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3.  <span data-ttu-id="33ab9-111">Para habilitar el inicio manual del servicio, en la **propiedades** ventana Seleccione la **General** ficha y en el **tipo de inicio** seleccione Manual y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="33ab9-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4.  <span data-ttu-id="33ab9-112">Para iniciar el servicio, en el área de estado de servicio, haga clic en el **iniciar** botón.</span><span class="sxs-lookup"><span data-stu-id="33ab9-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="33ab9-113">El estado del servicio debería mostrar ahora "Iniciado".</span><span class="sxs-lookup"><span data-stu-id="33ab9-113">The service status should now display "Started".</span></span>  
  
5.  <span data-ttu-id="33ab9-114">Para volver a la lista de servicios, haga clic en el **Aceptar**y salga de la consola de MMC.</span><span class="sxs-lookup"><span data-stu-id="33ab9-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33ab9-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33ab9-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ab9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="33ab9-116">See Also</span></span>  
 [<span data-ttu-id="33ab9-117">Uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="33ab9-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [<span data-ttu-id="33ab9-118">Configuración del servicio de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="33ab9-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
