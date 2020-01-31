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
ms.openlocfilehash: c51825433bbc86c897c097475d5c15c855f6ec8b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790407"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="e41dd-102">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="e41dd-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="e41dd-103">Proporciona métodos para consultar información sobre una instancia de método.</span><span class="sxs-lookup"><span data-stu-id="e41dd-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="e41dd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e41dd-104">Methods</span></span>

| <span data-ttu-id="e41dd-105">Método</span><span class="sxs-lookup"><span data-stu-id="e41dd-105">Method</span></span>                                                                                                                  | <span data-ttu-id="e41dd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e41dd-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="e41dd-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="e41dd-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="e41dd-108">Obtiene el IL para direccionar la información de asignación.</span><span class="sxs-lookup"><span data-stu-id="e41dd-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="e41dd-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="e41dd-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="e41dd-110">Obtiene la dirección de punto de entrada más representativa para la compilación nativa de todos los puntos de entrada posibles para un método.</span><span class="sxs-lookup"><span data-stu-id="e41dd-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e41dd-111">Notas</span><span class="sxs-lookup"><span data-stu-id="e41dd-111">Remarks</span></span>

<span data-ttu-id="e41dd-112">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e41dd-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e41dd-113">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` que se puede obtener a través de los mecanismos COM habituales.</span><span class="sxs-lookup"><span data-stu-id="e41dd-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="e41dd-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e41dd-114">Requirements</span></span>

<span data-ttu-id="e41dd-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e41dd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e41dd-116">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e41dd-116">**Header:** None</span></span>  
<span data-ttu-id="e41dd-117">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e41dd-117">**Library:** None</span></span>  
<span data-ttu-id="e41dd-118">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e41dd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e41dd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e41dd-119">See also</span></span>

- [<span data-ttu-id="e41dd-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="e41dd-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="e41dd-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e41dd-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
