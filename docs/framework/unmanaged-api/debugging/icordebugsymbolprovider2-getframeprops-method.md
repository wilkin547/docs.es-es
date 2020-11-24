---
title: ICorDebugSymbolProvider2::GetFrameProps (método)
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: ba1fd104c35b6e6dfdfd771f71eb19f8d532a1d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672016"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="a8e95-102">ICorDebugSymbolProvider2::GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="a8e95-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>

<span data-ttu-id="a8e95-103">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="a8e95-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8e95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8e95-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8e95-105">Parameters</span></span>  

 `codeRva`  
 <span data-ttu-id="a8e95-106">[in] Dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="a8e95-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="a8e95-107">[out] Puntero a la dirección virtual relativa de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="a8e95-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="a8e95-108">[out] Puntero a la dirección virtual relativa de inicio del marco.</span><span class="sxs-lookup"><span data-stu-id="a8e95-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8e95-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8e95-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8e95-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a8e95-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8e95-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8e95-111">Requirements</span></span>  

 <span data-ttu-id="a8e95-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8e95-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8e95-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8e95-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8e95-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8e95-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8e95-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8e95-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e95-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8e95-116">See also</span></span>

- [<span data-ttu-id="a8e95-117">Interfaz ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="a8e95-117">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="a8e95-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a8e95-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
