---
title: 'ICorDebugVariableSymbol:: (método)'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 782073968030d3dcdbbe49e0ed7732fe15c4a3bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968173"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="c40af-102">ICorDebugVariableSymbol:: (método)</span><span class="sxs-lookup"><span data-stu-id="c40af-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="c40af-103">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="c40af-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c40af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c40af-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c40af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c40af-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="c40af-106">Puntero a un entero de 32 bits sin signo que contiene el tamaño de la variable.</span><span class="sxs-lookup"><span data-stu-id="c40af-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c40af-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c40af-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c40af-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c40af-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c40af-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c40af-109">Requirements</span></span>  
 <span data-ttu-id="c40af-110">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c40af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c40af-111">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c40af-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c40af-112">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c40af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c40af-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c40af-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c40af-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c40af-114">See also</span></span>

- [<span data-ttu-id="c40af-115">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c40af-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="c40af-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c40af-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
