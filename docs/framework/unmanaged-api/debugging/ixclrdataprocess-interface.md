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
ms.openlocfilehash: 8c98dd42b4ac5593d96478c2286f49ad216a4bc1
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416635"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="e60db-102">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="e60db-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="e60db-103">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="e60db-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="e60db-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e60db-104">Methods</span></span>

| <span data-ttu-id="e60db-105">Método</span><span class="sxs-lookup"><span data-stu-id="e60db-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="e60db-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e60db-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="e60db-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="e60db-107">GetAppDomainByUniqueId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="e60db-108">Obtiene un `AppDomain` en un proceso por su identificador único.</span><span class="sxs-lookup"><span data-stu-id="e60db-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="e60db-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="e60db-109">StartEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="e60db-110">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="e60db-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="e60db-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="e60db-111">EnumModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="e60db-112">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="e60db-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="e60db-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="e60db-113">EndEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="e60db-114">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de módulo.</span><span class="sxs-lookup"><span data-stu-id="e60db-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="e60db-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="e60db-115">StartEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="e60db-116">Proporciona un identificador para enumerar las instancias de método de `AppDomain` a partir de una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="e60db-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="e60db-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="e60db-117">EnumMethodInstanceByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="e60db-118">Enumera las instancias de método de este proceso empezando por un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="e60db-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="e60db-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="e60db-119">EndEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="e60db-120">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="e60db-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="e60db-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e60db-121">Remarks</span></span>

<span data-ttu-id="e60db-122">Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e60db-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e60db-123">Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` que puede obtenerse a través de los mecanismos de COM habituales.</span><span class="sxs-lookup"><span data-stu-id="e60db-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="e60db-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e60db-124">Requirements</span></span>

<span data-ttu-id="e60db-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e60db-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="e60db-126">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="e60db-126">**Header:** None</span></span>  
<span data-ttu-id="e60db-127">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e60db-127">**Library:** None</span></span>  
<span data-ttu-id="e60db-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e60db-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e60db-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e60db-129">See Also</span></span>

- [<span data-ttu-id="e60db-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="e60db-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="e60db-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e60db-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
