---
title: ISymUnmanagedWriter::DefineConstant (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4d19b77633ba9c35dfedad047248b69643861644
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468993"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="cd13b-102">ISymUnmanagedWriter::DefineConstant (Método)</span><span class="sxs-lookup"><span data-stu-id="cd13b-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="cd13b-103">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="cd13b-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd13b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd13b-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd13b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd13b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="cd13b-106">[in] Un puntero a un `WCHAR` que define el nombre de constante.</span><span class="sxs-lookup"><span data-stu-id="cd13b-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="cd13b-107">[in] El valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="cd13b-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="cd13b-108">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="cd13b-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="cd13b-109">[in] La firma de la constante de tipo.</span><span class="sxs-lookup"><span data-stu-id="cd13b-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd13b-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cd13b-110">Return Value</span></span>  
 <span data-ttu-id="cd13b-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="cd13b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd13b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd13b-112">Requirements</span></span>  
 <span data-ttu-id="cd13b-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cd13b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd13b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd13b-114">See also</span></span>
- [<span data-ttu-id="cd13b-115">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd13b-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="cd13b-116">DefineConstant2 (método)</span><span class="sxs-lookup"><span data-stu-id="cd13b-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
