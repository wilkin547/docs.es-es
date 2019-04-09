---
title: Método ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103768918f67ca695a47c52b9cd97f24fb8d46ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081585"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="c1767-102">Método ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="c1767-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="c1767-103">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="c1767-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1767-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1767-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1767-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1767-105">Parameters</span></span>  
 <span data-ttu-id="c1767-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="c1767-106">ppThread</span></span>  
 <span data-ttu-id="c1767-107">[out] Un puntero a la dirección de un objeto ICorDebugThread que representa el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="c1767-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1767-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1767-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1767-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c1767-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1767-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1767-110">Requirements</span></span>  
 <span data-ttu-id="c1767-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1767-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1767-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1767-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1767-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1767-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c1767-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c1767-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1767-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1767-115">See also</span></span>

- [<span data-ttu-id="c1767-116">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c1767-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="c1767-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c1767-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
