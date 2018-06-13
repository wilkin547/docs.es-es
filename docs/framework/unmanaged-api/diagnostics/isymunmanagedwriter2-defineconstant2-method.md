---
title: ISymUnmanagedWriter2::DefineConstant2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6f9f198fc1115aed7b531515ab07ddc35d36ba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427341"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="24554-102">ISymUnmanagedWriter2::DefineConstant2 (Método)</span><span class="sxs-lookup"><span data-stu-id="24554-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="24554-103">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="24554-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24554-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24554-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24554-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24554-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="24554-106">[in] El nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="24554-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="24554-107">[in] El valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="24554-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="24554-108">[in] El token de metadatos de la constante.</span><span class="sxs-lookup"><span data-stu-id="24554-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24554-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="24554-109">Return Value</span></span>  
 <span data-ttu-id="24554-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="24554-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24554-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24554-111">Requirements</span></span>  
 <span data-ttu-id="24554-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="24554-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24554-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="24554-113">See Also</span></span>  
 [<span data-ttu-id="24554-114">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24554-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="24554-115">DefineConstant (método)</span><span class="sxs-lookup"><span data-stu-id="24554-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
