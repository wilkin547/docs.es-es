---
description: 'Más información acerca de: interfaz IXCLRDataMethodInstance'
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
ms.openlocfilehash: 4e9ad57988420ff14b297c693c31c0dc5b3b181c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800791"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="8006b-103">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="8006b-103">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="8006b-104">Proporciona métodos para consultar información sobre una instancia de método.</span><span class="sxs-lookup"><span data-stu-id="8006b-104">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="8006b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8006b-105">Methods</span></span>

| <span data-ttu-id="8006b-106">Método</span><span class="sxs-lookup"><span data-stu-id="8006b-106">Method</span></span>                                                                                                                  | <span data-ttu-id="8006b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8006b-107">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="8006b-108">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="8006b-108">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="8006b-109">Obtiene el IL para direccionar la información de asignación.</span><span class="sxs-lookup"><span data-stu-id="8006b-109">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="8006b-110">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="8006b-110">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="8006b-111">Obtiene la dirección de punto de entrada más representativa para la compilación nativa de todos los puntos de entrada posibles para un método.</span><span class="sxs-lookup"><span data-stu-id="8006b-111">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8006b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8006b-112">Remarks</span></span>

<span data-ttu-id="8006b-113">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="8006b-113">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8006b-114">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="8006b-114">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="8006b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8006b-115">Requirements</span></span>

<span data-ttu-id="8006b-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8006b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8006b-117">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="8006b-117">**Header:** None</span></span>  
<span data-ttu-id="8006b-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="8006b-118">**Library:** None</span></span>  
<span data-ttu-id="8006b-119">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8006b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8006b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8006b-120">See also</span></span>

- [<span data-ttu-id="8006b-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="8006b-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="8006b-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8006b-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
