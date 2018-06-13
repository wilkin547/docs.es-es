---
title: Método de ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9768fb91749158bf3193919b2106bde1c618468a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413236"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="22a82-102">Método de ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="22a82-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="22a82-103">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="22a82-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22a82-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22a82-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22a82-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="22a82-106">[out] Puntero al número de bytes del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="22a82-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22a82-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22a82-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22a82-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="22a82-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22a82-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22a82-109">Requirements</span></span>  
 <span data-ttu-id="22a82-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22a82-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22a82-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22a82-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22a82-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22a82-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22a82-113">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22a82-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a82-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="22a82-114">See Also</span></span>  
 [<span data-ttu-id="22a82-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="22a82-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="22a82-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="22a82-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
