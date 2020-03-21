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
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178370"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="20778-102">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="20778-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="20778-103">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="20778-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="20778-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="20778-104">Methods</span></span>

| <span data-ttu-id="20778-105">Método</span><span class="sxs-lookup"><span data-stu-id="20778-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="20778-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="20778-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="20778-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="20778-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="20778-108">Obtiene un `AppDomain` proceso en un proceso por su identificador único.</span><span class="sxs-lookup"><span data-stu-id="20778-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="20778-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="20778-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="20778-110">Proporciona un identificador para enumerar los módulos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="20778-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="20778-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="20778-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="20778-112">Enumera los módulos de este proceso.</span><span class="sxs-lookup"><span data-stu-id="20778-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="20778-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="20778-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="20778-114">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración del módulo.</span><span class="sxs-lookup"><span data-stu-id="20778-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="20778-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="20778-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="20778-116">Proporciona un identificador para enumerar las `AppDomain` instancias de método de inicio en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="20778-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="20778-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="20778-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="20778-118">Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.</span><span class="sxs-lookup"><span data-stu-id="20778-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="20778-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="20778-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="20778-120">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de instancias.</span><span class="sxs-lookup"><span data-stu-id="20778-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="20778-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="20778-121">Remarks</span></span>

<span data-ttu-id="20778-122">Esta interfaz se encuentra dentro del tiempo de ejecución y no se expone a través de encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="20778-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="20778-123">Sin embargo, es una interfaz `IUnknown` COM `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` que deriva de con GUID que se puede obtener a través de los mecanismos COM habituales.</span><span class="sxs-lookup"><span data-stu-id="20778-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="20778-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20778-124">Requirements</span></span>

<span data-ttu-id="20778-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20778-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="20778-126">**Encabezado:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="20778-126">**Header:** None</span></span>  
<span data-ttu-id="20778-127">**Biblioteca:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="20778-127">**Library:** None</span></span>  
<span data-ttu-id="20778-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="20778-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="20778-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20778-129">See also</span></span>

- [<span data-ttu-id="20778-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="20778-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="20778-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="20778-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
