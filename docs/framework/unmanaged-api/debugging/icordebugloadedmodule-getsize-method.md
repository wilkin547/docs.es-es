---
title: Método de ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 6a1c8c94b3c45ac995501b84bb4a69d73e7db25b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209856"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="d8fb2-102">Método de ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="d8fb2-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="d8fb2-103">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="d8fb2-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8fb2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8fb2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8fb2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8fb2-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="d8fb2-106">[out] Puntero al número de bytes del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="d8fb2-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8fb2-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d8fb2-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8fb2-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d8fb2-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8fb2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8fb2-109">Requirements</span></span>  
 <span data-ttu-id="d8fb2-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8fb2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8fb2-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8fb2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8fb2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8fb2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8fb2-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8fb2-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8fb2-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8fb2-114">See also</span></span>

- [<span data-ttu-id="d8fb2-115">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="d8fb2-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="d8fb2-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d8fb2-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
