---
description: 'Más información sobre: Icordebugsymbolprovider2 (:: Getframeprops ((método)'
title: ICorDebugSymbolProvider2::GetFrameProps (método)
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: c0286e423f8f395568ad4df94fac38a7ef91c6bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659561"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="c6efd-103">ICorDebugSymbolProvider2::GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="c6efd-103">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>

<span data-ttu-id="c6efd-104">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="c6efd-104">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6efd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6efd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6efd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6efd-106">Parameters</span></span>  

 `codeRva`  
 <span data-ttu-id="c6efd-107">[in] Dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="c6efd-107">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="c6efd-108">[out] Puntero a la dirección virtual relativa de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="c6efd-108">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="c6efd-109">[out] Puntero a la dirección virtual relativa de inicio del marco.</span><span class="sxs-lookup"><span data-stu-id="c6efd-109">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6efd-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c6efd-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6efd-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c6efd-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6efd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6efd-112">Requirements</span></span>  

 <span data-ttu-id="c6efd-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6efd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6efd-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6efd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6efd-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6efd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6efd-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6efd-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6efd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6efd-117">See also</span></span>

- [<span data-ttu-id="c6efd-118">Interfaz ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="c6efd-118">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="c6efd-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c6efd-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
