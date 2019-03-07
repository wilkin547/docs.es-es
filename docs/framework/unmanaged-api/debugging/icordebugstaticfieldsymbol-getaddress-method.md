---
title: ICorDebugStaticFieldSymbol::GetAddress (método)
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a78df94fdc4190a43c80b0a8e3457f164e38eb00
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498060"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="47187-102">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="47187-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="47187-103">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="47187-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47187-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47187-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47187-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47187-105">Parameters</span></span>  
 <span data-ttu-id="47187-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="47187-106">pRVA</span></span>  
 <span data-ttu-id="47187-107">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="47187-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47187-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47187-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47187-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="47187-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47187-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47187-110">Requirements</span></span>  
 <span data-ttu-id="47187-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47187-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47187-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47187-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47187-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47187-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47187-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47187-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47187-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="47187-115">See also</span></span>
- [<span data-ttu-id="47187-116">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47187-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="47187-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="47187-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
