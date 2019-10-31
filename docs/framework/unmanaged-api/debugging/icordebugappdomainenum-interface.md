---
title: ICorDebugAppDomainEnum (Interfaz)
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
ms.openlocfilehash: 6cc3ec1c802c28b74248380aa7f686e675a92f1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088838"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="96b60-102">ICorDebugAppDomainEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="96b60-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="96b60-103">Proporciona el método de `Next`, que devuelve un número especificado de valores de `ICorDebugAppDomainEnum` a partir de la siguiente ubicación de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="96b60-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="96b60-104">Esta interfaz es una subclase de "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="96b60-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96b60-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="96b60-105">Methods</span></span>  
  
|<span data-ttu-id="96b60-106">Método</span><span class="sxs-lookup"><span data-stu-id="96b60-106">Method</span></span>|<span data-ttu-id="96b60-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="96b60-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96b60-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="96b60-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="96b60-109">Obtiene el número especificado de dominios de aplicación de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="96b60-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96b60-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96b60-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96b60-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="96b60-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96b60-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96b60-112">Requirements</span></span>  
 <span data-ttu-id="96b60-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96b60-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96b60-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96b60-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96b60-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96b60-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96b60-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96b60-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b60-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="96b60-117">See also</span></span>

- [<span data-ttu-id="96b60-118">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="96b60-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="96b60-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="96b60-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
