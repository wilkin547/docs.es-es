---
title: Método ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 7d553c1a446e06f34c20da18c0edfe6773cfb597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209986"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="77e8a-102">Método ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="77e8a-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="77e8a-103">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="77e8a-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77e8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77e8a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77e8a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77e8a-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="77e8a-106">Puntero al número de bytes que este campo de instancia compensa en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="77e8a-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77e8a-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="77e8a-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77e8a-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="77e8a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77e8a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77e8a-109">Requirements</span></span>  
 <span data-ttu-id="77e8a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77e8a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77e8a-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77e8a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77e8a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77e8a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77e8a-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77e8a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e8a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77e8a-114">See also</span></span>

- [<span data-ttu-id="77e8a-115">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="77e8a-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="77e8a-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="77e8a-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
