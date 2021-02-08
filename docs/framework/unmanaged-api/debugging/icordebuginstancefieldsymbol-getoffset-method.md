---
description: 'Más información sobre: ICorDebugInstanceFieldSymbol:: GetOffset (método)'
title: Método ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 4a877b2f78adfac5c54694ab306fd7db60f266f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791171"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="645fa-103">Método ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="645fa-103">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>

<span data-ttu-id="645fa-104">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="645fa-104">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="645fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="645fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="645fa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="645fa-106">Parameters</span></span>  

 `pcbOffset`  
 <span data-ttu-id="645fa-107">Puntero al número de bytes que este campo de instancia compensa en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="645fa-107">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="645fa-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="645fa-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="645fa-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="645fa-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="645fa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="645fa-110">Requirements</span></span>  

 <span data-ttu-id="645fa-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="645fa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="645fa-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="645fa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="645fa-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="645fa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="645fa-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="645fa-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645fa-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="645fa-115">See also</span></span>

- [<span data-ttu-id="645fa-116">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="645fa-116">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="645fa-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="645fa-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
