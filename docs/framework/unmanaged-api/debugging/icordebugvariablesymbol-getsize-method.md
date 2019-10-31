---
title: 'ICorDebugVariableSymbol:: (método)'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 61dad9522f9171166ca56a97e68b9a149d35e49a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121007"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="9d4ac-102">ICorDebugVariableSymbol:: (método)</span><span class="sxs-lookup"><span data-stu-id="9d4ac-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="9d4ac-103">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="9d4ac-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d4ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d4ac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d4ac-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="9d4ac-106">Puntero a un entero de 32 bits sin signo que contiene el tamaño de la variable.</span><span class="sxs-lookup"><span data-stu-id="9d4ac-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d4ac-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d4ac-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d4ac-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9d4ac-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d4ac-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d4ac-109">Requirements</span></span>  
 <span data-ttu-id="9d4ac-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d4ac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d4ac-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d4ac-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d4ac-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d4ac-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d4ac-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d4ac-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d4ac-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d4ac-114">See also</span></span>

- [<span data-ttu-id="9d4ac-115">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d4ac-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="9d4ac-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9d4ac-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
