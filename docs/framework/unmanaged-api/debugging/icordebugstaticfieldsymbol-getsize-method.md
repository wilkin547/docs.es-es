---
title: ICorDebugStaticFieldSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9baa3632b6ede9ce45f34302611710344ed33761
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154328"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="21faf-102">ICorDebugStaticFieldSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="21faf-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="21faf-103">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="21faf-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21faf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21faf-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21faf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21faf-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="21faf-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="21faf-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21faf-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21faf-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21faf-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="21faf-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21faf-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21faf-109">Requirements</span></span>  
 <span data-ttu-id="21faf-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21faf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21faf-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21faf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21faf-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21faf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21faf-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21faf-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21faf-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="21faf-114">See also</span></span>

- [<span data-ttu-id="21faf-115">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="21faf-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="21faf-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="21faf-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
