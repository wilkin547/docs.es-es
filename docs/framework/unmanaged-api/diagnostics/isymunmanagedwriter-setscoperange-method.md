---
title: "ISymUnmanagedWriter::SetScopeRange (Método)"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9afb0038adc4273033fb9f1db1ebc57f43eae779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="f4a31-102">ISymUnmanagedWriter::SetScopeRange (Método)</span><span class="sxs-lookup"><span data-stu-id="f4a31-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="f4a31-103">Define el intervalo de desplazamiento del ámbito léxico especificado.</span><span class="sxs-lookup"><span data-stu-id="f4a31-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="f4a31-104">El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos.</span><span class="sxs-lookup"><span data-stu-id="f4a31-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="f4a31-105">Los ámbitos deben formar una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="f4a31-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="f4a31-106">No se permiten que los elementos del mismo nivel se superponen.</span><span class="sxs-lookup"><span data-stu-id="f4a31-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a31-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4a31-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4a31-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4a31-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="f4a31-109">[in] El identificador de ámbito para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f4a31-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="f4a31-110">[in] El desplazamiento, en bytes, de la primera instrucción del ámbito léxico desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="f4a31-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="f4a31-111">[in] El desplazamiento, en bytes, de la última instrucción del ámbito léxico desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="f4a31-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4a31-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f4a31-112">Return Value</span></span>  
 <span data-ttu-id="f4a31-113">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f4a31-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4a31-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4a31-114">Remarks</span></span>  
 <span data-ttu-id="f4a31-115">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que puede utilizarse con `ISymUnmanagedWriter::SetScopeRange` definir un ámbito de desplazamiento inicial y final en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="f4a31-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="f4a31-116">En este caso, los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) se omiten.</span><span class="sxs-lookup"><span data-stu-id="f4a31-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="f4a31-117">Los identificadores de ámbito sólo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="f4a31-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4a31-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4a31-118">Requirements</span></span>  
 <span data-ttu-id="f4a31-119">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f4a31-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a31-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4a31-120">See Also</span></span>  
 [<span data-ttu-id="f4a31-121">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4a31-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
