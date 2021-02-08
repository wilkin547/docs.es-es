---
description: 'Más información acerca de: interfaz IXCLRDataMethodDefinition'
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
ms.openlocfilehash: d73246b42a0bfb982c87b04d5490e945f7caa745
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790352"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="dcd90-103">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="dcd90-103">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="dcd90-104">Proporciona métodos para consultar información sobre una definición de método.</span><span class="sxs-lookup"><span data-stu-id="dcd90-104">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="dcd90-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dcd90-105">Methods</span></span>

<span data-ttu-id="dcd90-106">Los métodos siguientes son algunos de los métodos disponibles en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="dcd90-106">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="dcd90-107">Método</span><span class="sxs-lookup"><span data-stu-id="dcd90-107">Method</span></span>                                                                                                                          | <span data-ttu-id="dcd90-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcd90-108">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="dcd90-109">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="dcd90-109">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="dcd90-110">Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="dcd90-110">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="dcd90-111">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="dcd90-111">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="dcd90-112">Enumera las instancias de esta definición de método.</span><span class="sxs-lookup"><span data-stu-id="dcd90-112">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="dcd90-113">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="dcd90-113">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="dcd90-114">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="dcd90-114">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="dcd90-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dcd90-115">Remarks</span></span>

<span data-ttu-id="dcd90-116">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="dcd90-116">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="dcd90-117">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `AAF60008-FB2C-420b-8FB1-42D244A54A97` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="dcd90-117">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="dcd90-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcd90-118">Requirements</span></span>

<span data-ttu-id="dcd90-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcd90-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dcd90-120">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="dcd90-120">**Header:** None</span></span>  
<span data-ttu-id="dcd90-121">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="dcd90-121">**Library:** None</span></span>  
<span data-ttu-id="dcd90-122">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dcd90-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="dcd90-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcd90-123">See also</span></span>

- [<span data-ttu-id="dcd90-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="dcd90-124">Debugging</span></span>](index.md)
- [<span data-ttu-id="dcd90-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="dcd90-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
