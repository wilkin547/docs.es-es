---
title: ICorDebugMergedAssemblyRecord::GetIndex (método)
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca304b90cee291ef86e225c2b0691631833e53a2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917942"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="c37df-102">ICorDebugMergedAssemblyRecord::GetIndex (método)</span><span class="sxs-lookup"><span data-stu-id="c37df-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="c37df-103">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c37df-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c37df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c37df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c37df-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="c37df-106">[out] Puntero al índice de prefijo.</span><span class="sxs-lookup"><span data-stu-id="c37df-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c37df-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c37df-107">Remarks</span></span>  
 <span data-ttu-id="c37df-108">El índice de prefijo se utiliza para evitar colisiones de nombres en los nombres de tipos de metadatos combinados.</span><span class="sxs-lookup"><span data-stu-id="c37df-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c37df-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c37df-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c37df-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c37df-110">Requirements</span></span>  
 <span data-ttu-id="c37df-111">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c37df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c37df-112">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c37df-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c37df-113">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c37df-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c37df-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c37df-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37df-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c37df-115">See also</span></span>

- [<span data-ttu-id="c37df-116">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c37df-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="c37df-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c37df-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
