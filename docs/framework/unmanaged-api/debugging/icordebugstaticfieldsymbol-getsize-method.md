---
title: ICorDebugStaticFieldSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: e36c94bf411e75f915cca86aee74cdf161674d25
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379411"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="fcf26-102">ICorDebugStaticFieldSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="fcf26-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="fcf26-103">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="fcf26-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcf26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcf26-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fcf26-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="fcf26-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="fcf26-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcf26-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fcf26-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fcf26-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fcf26-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcf26-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcf26-109">Requirements</span></span>  
 <span data-ttu-id="fcf26-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcf26-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcf26-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcf26-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcf26-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcf26-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcf26-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf26-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf26-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcf26-114">See also</span></span>

- [<span data-ttu-id="fcf26-115">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="fcf26-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="fcf26-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fcf26-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
