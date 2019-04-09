---
title: ICorDebugStaticFieldSymbol::GetAddress (método)
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e233fe78f6b2c721114f0307a8ca414625a0087e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160425"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="9853e-102">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="9853e-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="9853e-103">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="9853e-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9853e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9853e-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9853e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9853e-105">Parameters</span></span>  
 <span data-ttu-id="9853e-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="9853e-106">pRVA</span></span>  
 <span data-ttu-id="9853e-107">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="9853e-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9853e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9853e-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9853e-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9853e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9853e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9853e-110">Requirements</span></span>  
 <span data-ttu-id="9853e-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9853e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9853e-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9853e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9853e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9853e-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9853e-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9853e-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9853e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9853e-115">See also</span></span>

- [<span data-ttu-id="9853e-116">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="9853e-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="9853e-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9853e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
