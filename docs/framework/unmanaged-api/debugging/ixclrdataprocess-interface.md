---
description: 'Más información acerca de: interfaz IXCLRDataProcess'
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
ms.openlocfilehash: b611491e5c9a5957c07a305a3f395b67ad208649
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800648"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="f0d8a-103">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="f0d8a-103">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="f0d8a-104">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-104">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="f0d8a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f0d8a-105">Methods</span></span>

| <span data-ttu-id="f0d8a-106">Método</span><span class="sxs-lookup"><span data-stu-id="f0d8a-106">Method</span></span>                                                                                                                                               | <span data-ttu-id="f0d8a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0d8a-107">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="f0d8a-108">GetRuntimeNameByAddress</span><span class="sxs-lookup"><span data-stu-id="f0d8a-108">GetRuntimeNameByAddress</span></span>](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | <span data-ttu-id="f0d8a-109">Obtiene un nombre para la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-109">Gets a name for the given address.</span></span>                                                               |
| [<span data-ttu-id="f0d8a-110">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="f0d8a-110">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="f0d8a-111">Obtiene un `AppDomain` en un proceso por su identificador único.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-111">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="f0d8a-112">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="f0d8a-112">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="f0d8a-113">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-113">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="f0d8a-114">EnumModule</span><span class="sxs-lookup"><span data-stu-id="f0d8a-114">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="f0d8a-115">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-115">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="f0d8a-116">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="f0d8a-116">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="f0d8a-117">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de módulos.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-117">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="f0d8a-118">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="f0d8a-118">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="f0d8a-119">Proporciona un identificador para enumerar las instancias de método de que `AppDomain` empiezan en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-119">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="f0d8a-120">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="f0d8a-120">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="f0d8a-121">Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-121">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="f0d8a-122">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="f0d8a-122">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="f0d8a-123">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-123">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="f0d8a-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f0d8a-124">Remarks</span></span>

<span data-ttu-id="f0d8a-125">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-125">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f0d8a-126">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-126">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0d8a-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0d8a-127">Requirements</span></span>

<span data-ttu-id="f0d8a-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0d8a-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="f0d8a-129">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f0d8a-129">**Header:** None</span></span>  
<span data-ttu-id="f0d8a-130">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f0d8a-130">**Library:** None</span></span>  
<span data-ttu-id="f0d8a-131">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f0d8a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f0d8a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0d8a-132">See also</span></span>

- [<span data-ttu-id="f0d8a-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="f0d8a-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="f0d8a-134">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f0d8a-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
