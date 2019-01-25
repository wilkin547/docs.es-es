---
title: Interfaz ISOSDacInterface
ms.date: 01/16/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5e037cf6fb88fff4886733ff4152dca0a827e0a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491033"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="71074-102">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="71074-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="71074-103">Proporciona métodos auxiliares para acceder a ellos desde `SOS`.</span><span class="sxs-lookup"><span data-stu-id="71074-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="71074-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="71074-104">Methods</span></span>

| <span data-ttu-id="71074-105">Método</span><span class="sxs-lookup"><span data-stu-id="71074-105">Method</span></span>                                                                                                               | <span data-ttu-id="71074-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="71074-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="71074-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="71074-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="71074-108">Obtiene los datos para la dada [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="71074-108">Gets the data for the given [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span> |

## <a name="remarks"></a><span data-ttu-id="71074-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71074-109">Remarks</span></span>

<span data-ttu-id="71074-110">Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="71074-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="71074-111">Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` que puede obtenerse a través de los mecanismos de COM habituales.</span><span class="sxs-lookup"><span data-stu-id="71074-111">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="71074-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71074-112">Requirements</span></span>

<span data-ttu-id="71074-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71074-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="71074-114">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="71074-114">**Header:** None</span></span>  
<span data-ttu-id="71074-115">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="71074-115">**Library:** None</span></span>  
<span data-ttu-id="71074-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="71074-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="71074-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="71074-117">See also</span></span>

- [<span data-ttu-id="71074-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="71074-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="71074-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="71074-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
