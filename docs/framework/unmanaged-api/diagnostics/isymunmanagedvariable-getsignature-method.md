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
ms.openlocfilehash: 3cc616246812bb9643388d8ad57cf84bc387b55e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797506"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="0ca94-102">ISymUnmanagedVariable::GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="0ca94-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="0ca94-103">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="0ca94-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca94-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ca94-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ca94-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ca94-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="0ca94-106">[in] La longitud del búfer que apunta el `sig` parámetro.</span><span class="sxs-lookup"><span data-stu-id="0ca94-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="0ca94-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la firma.</span><span class="sxs-lookup"><span data-stu-id="0ca94-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="0ca94-108">[out] Búfer que almacena la firma.</span><span class="sxs-lookup"><span data-stu-id="0ca94-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ca94-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0ca94-109">Return Value</span></span>  
 <span data-ttu-id="0ca94-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0ca94-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ca94-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ca94-111">Requirements</span></span>  
 <span data-ttu-id="0ca94-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0ca94-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca94-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ca94-113">See also</span></span>

- [<span data-ttu-id="0ca94-114">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ca94-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
