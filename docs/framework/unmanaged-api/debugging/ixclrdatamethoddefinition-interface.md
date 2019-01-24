---
title: Interfaz IXCLRDataMethodDefinition
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4b1e8cb1cf34bb1c5ade1353351aab953e2b734a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644252"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="29bf9-102">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="29bf9-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="29bf9-103">Proporciona métodos para consultar información sobre una definición de método.</span><span class="sxs-lookup"><span data-stu-id="29bf9-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="29bf9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="29bf9-104">Methods</span></span>

<span data-ttu-id="29bf9-105">Los métodos siguientes son algunos de los métodos disponibles en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="29bf9-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="29bf9-106">Método</span><span class="sxs-lookup"><span data-stu-id="29bf9-106">Method</span></span>                                                                                                                          | <span data-ttu-id="29bf9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="29bf9-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="29bf9-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="29bf9-108">StartEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="29bf9-109">Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="29bf9-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="29bf9-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="29bf9-110">EnumInstance</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="29bf9-111">Enumera las instancias de esta definición de método.</span><span class="sxs-lookup"><span data-stu-id="29bf9-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="29bf9-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="29bf9-112">EndEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="29bf9-113">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="29bf9-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="29bf9-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29bf9-114">Remarks</span></span>

<span data-ttu-id="29bf9-115">Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="29bf9-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="29bf9-116">Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` que puede obtenerse a través de los mecanismos de COM habituales.</span><span class="sxs-lookup"><span data-stu-id="29bf9-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="29bf9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29bf9-117">Requirements</span></span>

<span data-ttu-id="29bf9-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29bf9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="29bf9-119">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="29bf9-119">**Header:** None</span></span>  
<span data-ttu-id="29bf9-120">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="29bf9-120">**Library:** None</span></span>  
<span data-ttu-id="29bf9-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="29bf9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="29bf9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="29bf9-122">See also</span></span>

- [<span data-ttu-id="29bf9-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="29bf9-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="29bf9-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="29bf9-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
