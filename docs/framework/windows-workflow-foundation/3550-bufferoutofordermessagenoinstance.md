---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ce8b2cd52523d8a2efc94214479ca3c41d2dec4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="ce201-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="ce201-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="ce201-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ce201-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce201-104">Id.</span><span class="sxs-lookup"><span data-stu-id="ce201-104">ID</span></span>|<span data-ttu-id="ce201-105">3550</span><span class="sxs-lookup"><span data-stu-id="ce201-105">3550</span></span>|  
|<span data-ttu-id="ce201-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ce201-106">Keywords</span></span>|<span data-ttu-id="ce201-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ce201-107">WFServices</span></span>|  
|<span data-ttu-id="ce201-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ce201-108">Level</span></span>|<span data-ttu-id="ce201-109">Información</span><span class="sxs-lookup"><span data-stu-id="ce201-109">Information</span></span>|  
|<span data-ttu-id="ce201-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ce201-110">Channel</span></span>|<span data-ttu-id="ce201-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ce201-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ce201-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce201-112">Description</span></span>  
 <span data-ttu-id="ce201-113">Indica que se ha producido un error en la recepción almacenada en el búfer.</span><span class="sxs-lookup"><span data-stu-id="ce201-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="ce201-114">La operación se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="ce201-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ce201-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ce201-115">Message</span></span>  
 <span data-ttu-id="ce201-116">La operación '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="ce201-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="ce201-117">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="ce201-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ce201-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="ce201-118">Details</span></span>  
  
|<span data-ttu-id="ce201-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ce201-119">Data Item Name</span></span>|<span data-ttu-id="ce201-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ce201-120">Data Item Type</span></span>|<span data-ttu-id="ce201-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce201-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ce201-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="ce201-122">OperationName</span></span>|<span data-ttu-id="ce201-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce201-123">xs:string</span></span>|<span data-ttu-id="ce201-124">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="ce201-124">The name of the operation.</span></span>|  
|<span data-ttu-id="ce201-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ce201-125">AppDomain</span></span>|<span data-ttu-id="ce201-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce201-126">xs:string</span></span>|<span data-ttu-id="ce201-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ce201-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
