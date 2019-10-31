---
title: 'ICorDebugMergedAssemblyRecord:: GetIndex (método)'
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 236bd8b22d6c3ec783d787f6c906ede3193cfc1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131408"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="cee6e-102">ICorDebugMergedAssemblyRecord:: GetIndex (método)</span><span class="sxs-lookup"><span data-stu-id="cee6e-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="cee6e-103">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cee6e-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cee6e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cee6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cee6e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cee6e-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="cee6e-106">[out] Puntero al índice de prefijo.</span><span class="sxs-lookup"><span data-stu-id="cee6e-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cee6e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cee6e-107">Remarks</span></span>  
 <span data-ttu-id="cee6e-108">El índice de prefijo se utiliza para evitar colisiones de nombres en los nombres de tipos de metadatos combinados.</span><span class="sxs-lookup"><span data-stu-id="cee6e-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cee6e-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cee6e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cee6e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cee6e-110">Requirements</span></span>  
 <span data-ttu-id="cee6e-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cee6e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cee6e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cee6e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cee6e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cee6e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cee6e-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cee6e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee6e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cee6e-115">See also</span></span>

- [<span data-ttu-id="cee6e-116">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cee6e-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="cee6e-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cee6e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
