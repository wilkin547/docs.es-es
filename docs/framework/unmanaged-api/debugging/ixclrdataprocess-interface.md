---
title: Interfaz IXCLRDataProcess
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 376ec2b840bc17c79ed1f27c17a8ddd22c37a0f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245359"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="92553-102">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="92553-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="92553-103">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="92553-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="92553-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="92553-104">Methods</span></span>

| <span data-ttu-id="92553-105">Método</span><span class="sxs-lookup"><span data-stu-id="92553-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="92553-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="92553-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="92553-107">GetRuntimeNameByAddress</span><span class="sxs-lookup"><span data-stu-id="92553-107">GetRuntimeNameByAddress</span></span>](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | <span data-ttu-id="92553-108">Obtiene un nombre para la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="92553-108">Gets a name for the given address.</span></span>                                                               |
| [<span data-ttu-id="92553-109">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="92553-109">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="92553-110">Obtiene un `AppDomain` en un proceso por su identificador único.</span><span class="sxs-lookup"><span data-stu-id="92553-110">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="92553-111">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="92553-111">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="92553-112">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="92553-112">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="92553-113">EnumModule</span><span class="sxs-lookup"><span data-stu-id="92553-113">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="92553-114">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="92553-114">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="92553-115">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="92553-115">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="92553-116">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de módulos.</span><span class="sxs-lookup"><span data-stu-id="92553-116">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="92553-117">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="92553-117">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="92553-118">Proporciona un identificador para enumerar las instancias de método de que `AppDomain` empiezan en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="92553-118">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="92553-119">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="92553-119">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="92553-120">Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="92553-120">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="92553-121">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="92553-121">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="92553-122">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="92553-122">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="92553-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92553-123">Remarks</span></span>

<span data-ttu-id="92553-124">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="92553-124">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="92553-125">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="92553-125">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="92553-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92553-126">Requirements</span></span>

<span data-ttu-id="92553-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92553-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="92553-128">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="92553-128">**Header:** None</span></span>  
<span data-ttu-id="92553-129">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="92553-129">**Library:** None</span></span>  
<span data-ttu-id="92553-130">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="92553-130">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="92553-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="92553-131">See also</span></span>

- [<span data-ttu-id="92553-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="92553-132">Debugging</span></span>](index.md)
- [<span data-ttu-id="92553-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="92553-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
