---
title: ISymUnmanagedVariable::GetSignature (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f28d6ec882afb21c3c204e141b1b6d883793004
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499061"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="9f2ed-102">ISymUnmanagedVariable::GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="9f2ed-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="9f2ed-103">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="9f2ed-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f2ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f2ed-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f2ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f2ed-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="9f2ed-106">[in] La longitud del búfer que apunta el `sig` parámetro.</span><span class="sxs-lookup"><span data-stu-id="9f2ed-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="9f2ed-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la firma.</span><span class="sxs-lookup"><span data-stu-id="9f2ed-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="9f2ed-108">[out] Búfer que almacena la firma.</span><span class="sxs-lookup"><span data-stu-id="9f2ed-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f2ed-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9f2ed-109">Return Value</span></span>  
 <span data-ttu-id="9f2ed-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9f2ed-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f2ed-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f2ed-111">Requirements</span></span>  
 <span data-ttu-id="9f2ed-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9f2ed-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f2ed-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f2ed-113">See also</span></span>
- [<span data-ttu-id="9f2ed-114">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f2ed-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
