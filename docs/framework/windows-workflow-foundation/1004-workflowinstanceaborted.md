---
description: 'Más información acerca de: 1004-WorkflowInstanceAborted'
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: 4aaa0899da9b0b8510684a13537a8cb8f9117ee1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755627"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="e1a76-103">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="e1a76-103">1004 - WorkflowInstanceAborted</span></span>

## <a name="properties"></a><span data-ttu-id="e1a76-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e1a76-104">Properties</span></span>

|||
|-|-|
|<span data-ttu-id="e1a76-105">Id.</span><span class="sxs-lookup"><span data-stu-id="e1a76-105">ID</span></span>|<span data-ttu-id="e1a76-106">1004</span><span class="sxs-lookup"><span data-stu-id="e1a76-106">1004</span></span>|
|<span data-ttu-id="e1a76-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e1a76-107">Keywords</span></span>|<span data-ttu-id="e1a76-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e1a76-108">WFRuntime</span></span>|
|<span data-ttu-id="e1a76-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="e1a76-109">Level</span></span>|<span data-ttu-id="e1a76-110">Información</span><span class="sxs-lookup"><span data-stu-id="e1a76-110">Information</span></span>|
|<span data-ttu-id="e1a76-111">Canal</span><span class="sxs-lookup"><span data-stu-id="e1a76-111">Channel</span></span>|<span data-ttu-id="e1a76-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e1a76-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|

## <a name="description"></a><span data-ttu-id="e1a76-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1a76-113">Description</span></span>

<span data-ttu-id="e1a76-114">Indica que una instancia de flujo de trabajo se ha anulado con una excepción.</span><span class="sxs-lookup"><span data-stu-id="e1a76-114">Indicates a workflow instance has aborted with an exception.</span></span>

## <a name="message"></a><span data-ttu-id="e1a76-115">Message</span><span class="sxs-lookup"><span data-stu-id="e1a76-115">Message</span></span>

<span data-ttu-id="e1a76-116">WorkflowInstance Id: '%1' se anuló con una excepción.</span><span class="sxs-lookup"><span data-stu-id="e1a76-116">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>

## <a name="details"></a><span data-ttu-id="e1a76-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="e1a76-117">Details</span></span>

|<span data-ttu-id="e1a76-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1a76-118">Data Item Name</span></span>|<span data-ttu-id="e1a76-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1a76-119">Data Item Type</span></span>|<span data-ttu-id="e1a76-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1a76-120">Description</span></span>|
|--------------------|--------------------|-----------------|
|<span data-ttu-id="e1a76-121">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="e1a76-121">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="e1a76-122">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1a76-122">The instance id for the workflow</span></span>|
|<span data-ttu-id="e1a76-123">Excepción</span><span class="sxs-lookup"><span data-stu-id="e1a76-123">Exception</span></span>|`xs:string`|<span data-ttu-id="e1a76-124">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="e1a76-124">The exception details for the exception</span></span>|
|<span data-ttu-id="e1a76-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e1a76-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e1a76-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e1a76-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
