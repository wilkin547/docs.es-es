---
title: "ISymUnmanagedWriter::OpenScope (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f56bc14b096b5086db1fc8d046ed699559381fb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="a3b22-102">ISymUnmanagedWriter::OpenScope (Método)</span><span class="sxs-lookup"><span data-stu-id="a3b22-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="a3b22-103">Abre un nuevo ámbito léxico en el método actual.</span><span class="sxs-lookup"><span data-stu-id="a3b22-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="a3b22-104">El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos.</span><span class="sxs-lookup"><span data-stu-id="a3b22-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="a3b22-105">Los ámbitos deben formar una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="a3b22-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="a3b22-106">No se permiten que los elementos del mismo nivel se superponen.</span><span class="sxs-lookup"><span data-stu-id="a3b22-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3b22-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3b22-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3b22-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3b22-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="a3b22-109">[in] El desplazamiento de la primera instrucción del ámbito léxico, en bytes, desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="a3b22-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="a3b22-110">[out] Un puntero a un `ULONG32` que recibe el identificador de ámbito.</span><span class="sxs-lookup"><span data-stu-id="a3b22-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3b22-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3b22-111">Return Value</span></span>  
 <span data-ttu-id="a3b22-112">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a3b22-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3b22-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3b22-113">Remarks</span></span>  
 <span data-ttu-id="a3b22-114">`ISymUnmanagedWriter::OpenScope`Devuelve un identificador de ámbito opaco que puede utilizarse con [ISymUnmanagedWriter::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) definir un ámbito de desplazamiento inicial y final en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="a3b22-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="a3b22-115">En este caso, los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) se omiten.</span><span class="sxs-lookup"><span data-stu-id="a3b22-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="a3b22-116">Los identificadores de ámbito sólo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="a3b22-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3b22-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3b22-117">Requirements</span></span>  
 <span data-ttu-id="a3b22-118">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a3b22-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b22-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3b22-119">See Also</span></span>  
 [<span data-ttu-id="a3b22-120">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3b22-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
