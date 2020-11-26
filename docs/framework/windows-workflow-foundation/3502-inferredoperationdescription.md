---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 05278067e3f86612ee4aafbe7d5eb66dc934cb85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242115"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="13492-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="13492-102">3502 - InferredOperationDescription</span></span>

## <a name="properties"></a><span data-ttu-id="13492-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="13492-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13492-104">ID</span><span class="sxs-lookup"><span data-stu-id="13492-104">ID</span></span>|<span data-ttu-id="13492-105">3502</span><span class="sxs-lookup"><span data-stu-id="13492-105">3502</span></span>|  
|<span data-ttu-id="13492-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="13492-106">Keywords</span></span>|<span data-ttu-id="13492-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="13492-107">WFServices</span></span>|  
|<span data-ttu-id="13492-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="13492-108">Level</span></span>|<span data-ttu-id="13492-109">Información</span><span class="sxs-lookup"><span data-stu-id="13492-109">Information</span></span>|  
|<span data-ttu-id="13492-110">Canal</span><span class="sxs-lookup"><span data-stu-id="13492-110">Channel</span></span>|<span data-ttu-id="13492-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="13492-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="13492-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="13492-112">Description</span></span>  

 <span data-ttu-id="13492-113">Indica que un OperationDescription se ha inferido de WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="13492-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="13492-114">Message</span><span class="sxs-lookup"><span data-stu-id="13492-114">Message</span></span>  

 <span data-ttu-id="13492-115">OperationDescription con Name='%1' en el contrato '%2' se ha inferido de WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="13492-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="13492-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="13492-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="13492-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="13492-117">Details</span></span>  
  
|<span data-ttu-id="13492-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="13492-118">Data Item Name</span></span>|<span data-ttu-id="13492-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="13492-119">Data Item Type</span></span>|<span data-ttu-id="13492-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="13492-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="13492-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="13492-121">OperationName</span></span>|<span data-ttu-id="13492-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="13492-122">xs:string</span></span>|<span data-ttu-id="13492-123">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="13492-123">The name of the operation.</span></span>|  
|<span data-ttu-id="13492-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="13492-124">ContractName</span></span>|<span data-ttu-id="13492-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="13492-125">xs:string</span></span>|<span data-ttu-id="13492-126">El nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="13492-126">The name of the contract.</span></span>|  
|<span data-ttu-id="13492-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="13492-127">IsOneWay</span></span>|<span data-ttu-id="13492-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="13492-128">xs:string</span></span>|<span data-ttu-id="13492-129">True o false para indicar si el contrato es unidireccional.</span><span class="sxs-lookup"><span data-stu-id="13492-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="13492-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="13492-130">AppDomain</span></span>|<span data-ttu-id="13492-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="13492-131">xs:string</span></span>|<span data-ttu-id="13492-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="13492-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
