---
title: "ICorDebugMergedAssemblyRecord::GetIndex (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dac64c785077fc3901e712498e66e11b9c9f3279
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="41cd9-102">ICorDebugMergedAssemblyRecord::GetIndex (método)</span><span class="sxs-lookup"><span data-stu-id="41cd9-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="41cd9-103">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="41cd9-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41cd9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41cd9-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41cd9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41cd9-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="41cd9-106">[out] Puntero al índice de prefijo.</span><span class="sxs-lookup"><span data-stu-id="41cd9-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41cd9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41cd9-107">Remarks</span></span>  
 <span data-ttu-id="41cd9-108">El índice de prefijo se utiliza para evitar colisiones de nombres en los nombres de tipos de metadatos combinados.</span><span class="sxs-lookup"><span data-stu-id="41cd9-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41cd9-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="41cd9-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41cd9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41cd9-110">Requirements</span></span>  
 <span data-ttu-id="41cd9-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41cd9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41cd9-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41cd9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41cd9-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41cd9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41cd9-114">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41cd9-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cd9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="41cd9-115">See Also</span></span>  
 [<span data-ttu-id="41cd9-116">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41cd9-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="41cd9-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="41cd9-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
