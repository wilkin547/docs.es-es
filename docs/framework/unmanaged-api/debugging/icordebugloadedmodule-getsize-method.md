---
title: Método de ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4601261971cce32b6d6d9ee7377f725a85103a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183474"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="264c1-102">Método de ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="264c1-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="264c1-103">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="264c1-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="264c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="264c1-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="264c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="264c1-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="264c1-106">[out] Puntero al número de bytes del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="264c1-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="264c1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="264c1-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="264c1-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="264c1-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="264c1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="264c1-109">Requirements</span></span>  
 <span data-ttu-id="264c1-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="264c1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="264c1-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="264c1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="264c1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="264c1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="264c1-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="264c1-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="264c1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="264c1-114">See also</span></span>

- [<span data-ttu-id="264c1-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="264c1-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="264c1-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="264c1-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
