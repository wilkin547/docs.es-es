---
title: "ISymUnmanagedVariable::GetSignature (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ee403a5f92ba4eb88eca880d9bf2f858b52d4f05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="b8ad1-102">ISymUnmanagedVariable::GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="b8ad1-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="b8ad1-103">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="b8ad1-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8ad1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8ad1-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8ad1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8ad1-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="b8ad1-106">[in] La longitud del búfer que señala el `sig` parámetro.</span><span class="sxs-lookup"><span data-stu-id="b8ad1-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="b8ad1-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la firma.</span><span class="sxs-lookup"><span data-stu-id="b8ad1-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="b8ad1-108">[out] Búfer que almacena la firma.</span><span class="sxs-lookup"><span data-stu-id="b8ad1-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8ad1-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b8ad1-109">Return Value</span></span>  
 <span data-ttu-id="b8ad1-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b8ad1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8ad1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8ad1-111">Requirements</span></span>  
 <span data-ttu-id="b8ad1-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b8ad1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ad1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8ad1-113">See Also</span></span>  
 [<span data-ttu-id="b8ad1-114">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8ad1-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
