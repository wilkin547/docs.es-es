---
title: ICorDebugMergedAssemblyRecord::GetIndex (método)
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: b13e589e32b3317b567a4a89a5b48fc1299a1a84
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206953"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="69e65-102">ICorDebugMergedAssemblyRecord::GetIndex (método)</span><span class="sxs-lookup"><span data-stu-id="69e65-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="69e65-103">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="69e65-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e65-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69e65-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69e65-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69e65-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="69e65-106">[out] Puntero al índice de prefijo.</span><span class="sxs-lookup"><span data-stu-id="69e65-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69e65-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69e65-107">Remarks</span></span>  
 <span data-ttu-id="69e65-108">El índice de prefijo se utiliza para evitar colisiones de nombres en los nombres de tipos de metadatos combinados.</span><span class="sxs-lookup"><span data-stu-id="69e65-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69e65-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="69e65-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69e65-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69e65-110">Requirements</span></span>  
 <span data-ttu-id="69e65-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69e65-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69e65-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69e65-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69e65-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69e65-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69e65-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69e65-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e65-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69e65-115">See also</span></span>

- [<span data-ttu-id="69e65-116">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="69e65-116">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="69e65-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="69e65-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
