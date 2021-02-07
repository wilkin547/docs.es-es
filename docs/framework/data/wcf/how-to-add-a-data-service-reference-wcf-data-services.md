---
description: 'Más información acerca de cómo: agregar una referencia de servicio de datos (Servicios de datos de WCF)'
title: 'Cómo: Agregar una referencia a Data Services (Data Services de WCF)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 907ad9a7dc3710a6e565de55c74a0d279d20e159
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765761"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="35383-103">Cómo: agregar una referencia de servicio de datos (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="35383-103">How to: Add a data service reference (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="35383-104">Puede usar el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio para agregar una referencia a servicios de datos de WCF.</span><span class="sxs-lookup"><span data-stu-id="35383-104">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="35383-105">Esto le permite tener acceso más fácilmente a un servicio de datos en una aplicación cliente desarrollada en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="35383-105">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="35383-106">Cuando complete este procedimiento, se generarán clases de datos basadas en los metadatos que se obtienen del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="35383-106">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="35383-107">Para obtener más información, vea [generar la biblioteca de cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="35383-107">For more information, see [Generating the Data Service Client Library](generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="35383-108">Agregar una referencia de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="35383-108">Add a data service reference</span></span>

1. <span data-ttu-id="35383-109">(Opcional) Si el servicio de datos no forma parte de la solución y no se está ejecutando, inícielo y anote el URI del mismo.</span><span class="sxs-lookup"><span data-stu-id="35383-109">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="35383-110">En el **Explorador de soluciones** de Visual Studio, haga clic con el botón secundario en el proyecto de cliente y, a continuación, seleccione **Agregar**  >  **referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="35383-110">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="35383-111">Si el servicio de datos forma parte de la solución actual, haga clic en **detectar**.</span><span class="sxs-lookup"><span data-stu-id="35383-111">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="35383-112">o bien</span><span class="sxs-lookup"><span data-stu-id="35383-112">-or-</span></span>

     <span data-ttu-id="35383-113">En el cuadro de texto **Dirección** , escriba la dirección URL base del servicio de datos, como `http://localhost:1234/Northwind.svc` y, a continuación, haga clic en **ir**.</span><span class="sxs-lookup"><span data-stu-id="35383-113">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="35383-114">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="35383-114">Select **OK**.</span></span>

     <span data-ttu-id="35383-115">Se agrega al proyecto un nuevo archivo de código que contiene las clases de datos que pueden tener acceso e interactuar con los recursos del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="35383-115">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="35383-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="35383-116">See also</span></span>

- [<span data-ttu-id="35383-117">Guía de inicio rápido</span><span class="sxs-lookup"><span data-stu-id="35383-117">Quickstart</span></span>](quickstart-wcf-data-services.md)
