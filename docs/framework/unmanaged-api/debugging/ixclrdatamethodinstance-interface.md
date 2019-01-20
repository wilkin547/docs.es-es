---
title: Interfaz IXCLRDataMethodInstance
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5bf724bc76591ae59c073b5b9a788ca065f51dc0
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416526"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="d6089-102">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="d6089-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="d6089-103">Proporciona métodos para consultar información sobre una instancia de método.</span><span class="sxs-lookup"><span data-stu-id="d6089-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="d6089-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d6089-104">Methods</span></span>

| <span data-ttu-id="d6089-105">Método</span><span class="sxs-lookup"><span data-stu-id="d6089-105">Method</span></span>                                                                                                                  | <span data-ttu-id="d6089-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6089-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="d6089-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="d6089-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="d6089-108">Obtiene el IL a la información de asignación de dirección.</span><span class="sxs-lookup"><span data-stu-id="d6089-108">Gets the IL to address mapping information.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d6089-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6089-109">Remarks</span></span>

<span data-ttu-id="d6089-110">Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d6089-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d6089-111">Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` que puede obtenerse a través de los mecanismos de COM habituales.</span><span class="sxs-lookup"><span data-stu-id="d6089-111">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6089-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6089-112">Requirements</span></span>

<span data-ttu-id="d6089-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6089-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d6089-114">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="d6089-114">**Header:** None</span></span>  
<span data-ttu-id="d6089-115">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d6089-115">**Library:** None</span></span>  
<span data-ttu-id="d6089-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d6089-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d6089-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6089-117">See Also</span></span>

- [<span data-ttu-id="d6089-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="d6089-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d6089-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d6089-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
