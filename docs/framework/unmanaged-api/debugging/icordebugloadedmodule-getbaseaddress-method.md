---
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e84d6deca0cd09cc547636007208c70ab91c1ab1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223542"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="72d31-102">Método de ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="72d31-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="72d31-103">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="72d31-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72d31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72d31-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72d31-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72d31-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="72d31-106">[out] Puntero a la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="72d31-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72d31-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72d31-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72d31-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="72d31-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72d31-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72d31-109">Requirements</span></span>  
 <span data-ttu-id="72d31-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72d31-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72d31-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72d31-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72d31-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72d31-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="72d31-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="72d31-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72d31-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="72d31-114">See also</span></span>

- [<span data-ttu-id="72d31-115">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="72d31-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="72d31-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="72d31-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
