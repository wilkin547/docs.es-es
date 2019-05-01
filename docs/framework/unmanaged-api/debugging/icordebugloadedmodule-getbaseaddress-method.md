---
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e84d6deca0cd09cc547636007208c70ab91c1ab1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946295"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="85c26-102">Método de ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="85c26-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="85c26-103">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="85c26-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85c26-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85c26-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85c26-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="85c26-106">[out] Puntero a la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="85c26-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85c26-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85c26-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85c26-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="85c26-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c26-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85c26-109">Requirements</span></span>  
 <span data-ttu-id="85c26-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85c26-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85c26-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85c26-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85c26-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85c26-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85c26-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85c26-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c26-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="85c26-114">See also</span></span>

- [<span data-ttu-id="85c26-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85c26-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="85c26-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="85c26-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
