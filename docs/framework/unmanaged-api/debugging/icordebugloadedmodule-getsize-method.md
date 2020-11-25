---
title: Método de ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 2ed19cb4a190f2af7581a827e8bd11b748b3d4a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721327"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="7cf97-102">Método de ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="7cf97-102">ICorDebugLoadedModule::GetSize Method</span></span>

<span data-ttu-id="7cf97-103">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="7cf97-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cf97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cf97-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7cf97-105">Parameters</span></span>  

 `pcBytes`  
 <span data-ttu-id="7cf97-106">[out] Puntero al número de bytes del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="7cf97-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cf97-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7cf97-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7cf97-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7cf97-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cf97-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cf97-109">Requirements</span></span>  

 <span data-ttu-id="7cf97-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cf97-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf97-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cf97-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cf97-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cf97-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cf97-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cf97-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf97-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7cf97-114">See also</span></span>

- [<span data-ttu-id="7cf97-115">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="7cf97-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="7cf97-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7cf97-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
