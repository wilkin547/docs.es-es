---
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
ms.openlocfilehash: 9fb849c78636d5e29f58a70f59aa4cb3cd22df40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784733"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="b46fd-102">Interfaz ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="b46fd-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="b46fd-103">Proporciona el método de `Next`, que devuelve un número especificado de valores de `ICorDebugAppDomainEnum` a partir de la siguiente ubicación de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b46fd-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="b46fd-104">Esta interfaz es una subclase de "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="b46fd-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b46fd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b46fd-105">Methods</span></span>  
  
|<span data-ttu-id="b46fd-106">Método</span><span class="sxs-lookup"><span data-stu-id="b46fd-106">Method</span></span>|<span data-ttu-id="b46fd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b46fd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b46fd-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="b46fd-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="b46fd-109">Obtiene el número especificado de dominios de aplicación de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="b46fd-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b46fd-110">Notas</span><span class="sxs-lookup"><span data-stu-id="b46fd-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b46fd-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b46fd-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b46fd-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b46fd-112">Requirements</span></span>  
 <span data-ttu-id="b46fd-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b46fd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b46fd-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b46fd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b46fd-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b46fd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b46fd-116">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b46fd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b46fd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b46fd-117">See also</span></span>

- [<span data-ttu-id="b46fd-118">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b46fd-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="b46fd-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b46fd-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
