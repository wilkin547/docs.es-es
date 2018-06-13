---
title: ICorDebugStaticFieldSymbol::GetAddress (método)
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b877bde80b59b7d2074e4d799653dedd5aaacf39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419258"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="21a83-102">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="21a83-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="21a83-103">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="21a83-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a83-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21a83-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21a83-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21a83-105">Parameters</span></span>  
 <span data-ttu-id="21a83-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="21a83-106">pRVA</span></span>  
 <span data-ttu-id="21a83-107">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="21a83-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21a83-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21a83-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21a83-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="21a83-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21a83-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21a83-110">Requirements</span></span>  
 <span data-ttu-id="21a83-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21a83-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21a83-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21a83-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21a83-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21a83-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21a83-114">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21a83-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a83-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="21a83-115">See Also</span></span>  
 [<span data-ttu-id="21a83-116">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="21a83-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="21a83-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="21a83-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
