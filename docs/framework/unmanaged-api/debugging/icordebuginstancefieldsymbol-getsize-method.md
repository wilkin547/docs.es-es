---
title: Método ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: 3d3c6881ecd54fc48be92e5ea0dc74a5cfdabd8f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209958"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="923bc-102">Método ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="923bc-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="923bc-103">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="923bc-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="923bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="923bc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="923bc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="923bc-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="923bc-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="923bc-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="923bc-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="923bc-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="923bc-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="923bc-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="923bc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="923bc-109">Requirements</span></span>  
 <span data-ttu-id="923bc-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="923bc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="923bc-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="923bc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="923bc-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="923bc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="923bc-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="923bc-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="923bc-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="923bc-114">See also</span></span>

- [<span data-ttu-id="923bc-115">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="923bc-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="923bc-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="923bc-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
