---
title: Procedimiento Agregar una referencia de servicio de datos (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: fc1786e1c6102c702374989253cd3ce23e3f7b54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765536"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="b02e8-102">Procedimiento Agregar una referencia de servicio de datos (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="b02e8-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="b02e8-103">Puede usar el **Add Service Reference** cuadro de diálogo de Visual Studio para agregar una referencia a WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="b02e8-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="b02e8-104">Esto le permite tener acceso más fácilmente a un servicio de datos en una aplicación cliente desarrollada en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b02e8-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="b02e8-105">Cuando complete este procedimiento, se generarán clases de datos basadas en los metadatos que se obtienen del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="b02e8-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="b02e8-106">Para obtener más información, consulte [generar la biblioteca de cliente de servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b02e8-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="b02e8-107">Agregar una referencia de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="b02e8-107">Add a data service reference</span></span>

1. <span data-ttu-id="b02e8-108">(Opcional) Si el servicio de datos no forma parte de la solución y no se está ejecutando, inícielo y anote el URI del mismo.</span><span class="sxs-lookup"><span data-stu-id="b02e8-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="b02e8-109">En Visual Studio, en **el Explorador de soluciones**, haga clic en el proyecto de cliente y, a continuación, seleccione **agregar** > **referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="b02e8-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="b02e8-110">Si el servicio de datos forma parte de la solución actual, haga clic en **Discover**.</span><span class="sxs-lookup"><span data-stu-id="b02e8-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="b02e8-111">-o bien-</span><span class="sxs-lookup"><span data-stu-id="b02e8-111">-or-</span></span>

     <span data-ttu-id="b02e8-112">En el **dirección** cuadro de texto, escriba la dirección URL base del servicio de datos, como `http://localhost:1234/Northwind.svc`y, a continuación, haga clic en **vaya**.</span><span class="sxs-lookup"><span data-stu-id="b02e8-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="b02e8-113">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b02e8-113">Select **OK**.</span></span>

     <span data-ttu-id="b02e8-114">Un nuevo archivo de código que contiene las clases de datos que pueden obtener acceso e interactuar con los recursos de servicio de datos se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b02e8-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="b02e8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b02e8-115">See also</span></span>

- [<span data-ttu-id="b02e8-116">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="b02e8-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)