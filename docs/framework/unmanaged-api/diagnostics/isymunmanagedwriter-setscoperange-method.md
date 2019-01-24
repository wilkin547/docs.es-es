---
title: ISymUnmanagedWriter::SetScopeRange (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da50542d9f57e008b31ce2e6ed9698df1275d5eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618817"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="c1c9b-102">ISymUnmanagedWriter::SetScopeRange (Método)</span><span class="sxs-lookup"><span data-stu-id="c1c9b-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="c1c9b-103">Define el intervalo de desplazamiento del ámbito léxico especificado.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="c1c9b-104">El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="c1c9b-105">Los ámbitos deben formar una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="c1c9b-106">Elementos del mismo nivel no se pueden superponer.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c9b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1c9b-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1c9b-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1c9b-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="c1c9b-109">[in] El identificador de ámbito para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="c1c9b-110">[in] El desplazamiento, en bytes, de la primera instrucción del ámbito léxico desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="c1c9b-111">[in] El desplazamiento, en bytes, de la última instrucción del ámbito léxico desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1c9b-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c1c9b-112">Return Value</span></span>  
 <span data-ttu-id="c1c9b-113">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1c9b-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1c9b-114">Remarks</span></span>  
 <span data-ttu-id="c1c9b-115">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que puede utilizarse con `ISymUnmanagedWriter::SetScopeRange` definir un ámbito de desplazamiento inicial y final en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="c1c9b-116">En este caso, los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) se omiten.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="c1c9b-117">Los identificadores de ámbito solo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="c1c9b-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c9b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1c9b-118">Requirements</span></span>  
 <span data-ttu-id="c1c9b-119">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c1c9b-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c9b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1c9b-120">See also</span></span>
- [<span data-ttu-id="c1c9b-121">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1c9b-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
