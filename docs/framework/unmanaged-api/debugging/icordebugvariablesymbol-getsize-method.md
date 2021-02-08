---
description: 'Más información acerca de: ICorDebugVariableSymbol:: método de método'
title: ICorDebugVariableSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: f4098bf5e053ab66dd7966d4b665cfad4dee01d5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790586"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="e8b4b-103">ICorDebugVariableSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="e8b4b-103">ICorDebugVariableSymbol::GetSize Method</span></span>

<span data-ttu-id="e8b4b-104">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="e8b4b-104">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8b4b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8b4b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8b4b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8b4b-106">Parameters</span></span>  

 `pcbValue`  
 <span data-ttu-id="e8b4b-107">Puntero a un entero de 32 bits sin signo que contiene el tamaño de la variable.</span><span class="sxs-lookup"><span data-stu-id="e8b4b-107">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8b4b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e8b4b-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8b4b-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e8b4b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8b4b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8b4b-110">Requirements</span></span>  

 <span data-ttu-id="e8b4b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8b4b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8b4b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8b4b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8b4b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8b4b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8b4b-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8b4b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b4b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8b4b-115">See also</span></span>

- [<span data-ttu-id="e8b4b-116">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="e8b4b-116">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="e8b4b-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e8b4b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
