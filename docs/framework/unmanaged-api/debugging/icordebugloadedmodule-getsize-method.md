---
title: Método de ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4601261971cce32b6d6d9ee7377f725a85103a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183474"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="ea156-102">Método de ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="ea156-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="ea156-103">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="ea156-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea156-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea156-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea156-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea156-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="ea156-106">[out] Puntero al número de bytes del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="ea156-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea156-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea156-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea156-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ea156-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea156-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea156-109">Requirements</span></span>  
 <span data-ttu-id="ea156-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea156-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea156-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea156-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea156-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea156-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ea156-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ea156-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea156-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea156-114">See also</span></span>

- [<span data-ttu-id="ea156-115">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="ea156-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="ea156-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ea156-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
