---
description: 'Más información acerca de: ICorDebugInstanceFieldSymbol:: método de método'
title: Método ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: fa143620b57ec053ab26ff79b7ea2b2f386431e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791158"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="206ea-103">Método ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="206ea-103">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="206ea-104">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="206ea-104">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="206ea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="206ea-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="206ea-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="206ea-106">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="206ea-107">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="206ea-107">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="206ea-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="206ea-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="206ea-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="206ea-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="206ea-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="206ea-110">Requirements</span></span>  

 <span data-ttu-id="206ea-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="206ea-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="206ea-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="206ea-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="206ea-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="206ea-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="206ea-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="206ea-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="206ea-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="206ea-115">See also</span></span>

- [<span data-ttu-id="206ea-116">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="206ea-116">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="206ea-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="206ea-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
