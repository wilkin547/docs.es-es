---
title: ICorDebugMergedAssemblyRecord::GetIndex (método)
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: c8fb5ace27fbf7fbebdaca5822af99cd6673e8cf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793128"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="444a9-102">ICorDebugMergedAssemblyRecord::GetIndex (método)</span><span class="sxs-lookup"><span data-stu-id="444a9-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="444a9-103">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="444a9-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="444a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="444a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="444a9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="444a9-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="444a9-106">[out] Puntero al índice de prefijo.</span><span class="sxs-lookup"><span data-stu-id="444a9-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="444a9-107">Notas</span><span class="sxs-lookup"><span data-stu-id="444a9-107">Remarks</span></span>  
 <span data-ttu-id="444a9-108">El índice de prefijo se utiliza para evitar colisiones de nombres en los nombres de tipos de metadatos combinados.</span><span class="sxs-lookup"><span data-stu-id="444a9-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="444a9-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="444a9-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="444a9-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="444a9-110">Requirements</span></span>  
 <span data-ttu-id="444a9-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="444a9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="444a9-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="444a9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="444a9-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="444a9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="444a9-114">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="444a9-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="444a9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="444a9-115">See also</span></span>

- [<span data-ttu-id="444a9-116">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="444a9-116">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="444a9-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="444a9-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
