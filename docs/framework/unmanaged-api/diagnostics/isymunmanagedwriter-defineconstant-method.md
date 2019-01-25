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
ms.openlocfilehash: e03339ff2c1205f66281bd31c3ef67439feea39c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726498"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="8db94-102">ISymUnmanagedWriter::DefineConstant (Método)</span><span class="sxs-lookup"><span data-stu-id="8db94-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="8db94-103">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="8db94-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db94-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8db94-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8db94-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8db94-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8db94-106">[in] Un puntero a un `WCHAR` que define el nombre de constante.</span><span class="sxs-lookup"><span data-stu-id="8db94-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="8db94-107">[in] El valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="8db94-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="8db94-108">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="8db94-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="8db94-109">[in] La firma de la constante de tipo.</span><span class="sxs-lookup"><span data-stu-id="8db94-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8db94-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8db94-110">Return Value</span></span>  
 <span data-ttu-id="8db94-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8db94-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8db94-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8db94-112">Requirements</span></span>  
 <span data-ttu-id="8db94-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8db94-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db94-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8db94-114">See also</span></span>
- [<span data-ttu-id="8db94-115">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8db94-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="8db94-116">DefineConstant2 (método)</span><span class="sxs-lookup"><span data-stu-id="8db94-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
