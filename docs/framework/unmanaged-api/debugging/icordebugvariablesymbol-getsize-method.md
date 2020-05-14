---
title: ICorDebugVariableSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: d924de33c8ec49501be0ee7700b2eee8c79bb950
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397109"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="7c542-102">ICorDebugVariableSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="7c542-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="7c542-103">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="7c542-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c542-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c542-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c542-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c542-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="7c542-106">Puntero a un entero de 32 bits sin signo que contiene el tamaño de la variable.</span><span class="sxs-lookup"><span data-stu-id="7c542-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c542-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c542-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c542-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7c542-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c542-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c542-109">Requirements</span></span>  
 <span data-ttu-id="7c542-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c542-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c542-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c542-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c542-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c542-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c542-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c542-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c542-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c542-114">See also</span></span>

- [<span data-ttu-id="7c542-115">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="7c542-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="7c542-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7c542-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
