---
title: Procedimiento Agregar una referencia de servicio de datos (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 42d89cf87b5fe9bbdb229f10cd6a0e340d4c08fd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790742"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="5e409-102">Procedimiento Agregar una referencia de servicio de datos (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="5e409-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="5e409-103">Puede usar el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio para agregar una referencia a WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="5e409-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="5e409-104">Esto le permite tener acceso más fácilmente a un servicio de datos en una aplicación cliente desarrollada en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5e409-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="5e409-105">Cuando complete este procedimiento, se generarán clases de datos basadas en los metadatos que se obtienen del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="5e409-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="5e409-106">Para obtener más información, vea [generar la biblioteca de cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5e409-106">For more information, see [Generating the Data Service Client Library](generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="5e409-107">Agregar una referencia de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="5e409-107">Add a data service reference</span></span>

1. <span data-ttu-id="5e409-108">(Opcional) Si el servicio de datos no forma parte de la solución y no se está ejecutando, inícielo y anote el URI del mismo.</span><span class="sxs-lookup"><span data-stu-id="5e409-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="5e409-109">En el **Explorador de soluciones**de Visual Studio, haga clic con el botón secundario en el proyecto de cliente y, a continuación, seleccione **Agregar** > **referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="5e409-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="5e409-110">Si el servicio de datos forma parte de la solución actual, haga clic en **detectar**.</span><span class="sxs-lookup"><span data-stu-id="5e409-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="5e409-111">-o bien-</span><span class="sxs-lookup"><span data-stu-id="5e409-111">-or-</span></span>

     <span data-ttu-id="5e409-112">En el cuadro de texto **Dirección** , escriba la dirección URL base del servicio de datos, `http://localhost:1234/Northwind.svc`como y, a continuación, haga clic en **ir**.</span><span class="sxs-lookup"><span data-stu-id="5e409-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="5e409-113">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e409-113">Select **OK**.</span></span>

     <span data-ttu-id="5e409-114">Se agrega al proyecto un nuevo archivo de código que contiene las clases de datos que pueden tener acceso e interactuar con los recursos del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="5e409-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e409-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e409-115">See also</span></span>

- [<span data-ttu-id="5e409-116">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="5e409-116">Quickstart</span></span>](quickstart-wcf-data-services.md)
