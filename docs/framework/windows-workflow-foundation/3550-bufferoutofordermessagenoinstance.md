---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 1af943e23aa643c6614b946175c0b1854a7ceb62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755589"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="ccd41-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="ccd41-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="ccd41-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ccd41-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ccd41-104">ID</span><span class="sxs-lookup"><span data-stu-id="ccd41-104">ID</span></span>|<span data-ttu-id="ccd41-105">3550</span><span class="sxs-lookup"><span data-stu-id="ccd41-105">3550</span></span>|  
|<span data-ttu-id="ccd41-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ccd41-106">Keywords</span></span>|<span data-ttu-id="ccd41-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ccd41-107">WFServices</span></span>|  
|<span data-ttu-id="ccd41-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ccd41-108">Level</span></span>|<span data-ttu-id="ccd41-109">Información</span><span class="sxs-lookup"><span data-stu-id="ccd41-109">Information</span></span>|  
|<span data-ttu-id="ccd41-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ccd41-110">Channel</span></span>|<span data-ttu-id="ccd41-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ccd41-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ccd41-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccd41-112">Description</span></span>  
 <span data-ttu-id="ccd41-113">Indica que se ha producido un error en la recepción almacenada en el búfer.</span><span class="sxs-lookup"><span data-stu-id="ccd41-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="ccd41-114">La operación se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="ccd41-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ccd41-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ccd41-115">Message</span></span>  
 <span data-ttu-id="ccd41-116">La operación '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="ccd41-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="ccd41-117">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="ccd41-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ccd41-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="ccd41-118">Details</span></span>  
  
|<span data-ttu-id="ccd41-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ccd41-119">Data Item Name</span></span>|<span data-ttu-id="ccd41-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ccd41-120">Data Item Type</span></span>|<span data-ttu-id="ccd41-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccd41-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ccd41-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="ccd41-122">OperationName</span></span>|<span data-ttu-id="ccd41-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="ccd41-123">xs:string</span></span>|<span data-ttu-id="ccd41-124">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="ccd41-124">The name of the operation.</span></span>|  
|<span data-ttu-id="ccd41-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ccd41-125">AppDomain</span></span>|<span data-ttu-id="ccd41-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ccd41-126">xs:string</span></span>|<span data-ttu-id="ccd41-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ccd41-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
