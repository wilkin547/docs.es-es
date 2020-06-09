---
title: Procedimiento para habilitar el servicio de uso compartido de puertos Net.TCP
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 8b305b98d620636328866bce848411f395053485
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593157"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="238f1-102">Procedimiento para habilitar el servicio de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="238f1-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="238f1-103">Windows Communication Foundation (WCF) usa un servicio de Windows denominado servicio de uso compartido de puertos net. TCP para facilitar el uso compartido de puertos TCP en varios procesos.</span><span class="sxs-lookup"><span data-stu-id="238f1-103">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="238f1-104">Este servicio se instala como parte de WCF, pero el servicio no está habilitado de forma predeterminada como precaución de seguridad y, por lo tanto, debe habilitarse manualmente antes de usarse por primera vez.</span><span class="sxs-lookup"><span data-stu-id="238f1-104">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="238f1-105">En este tema se describe cómo configurar el Servicio de uso compartido de puertos Net.TCP mediante el complemento de Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="238f1-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="238f1-106">Después de habilitar el servicio de uso compartido de puertos net. TCP e iniciarlo manualmente, consulte [Cómo: configurar un servicio WCF para usar el uso compartido de puertos](how-to-configure-a-wcf-service-to-use-port-sharing.md) para obtener información sobre cómo configurar el servicio para utilizar este servicio.</span><span class="sxs-lookup"><span data-stu-id="238f1-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="238f1-107">Para obtener un ejemplo que usa net. TCP://uso compartido de puertos, consulte el [ejemplo de uso compartido de puertos net. TCP](../samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="238f1-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="238f1-108">Habilitación del servicio de uso compartido de puertos Net.TCP mediante MMC</span><span class="sxs-lookup"><span data-stu-id="238f1-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1. <span data-ttu-id="238f1-109">En el menú Inicio, abra la consola de administración de servicios; para ello, abra una ventana del símbolo del sistema y escriba `services.msc` o abra ejecutar y escriba `services.msc` en el cuadro Abrir.</span><span class="sxs-lookup"><span data-stu-id="238f1-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2. <span data-ttu-id="238f1-110">En la columna **nombre** de la lista de servicios, haga clic con el botón secundario en el **servicio de uso compartido de puertos net. TCP**y seleccione **propiedades** en el menú.</span><span class="sxs-lookup"><span data-stu-id="238f1-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3. <span data-ttu-id="238f1-111">Para habilitar el inicio manual del servicio, en la ventana **propiedades** , seleccione la pestaña **General** y, en el cuadro **tipo de inicio** , seleccione manual y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="238f1-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4. <span data-ttu-id="238f1-112">Para iniciar el servicio, en el área estado del servicio, haga clic en el botón **iniciar** .</span><span class="sxs-lookup"><span data-stu-id="238f1-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="238f1-113">El estado del servicio debería mostrar ahora "Iniciado".</span><span class="sxs-lookup"><span data-stu-id="238f1-113">The service status should now display "Started".</span></span>  
  
5. <span data-ttu-id="238f1-114">Para volver a la lista de servicios, haga clic en **Aceptar**y salga de la consola MMC.</span><span class="sxs-lookup"><span data-stu-id="238f1-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="238f1-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="238f1-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238f1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="238f1-116">See also</span></span>

- [<span data-ttu-id="238f1-117">Uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="238f1-117">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)
- [<span data-ttu-id="238f1-118">Configuración del servicio de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="238f1-118">Configuring the Net.TCP Port Sharing Service</span></span>](configuring-the-net-tcp-port-sharing-service.md)
