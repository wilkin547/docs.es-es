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
ms.openlocfilehash: 6a6def8fc10f04b89aa8d8c735025b01f9b6ddfb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420765"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="8556b-102">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="8556b-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="8556b-103">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="8556b-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="8556b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8556b-104">Methods</span></span>

| <span data-ttu-id="8556b-105">Método</span><span class="sxs-lookup"><span data-stu-id="8556b-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="8556b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8556b-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="8556b-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="8556b-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="8556b-108">Obtiene un `AppDomain` en un proceso por su identificador único.</span><span class="sxs-lookup"><span data-stu-id="8556b-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="8556b-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="8556b-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="8556b-110">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="8556b-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="8556b-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="8556b-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="8556b-112">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="8556b-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="8556b-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="8556b-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="8556b-114">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de módulos.</span><span class="sxs-lookup"><span data-stu-id="8556b-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="8556b-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="8556b-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="8556b-116">Proporciona un identificador para enumerar las instancias de método de que `AppDomain` empiezan en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="8556b-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="8556b-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="8556b-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="8556b-118">Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="8556b-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="8556b-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="8556b-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="8556b-120">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="8556b-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="8556b-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8556b-121">Remarks</span></span>

<span data-ttu-id="8556b-122">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="8556b-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8556b-123">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="8556b-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="8556b-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8556b-124">Requirements</span></span>

<span data-ttu-id="8556b-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8556b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="8556b-126">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="8556b-126">**Header:** None</span></span>  
<span data-ttu-id="8556b-127">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="8556b-127">**Library:** None</span></span>  
<span data-ttu-id="8556b-128">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8556b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8556b-129">Consulta también</span><span class="sxs-lookup"><span data-stu-id="8556b-129">See also</span></span>

- [<span data-ttu-id="8556b-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="8556b-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="8556b-131">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8556b-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
