---
title: 3502 - InferredOperationDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 044d67bc2b721451ade04947484899266d288d8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="06214-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="06214-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="06214-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="06214-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06214-104">Id.</span><span class="sxs-lookup"><span data-stu-id="06214-104">ID</span></span>|<span data-ttu-id="06214-105">3502</span><span class="sxs-lookup"><span data-stu-id="06214-105">3502</span></span>|  
|<span data-ttu-id="06214-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="06214-106">Keywords</span></span>|<span data-ttu-id="06214-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="06214-107">WFServices</span></span>|  
|<span data-ttu-id="06214-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="06214-108">Level</span></span>|<span data-ttu-id="06214-109">Información</span><span class="sxs-lookup"><span data-stu-id="06214-109">Information</span></span>|  
|<span data-ttu-id="06214-110">Canal</span><span class="sxs-lookup"><span data-stu-id="06214-110">Channel</span></span>|<span data-ttu-id="06214-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="06214-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="06214-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="06214-112">Description</span></span>  
 <span data-ttu-id="06214-113">Indica que un OperationDescription se ha inferido de WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="06214-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="06214-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="06214-114">Message</span></span>  
 <span data-ttu-id="06214-115">OperationDescription con Name='%1' en el contrato '%2' se ha inferido de WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="06214-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="06214-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="06214-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="06214-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="06214-117">Details</span></span>  
  
|<span data-ttu-id="06214-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="06214-118">Data Item Name</span></span>|<span data-ttu-id="06214-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="06214-119">Data Item Type</span></span>|<span data-ttu-id="06214-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="06214-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="06214-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="06214-121">OperationName</span></span>|<span data-ttu-id="06214-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="06214-122">xs:string</span></span>|<span data-ttu-id="06214-123">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="06214-123">The name of the operation.</span></span>|  
|<span data-ttu-id="06214-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="06214-124">ContractName</span></span>|<span data-ttu-id="06214-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="06214-125">xs:string</span></span>|<span data-ttu-id="06214-126">El nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="06214-126">The name of the contract.</span></span>|  
|<span data-ttu-id="06214-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="06214-127">IsOneWay</span></span>|<span data-ttu-id="06214-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="06214-128">xs:string</span></span>|<span data-ttu-id="06214-129">True o false para indicar si el contrato es unidireccional.</span><span class="sxs-lookup"><span data-stu-id="06214-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="06214-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="06214-130">AppDomain</span></span>|<span data-ttu-id="06214-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="06214-131">xs:string</span></span>|<span data-ttu-id="06214-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="06214-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
