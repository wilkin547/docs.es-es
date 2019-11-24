---
title: ISymUnmanagedWriter3::OpenMethod2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: 3a628aec0823c5db07d31d33813a020606906163
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438129"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="194af-102">ISymUnmanagedWriter3::OpenMethod2 (Método)</span><span class="sxs-lookup"><span data-stu-id="194af-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="194af-103">Opens a method and provides its real section offset in the image.</span><span class="sxs-lookup"><span data-stu-id="194af-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="194af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="194af-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="194af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="194af-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="194af-106">[in] The metadata token for the method to be opened.</span><span class="sxs-lookup"><span data-stu-id="194af-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="194af-107">[in] The section offset in the image.</span><span class="sxs-lookup"><span data-stu-id="194af-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="194af-108">[in] The offset in the image.</span><span class="sxs-lookup"><span data-stu-id="194af-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="194af-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="194af-109">Return Value</span></span>  
 <span data-ttu-id="194af-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="194af-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="194af-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="194af-111">Requirements</span></span>  
 <span data-ttu-id="194af-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="194af-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="194af-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="194af-113">See also</span></span>

- [<span data-ttu-id="194af-114">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="194af-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="194af-115">OpenMethod (método)</span><span class="sxs-lookup"><span data-stu-id="194af-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
