---
title: "Método de ICorDebugLoadedModule::GetBaseAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d71b1db35a9e2747e7e14787f385f42f98305c61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="bbccd-102">Método de ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="bbccd-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="bbccd-103">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="bbccd-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbccd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbccd-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbccd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bbccd-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="bbccd-106">[out] Puntero a la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="bbccd-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbccd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bbccd-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbccd-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bbccd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbccd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbccd-109">Requirements</span></span>  
 <span data-ttu-id="bbccd-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbccd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbccd-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbccd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbccd-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbccd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbccd-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbccd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbccd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbccd-114">See Also</span></span>  
 [<span data-ttu-id="bbccd-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bbccd-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="bbccd-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bbccd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
