---
title: "Método ICorDebugInstanceFieldSymbol::GetOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 534e3238a4b20e390c4f2168629e0ba93620f55a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="e75b9-102">Método ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="e75b9-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="e75b9-103">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="e75b9-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e75b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e75b9-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e75b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e75b9-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="e75b9-106">Puntero al número de bytes que este campo de instancia compensa en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="e75b9-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e75b9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e75b9-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e75b9-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e75b9-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e75b9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e75b9-109">Requirements</span></span>  
 <span data-ttu-id="e75b9-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e75b9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e75b9-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e75b9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e75b9-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e75b9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e75b9-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e75b9-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75b9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e75b9-114">See Also</span></span>  
 [<span data-ttu-id="e75b9-115">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e75b9-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="e75b9-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e75b9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
