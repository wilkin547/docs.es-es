---
title: ICorDebugVariableSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 6d60dbdefd09770fd5a18653c5118469323581e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790910"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="57f7f-102">ICorDebugVariableSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="57f7f-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="57f7f-103">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="57f7f-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57f7f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57f7f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57f7f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="57f7f-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="57f7f-106">Puntero a un entero de 32 bits sin signo que contiene el tamaño de la variable.</span><span class="sxs-lookup"><span data-stu-id="57f7f-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57f7f-107">Notas</span><span class="sxs-lookup"><span data-stu-id="57f7f-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57f7f-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="57f7f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57f7f-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="57f7f-109">Requirements</span></span>  
 <span data-ttu-id="57f7f-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57f7f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57f7f-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57f7f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57f7f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57f7f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57f7f-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57f7f-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f7f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="57f7f-114">See also</span></span>

- [<span data-ttu-id="57f7f-115">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="57f7f-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="57f7f-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="57f7f-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
