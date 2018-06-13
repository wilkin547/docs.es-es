---
title: 'Cómo: Agregar una referencia a Data Services (Data Services de WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: a8dcc01fb7a564a363cabed6a22738cd520d317f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356236"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="06934-102">Cómo: Agregar una referencia a Data Services (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="06934-102">How to: Add a Data Service Reference (WCF Data Services)</span></span>
<span data-ttu-id="06934-103">Puede usar el **Agregar referencia de servicio** cuadro de diálogo de Visual Studio para agregar una referencia a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06934-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span> <span data-ttu-id="06934-104">Esto le permite tener acceso más fácilmente a un servicio de datos en una aplicación cliente desarrollada en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="06934-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="06934-105">Cuando complete este procedimiento, se generarán clases de datos basadas en los metadatos que se obtienen del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="06934-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="06934-106">Para obtener más información, consulte [generar la biblioteca de cliente de servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="06934-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>  
  
### <a name="to-add-a-data-service-reference"></a><span data-ttu-id="06934-107">Para agregar una referencia a un servicio de datos</span><span class="sxs-lookup"><span data-stu-id="06934-107">To add a data service reference</span></span>  
  
1.  <span data-ttu-id="06934-108">(Opcional) Si el servicio de datos no forma parte de la solución y no se está ejecutando, inícielo y anote el URI del mismo.</span><span class="sxs-lookup"><span data-stu-id="06934-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>  
  
2.  <span data-ttu-id="06934-109">Haga clic en el proyecto de cliente y, a continuación, seleccione **Agregar referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="06934-109">Right-click the client project and then select **Add Service Reference**.</span></span>  
  
3.  <span data-ttu-id="06934-110">Si el servicio de datos forma parte de la solución actual, haga clic en **Discover**.</span><span class="sxs-lookup"><span data-stu-id="06934-110">If the data service is part of the current solution, click **Discover**.</span></span>  
  
     <span data-ttu-id="06934-111">-o bien-</span><span class="sxs-lookup"><span data-stu-id="06934-111">-or-</span></span>  
  
     <span data-ttu-id="06934-112">En el **dirección** cuadro de texto, escriba la dirección URL base del servicio de datos, como `http://localhost:1234/Northwind.svc`y, a continuación, haga clic en **vaya**.</span><span class="sxs-lookup"><span data-stu-id="06934-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>  
  
4.  <span data-ttu-id="06934-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="06934-113">Click **OK**.</span></span>  
  
     <span data-ttu-id="06934-114">De este modo se agrega un nuevo archivo de código que contiene las clases de datos que se usan para obtener acceso e interactuar con los recursos del servicio de datos como objetos.</span><span class="sxs-lookup"><span data-stu-id="06934-114">This adds a new code file that contains the data classes that are used to access and interact with data service resources as objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06934-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="06934-115">See Also</span></span>  
 [<span data-ttu-id="06934-116">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="06934-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
