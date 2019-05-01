---
title: Método ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8ea777755aebb59f3e865df26c38c74ef68ae31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946409"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="2ab1f-102">Método ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="2ab1f-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="2ab1f-103">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="2ab1f-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab1f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ab1f-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ab1f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ab1f-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="2ab1f-106">Puntero al número de bytes que este campo de instancia compensa en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="2ab1f-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ab1f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ab1f-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ab1f-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2ab1f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ab1f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ab1f-109">Requirements</span></span>  
 <span data-ttu-id="2ab1f-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ab1f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab1f-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ab1f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ab1f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ab1f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ab1f-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab1f-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab1f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ab1f-114">See also</span></span>

- [<span data-ttu-id="2ab1f-115">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ab1f-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="2ab1f-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2ab1f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
