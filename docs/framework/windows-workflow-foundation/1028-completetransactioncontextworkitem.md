---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 806a437822cef8802a2bef6a54f924f84c88ef60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008816"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="7e924-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="7e924-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="7e924-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7e924-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e924-104">ID</span><span class="sxs-lookup"><span data-stu-id="7e924-104">ID</span></span>|<span data-ttu-id="7e924-105">1028</span><span class="sxs-lookup"><span data-stu-id="7e924-105">1028</span></span>|  
|<span data-ttu-id="7e924-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7e924-106">Keywords</span></span>|<span data-ttu-id="7e924-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7e924-107">WFRuntime</span></span>|  
|<span data-ttu-id="7e924-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="7e924-108">Level</span></span>|<span data-ttu-id="7e924-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="7e924-109">Verbose</span></span>|  
|<span data-ttu-id="7e924-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7e924-110">Channel</span></span>|<span data-ttu-id="7e924-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7e924-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7e924-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e924-112">Description</span></span>  
 <span data-ttu-id="7e924-113">Indica que se ha completado un TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="7e924-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7e924-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7e924-114">Message</span></span>  
 <span data-ttu-id="7e924-115">Un TransactionContextWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="7e924-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7e924-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="7e924-116">Details</span></span>  
  
|<span data-ttu-id="7e924-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7e924-117">Data Item Name</span></span>|<span data-ttu-id="7e924-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7e924-118">Data Item Type</span></span>|<span data-ttu-id="7e924-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e924-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7e924-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="7e924-120">Activity</span></span>|<span data-ttu-id="7e924-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e924-121">xs:string</span></span>|<span data-ttu-id="7e924-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7e924-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="7e924-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7e924-123">DisplayName</span></span>|<span data-ttu-id="7e924-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e924-124">xs:string</span></span>|<span data-ttu-id="7e924-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7e924-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="7e924-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7e924-126">InstanceId</span></span>|<span data-ttu-id="7e924-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e924-127">xs:string</span></span>|<span data-ttu-id="7e924-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7e924-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="7e924-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7e924-129">AppDomain</span></span>|<span data-ttu-id="7e924-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e924-130">xs:string</span></span>|<span data-ttu-id="7e924-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7e924-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
