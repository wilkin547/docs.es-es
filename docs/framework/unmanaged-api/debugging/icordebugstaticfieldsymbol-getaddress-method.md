---
title: ICorDebugStaticFieldSymbol::GetAddress (método)
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 7b8072234df172eeafd77db90287ea3319c08ec7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378767"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="85d81-102">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="85d81-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="85d81-103">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="85d81-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d81-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85d81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85d81-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85d81-105">Parameters</span></span>  
 <span data-ttu-id="85d81-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="85d81-106">pRVA</span></span>  
 <span data-ttu-id="85d81-107">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="85d81-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85d81-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="85d81-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85d81-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="85d81-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85d81-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85d81-110">Requirements</span></span>  
 <span data-ttu-id="85d81-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85d81-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85d81-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85d81-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85d81-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85d81-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85d81-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85d81-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d81-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85d81-115">See also</span></span>

- [<span data-ttu-id="85d81-116">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="85d81-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="85d81-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="85d81-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
