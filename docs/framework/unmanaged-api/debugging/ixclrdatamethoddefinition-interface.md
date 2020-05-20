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
ms.openlocfilehash: ebb689eee4a89a70e81d8f9d958e7826c3b3421b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420960"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="d96fc-102">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="d96fc-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="d96fc-103">Proporciona métodos para consultar información sobre una definición de método.</span><span class="sxs-lookup"><span data-stu-id="d96fc-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="d96fc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d96fc-104">Methods</span></span>

<span data-ttu-id="d96fc-105">Los métodos siguientes son algunos de los métodos disponibles en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d96fc-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="d96fc-106">Método</span><span class="sxs-lookup"><span data-stu-id="d96fc-106">Method</span></span>                                                                                                                          | <span data-ttu-id="d96fc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d96fc-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="d96fc-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="d96fc-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="d96fc-109">Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="d96fc-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="d96fc-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="d96fc-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="d96fc-111">Enumera las instancias de esta definición de método.</span><span class="sxs-lookup"><span data-stu-id="d96fc-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="d96fc-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="d96fc-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="d96fc-113">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="d96fc-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="d96fc-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d96fc-114">Remarks</span></span>

<span data-ttu-id="d96fc-115">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d96fc-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d96fc-116">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `AAF60008-FB2C-420b-8FB1-42D244A54A97` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="d96fc-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="d96fc-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d96fc-117">Requirements</span></span>

<span data-ttu-id="d96fc-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d96fc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d96fc-119">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d96fc-119">**Header:** None</span></span>  
<span data-ttu-id="d96fc-120">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d96fc-120">**Library:** None</span></span>  
<span data-ttu-id="d96fc-121">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d96fc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d96fc-122">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d96fc-122">See also</span></span>

- [<span data-ttu-id="d96fc-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="d96fc-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="d96fc-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d96fc-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
