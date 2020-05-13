---
title: ICorDebugSymbolProvider2::GetFrameProps (método)
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: ad44c5a7b2d901967ae354f3c30218a8c7f2c2de
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379331"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="a7755-102">ICorDebugSymbolProvider2::GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="a7755-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="a7755-103">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="a7755-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7755-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7755-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7755-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7755-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="a7755-106">[in] Dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="a7755-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="a7755-107">[out] Puntero a la dirección virtual relativa de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="a7755-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="a7755-108">[out] Puntero a la dirección virtual relativa de inicio del marco.</span><span class="sxs-lookup"><span data-stu-id="a7755-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7755-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a7755-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7755-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a7755-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7755-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7755-111">Requirements</span></span>  
 <span data-ttu-id="a7755-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7755-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7755-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7755-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7755-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7755-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7755-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7755-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7755-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7755-116">See also</span></span>

- [<span data-ttu-id="a7755-117">Interfaz ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="a7755-117">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="a7755-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a7755-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
