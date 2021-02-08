---
description: 'Más información sobre: ICorDebugMergedAssemblyRecord:: GetIndex (método)'
title: ICorDebugMergedAssemblyRecord::GetIndex (método)
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: f3a51c5ed5edacc9678c965ac385d0969e2ee8a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801116"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="52283-103">ICorDebugMergedAssemblyRecord::GetIndex (método)</span><span class="sxs-lookup"><span data-stu-id="52283-103">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>

<span data-ttu-id="52283-104">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52283-104">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52283-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52283-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52283-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52283-106">Parameters</span></span>  

 `pIndex`  
 <span data-ttu-id="52283-107">[out] Puntero al índice de prefijo.</span><span class="sxs-lookup"><span data-stu-id="52283-107">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52283-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52283-108">Remarks</span></span>  

 <span data-ttu-id="52283-109">El índice de prefijo se utiliza para evitar colisiones de nombres en los nombres de tipos de metadatos combinados.</span><span class="sxs-lookup"><span data-stu-id="52283-109">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52283-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="52283-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52283-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52283-111">Requirements</span></span>  

 <span data-ttu-id="52283-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52283-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52283-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52283-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52283-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52283-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52283-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52283-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52283-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="52283-116">See also</span></span>

- [<span data-ttu-id="52283-117">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="52283-117">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="52283-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="52283-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
