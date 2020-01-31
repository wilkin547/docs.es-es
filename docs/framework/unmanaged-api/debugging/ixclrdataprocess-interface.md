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
ms.openlocfilehash: a5d707d61513b030e5968af28db3c2a606e4419b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790370"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="93ffb-102">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="93ffb-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="93ffb-103">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="93ffb-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="93ffb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="93ffb-104">Methods</span></span>

| <span data-ttu-id="93ffb-105">Método</span><span class="sxs-lookup"><span data-stu-id="93ffb-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="93ffb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="93ffb-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="93ffb-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="93ffb-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="93ffb-108">Obtiene una `AppDomain` en un proceso por su identificador único.</span><span class="sxs-lookup"><span data-stu-id="93ffb-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="93ffb-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="93ffb-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="93ffb-110">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="93ffb-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="93ffb-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="93ffb-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="93ffb-112">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="93ffb-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="93ffb-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="93ffb-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="93ffb-114">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de módulos.</span><span class="sxs-lookup"><span data-stu-id="93ffb-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="93ffb-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="93ffb-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="93ffb-116">Proporciona un identificador para enumerar las instancias de método de `AppDomain` a partir de una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="93ffb-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="93ffb-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="93ffb-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="93ffb-118">Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="93ffb-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="93ffb-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="93ffb-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="93ffb-120">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="93ffb-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="93ffb-121">Notas</span><span class="sxs-lookup"><span data-stu-id="93ffb-121">Remarks</span></span>

<span data-ttu-id="93ffb-122">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="93ffb-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="93ffb-123">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` que se puede obtener a través de los mecanismos COM habituales.</span><span class="sxs-lookup"><span data-stu-id="93ffb-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="93ffb-124">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="93ffb-124">Requirements</span></span>

<span data-ttu-id="93ffb-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93ffb-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="93ffb-126">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="93ffb-126">**Header:** None</span></span>  
<span data-ttu-id="93ffb-127">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="93ffb-127">**Library:** None</span></span>  
<span data-ttu-id="93ffb-128">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="93ffb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="93ffb-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="93ffb-129">See also</span></span>

- [<span data-ttu-id="93ffb-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="93ffb-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="93ffb-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="93ffb-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
