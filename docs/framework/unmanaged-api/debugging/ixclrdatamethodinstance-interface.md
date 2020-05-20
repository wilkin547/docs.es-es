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
ms.openlocfilehash: 0b1c982b25af9edea76a038b4314b4bd608f07df
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420895"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="449b6-102">Interfaz IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="449b6-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="449b6-103">Proporciona métodos para consultar información sobre una instancia de método.</span><span class="sxs-lookup"><span data-stu-id="449b6-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="449b6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="449b6-104">Methods</span></span>

| <span data-ttu-id="449b6-105">Método</span><span class="sxs-lookup"><span data-stu-id="449b6-105">Method</span></span>                                                                                                                  | <span data-ttu-id="449b6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="449b6-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="449b6-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="449b6-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="449b6-108">Obtiene el IL para direccionar la información de asignación.</span><span class="sxs-lookup"><span data-stu-id="449b6-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="449b6-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="449b6-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="449b6-110">Obtiene la dirección de punto de entrada más representativa para la compilación nativa de todos los puntos de entrada posibles para un método.</span><span class="sxs-lookup"><span data-stu-id="449b6-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="449b6-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="449b6-111">Remarks</span></span>

<span data-ttu-id="449b6-112">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="449b6-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="449b6-113">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="449b6-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="449b6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="449b6-114">Requirements</span></span>

<span data-ttu-id="449b6-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="449b6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="449b6-116">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="449b6-116">**Header:** None</span></span>  
<span data-ttu-id="449b6-117">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="449b6-117">**Library:** None</span></span>  
<span data-ttu-id="449b6-118">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="449b6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="449b6-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="449b6-119">See also</span></span>

- [<span data-ttu-id="449b6-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="449b6-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="449b6-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="449b6-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
