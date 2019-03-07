---
title: ISymUnmanagedConstant::GetSignature (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb893f06a5e905b981a408887f1c6bf5718ea79a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498567"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="c5dc2-102">ISymUnmanagedConstant::GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="c5dc2-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="c5dc2-103">Obtiene la firma de la constante.</span><span class="sxs-lookup"><span data-stu-id="c5dc2-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5dc2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5dc2-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5dc2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5dc2-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="c5dc2-106">[in] La longitud del búfer que el `pcSig` parámetro señala.</span><span class="sxs-lookup"><span data-stu-id="c5dc2-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="c5dc2-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la firma.</span><span class="sxs-lookup"><span data-stu-id="c5dc2-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="c5dc2-108">[out] Búfer que almacena la firma.</span><span class="sxs-lookup"><span data-stu-id="c5dc2-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5dc2-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c5dc2-109">Return Value</span></span>  
 <span data-ttu-id="c5dc2-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c5dc2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5dc2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5dc2-111">Requirements</span></span>  
 <span data-ttu-id="c5dc2-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c5dc2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5dc2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5dc2-113">See also</span></span>
- [<span data-ttu-id="c5dc2-114">ISymUnmanagedConstant (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5dc2-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="c5dc2-115">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="c5dc2-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="c5dc2-116">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="c5dc2-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
