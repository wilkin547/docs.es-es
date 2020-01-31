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
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790426"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="ee811-102">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="ee811-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="ee811-103">Proporciona métodos para consultar información sobre una definición de método.</span><span class="sxs-lookup"><span data-stu-id="ee811-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="ee811-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ee811-104">Methods</span></span>

<span data-ttu-id="ee811-105">Los métodos siguientes son algunos de los métodos disponibles en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="ee811-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="ee811-106">Método</span><span class="sxs-lookup"><span data-stu-id="ee811-106">Method</span></span>                                                                                                                          | <span data-ttu-id="ee811-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee811-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="ee811-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="ee811-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="ee811-109">Proporciona un identificador para la enumeración de instancias de método para un `IXCLRDataAppDomain`determinado.</span><span class="sxs-lookup"><span data-stu-id="ee811-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="ee811-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="ee811-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="ee811-111">Enumera las instancias de esta definición de método.</span><span class="sxs-lookup"><span data-stu-id="ee811-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="ee811-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="ee811-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="ee811-113">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="ee811-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="ee811-114">Notas</span><span class="sxs-lookup"><span data-stu-id="ee811-114">Remarks</span></span>

<span data-ttu-id="ee811-115">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ee811-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ee811-116">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` que se puede obtener a través de los mecanismos COM habituales.</span><span class="sxs-lookup"><span data-stu-id="ee811-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="ee811-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ee811-117">Requirements</span></span>

<span data-ttu-id="ee811-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee811-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ee811-119">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="ee811-119">**Header:** None</span></span>  
<span data-ttu-id="ee811-120">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="ee811-120">**Library:** None</span></span>  
<span data-ttu-id="ee811-121">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ee811-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ee811-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee811-122">See also</span></span>

- [<span data-ttu-id="ee811-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="ee811-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="ee811-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ee811-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
