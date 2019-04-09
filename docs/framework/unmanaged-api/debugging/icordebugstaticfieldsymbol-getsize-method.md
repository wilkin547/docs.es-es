---
title: ICorDebugStaticFieldSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9baa3632b6ede9ce45f34302611710344ed33761
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154328"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="9983a-102">ICorDebugStaticFieldSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="9983a-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="9983a-103">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="9983a-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9983a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9983a-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9983a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9983a-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="9983a-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="9983a-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9983a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9983a-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9983a-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9983a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9983a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9983a-109">Requirements</span></span>  
 <span data-ttu-id="9983a-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9983a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9983a-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9983a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9983a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9983a-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9983a-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9983a-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9983a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9983a-114">See also</span></span>

- [<span data-ttu-id="9983a-115">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="9983a-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="9983a-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9983a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
