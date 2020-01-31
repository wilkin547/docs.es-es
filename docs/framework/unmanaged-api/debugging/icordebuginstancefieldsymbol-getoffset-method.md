---
title: Método ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: f7c13d397b39698bdf1a22f14820680e1fd0a25f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782297"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="c7edf-102">Método ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="c7edf-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="c7edf-103">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="c7edf-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7edf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7edf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7edf-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c7edf-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="c7edf-106">Puntero al número de bytes que este campo de instancia compensa en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="c7edf-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7edf-107">Notas</span><span class="sxs-lookup"><span data-stu-id="c7edf-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7edf-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c7edf-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7edf-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c7edf-109">Requirements</span></span>  
 <span data-ttu-id="c7edf-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7edf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7edf-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7edf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7edf-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7edf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7edf-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7edf-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7edf-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7edf-114">See also</span></span>

- [<span data-ttu-id="c7edf-115">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7edf-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="c7edf-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c7edf-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
