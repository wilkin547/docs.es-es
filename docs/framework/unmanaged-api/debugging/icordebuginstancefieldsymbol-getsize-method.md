---
title: Método ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: c4b193b45e30b0eba3367f18cb1e4c2b4e108fa8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724915"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="9d7ae-102">Método ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="9d7ae-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="9d7ae-103">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="9d7ae-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d7ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d7ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d7ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d7ae-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="9d7ae-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="9d7ae-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d7ae-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d7ae-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d7ae-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9d7ae-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d7ae-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d7ae-109">Requirements</span></span>  

 <span data-ttu-id="9d7ae-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d7ae-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d7ae-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d7ae-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d7ae-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d7ae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d7ae-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d7ae-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d7ae-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d7ae-114">See also</span></span>

- [<span data-ttu-id="9d7ae-115">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="9d7ae-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="9d7ae-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9d7ae-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
