---
description: 'Más información acerca de: ICorDebugStaticFieldSymbol:: método de método'
title: ICorDebugStaticFieldSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: f6fd2fe60d7cb8a77dcff5ca259d05ae1ef195ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794694"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="f3ed2-103">ICorDebugStaticFieldSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="f3ed2-103">ICorDebugStaticFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="f3ed2-104">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="f3ed2-104">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ed2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3ed2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3ed2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3ed2-106">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="f3ed2-107">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="f3ed2-107">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3ed2-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3ed2-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3ed2-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3ed2-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3ed2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3ed2-110">Requirements</span></span>  

 <span data-ttu-id="f3ed2-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3ed2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3ed2-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3ed2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3ed2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3ed2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3ed2-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3ed2-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ed2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3ed2-115">See also</span></span>

- [<span data-ttu-id="f3ed2-116">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="f3ed2-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="f3ed2-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f3ed2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
