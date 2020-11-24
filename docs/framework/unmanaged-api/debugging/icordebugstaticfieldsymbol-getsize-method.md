---
title: ICorDebugStaticFieldSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: 34567247935588363d96b141717d7ec07bb76546
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677216"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="f22ff-102">ICorDebugStaticFieldSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="f22ff-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="f22ff-103">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="f22ff-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f22ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f22ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f22ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f22ff-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="f22ff-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="f22ff-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f22ff-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f22ff-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f22ff-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f22ff-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f22ff-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f22ff-109">Requirements</span></span>  

 <span data-ttu-id="f22ff-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f22ff-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f22ff-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f22ff-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f22ff-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f22ff-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f22ff-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f22ff-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22ff-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f22ff-114">See also</span></span>

- [<span data-ttu-id="f22ff-115">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="f22ff-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="f22ff-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f22ff-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
