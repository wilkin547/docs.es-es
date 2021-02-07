---
description: 'Más información acerca de: interfaz ICorDebugAppDomainEnum ('
title: Interfaz ICorDebugAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: dfea6254e6cf4f162e44d057fb4126a67a087b61
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754165"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="a94f0-103">Interfaz ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="a94f0-103">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="a94f0-104">Proporciona el `Next` método, que devuelve un número especificado de `ICorDebugAppDomainEnum` valores a partir de la siguiente ubicación de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="a94f0-104">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="a94f0-105">Esta interfaz es una subclase de "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="a94f0-105">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a94f0-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="a94f0-106">Methods</span></span>  
  
|<span data-ttu-id="a94f0-107">Método</span><span class="sxs-lookup"><span data-stu-id="a94f0-107">Method</span></span>|<span data-ttu-id="a94f0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a94f0-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a94f0-109">Next (método)</span><span class="sxs-lookup"><span data-stu-id="a94f0-109">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="a94f0-110">Obtiene el número especificado de dominios de aplicación de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="a94f0-110">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a94f0-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a94f0-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a94f0-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a94f0-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a94f0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a94f0-113">Requirements</span></span>  

 <span data-ttu-id="a94f0-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a94f0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a94f0-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a94f0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a94f0-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a94f0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a94f0-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a94f0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94f0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a94f0-118">See also</span></span>

- [<span data-ttu-id="a94f0-119">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a94f0-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="a94f0-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a94f0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
