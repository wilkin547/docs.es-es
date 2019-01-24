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
ms.openlocfilehash: ff74a7acb5cc84c177f083c19402cd78977aeab5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680379"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="ae559-102">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="ae559-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="ae559-103">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="ae559-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="ae559-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ae559-104">Methods</span></span>

| <span data-ttu-id="ae559-105">Método</span><span class="sxs-lookup"><span data-stu-id="ae559-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="ae559-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae559-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="ae559-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="ae559-107">GetAppDomainByUniqueId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="ae559-108">Obtiene un `AppDomain` en un proceso por su identificador único.</span><span class="sxs-lookup"><span data-stu-id="ae559-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="ae559-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="ae559-109">StartEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="ae559-110">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="ae559-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="ae559-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="ae559-111">EnumModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="ae559-112">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="ae559-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="ae559-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="ae559-113">EndEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="ae559-114">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de módulo.</span><span class="sxs-lookup"><span data-stu-id="ae559-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="ae559-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="ae559-115">StartEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="ae559-116">Proporciona un identificador para enumerar las instancias de método de `AppDomain` a partir de una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="ae559-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="ae559-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="ae559-117">EnumMethodInstanceByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="ae559-118">Enumera las instancias de método de este proceso empezando por un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="ae559-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="ae559-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="ae559-119">EndEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="ae559-120">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="ae559-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="ae559-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae559-121">Remarks</span></span>

<span data-ttu-id="ae559-122">Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ae559-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ae559-123">Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` que puede obtenerse a través de los mecanismos de COM habituales.</span><span class="sxs-lookup"><span data-stu-id="ae559-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="ae559-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae559-124">Requirements</span></span>

<span data-ttu-id="ae559-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae559-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="ae559-126">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="ae559-126">**Header:** None</span></span>  
<span data-ttu-id="ae559-127">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="ae559-127">**Library:** None</span></span>  
<span data-ttu-id="ae559-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ae559-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ae559-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae559-129">See also</span></span>

- [<span data-ttu-id="ae559-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="ae559-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ae559-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ae559-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
