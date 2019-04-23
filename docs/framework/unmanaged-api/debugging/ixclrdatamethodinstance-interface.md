---
title: Interfaz IXCLRDataMethodInstance
ms.date: 02/01/2019
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
ms.openlocfilehash: f62cbdc4b3e73f0c27492f7ed20b35378654d399
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152963"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="1ce18-102">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="1ce18-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="1ce18-103">Proporciona métodos para consultar información sobre una instancia de método.</span><span class="sxs-lookup"><span data-stu-id="1ce18-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="1ce18-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1ce18-104">Methods</span></span>

| <span data-ttu-id="1ce18-105">Método</span><span class="sxs-lookup"><span data-stu-id="1ce18-105">Method</span></span>                                                                                                                  | <span data-ttu-id="1ce18-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ce18-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="1ce18-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="1ce18-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="1ce18-108">Obtiene el IL a la información de asignación de dirección.</span><span class="sxs-lookup"><span data-stu-id="1ce18-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="1ce18-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="1ce18-109">GetRepresentativeEntryAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="1ce18-110">Obtiene la dirección del punto de entrada más representativa de la compilación nativa de todos los puntos de entrada posibles para un método.</span><span class="sxs-lookup"><span data-stu-id="1ce18-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1ce18-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ce18-111">Remarks</span></span>

<span data-ttu-id="1ce18-112">Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1ce18-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="1ce18-113">Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` que puede obtenerse a través de los mecanismos de COM habituales.</span><span class="sxs-lookup"><span data-stu-id="1ce18-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ce18-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ce18-114">Requirements</span></span>

<span data-ttu-id="1ce18-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ce18-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1ce18-116">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="1ce18-116">**Header:** None</span></span>  
<span data-ttu-id="1ce18-117">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="1ce18-117">**Library:** None</span></span>  
<span data-ttu-id="1ce18-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1ce18-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1ce18-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ce18-119">See also</span></span>

- [<span data-ttu-id="1ce18-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="1ce18-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="1ce18-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1ce18-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
