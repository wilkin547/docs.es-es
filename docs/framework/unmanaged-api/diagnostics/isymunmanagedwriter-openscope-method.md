---
title: ISymUnmanagedWriter::OpenScope (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ea6ce91e0651e09fb908d8b8b35811349ac8845
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089437"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="86c1c-102">ISymUnmanagedWriter::OpenScope (Método)</span><span class="sxs-lookup"><span data-stu-id="86c1c-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="86c1c-103">Abre un nuevo ámbito léxico en el método actual.</span><span class="sxs-lookup"><span data-stu-id="86c1c-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="86c1c-104">El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos.</span><span class="sxs-lookup"><span data-stu-id="86c1c-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="86c1c-105">Los ámbitos deben formar una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="86c1c-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="86c1c-106">Elementos del mismo nivel no se pueden superponer.</span><span class="sxs-lookup"><span data-stu-id="86c1c-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86c1c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86c1c-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86c1c-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86c1c-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="86c1c-109">[in] El desplazamiento de la primera instrucción del ámbito léxico, en bytes, desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="86c1c-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="86c1c-110">[out] Un puntero a un `ULONG32` que recibe el identificador de ámbito.</span><span class="sxs-lookup"><span data-stu-id="86c1c-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86c1c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="86c1c-111">Return Value</span></span>  
 <span data-ttu-id="86c1c-112">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="86c1c-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86c1c-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86c1c-113">Remarks</span></span>  
 `ISymUnmanagedWriter::OpenScope` <span data-ttu-id="86c1c-114">Devuelve un identificador de ámbito opaco que puede utilizarse con [SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) definir un ámbito de desplazamiento inicial y final en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="86c1c-114">returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="86c1c-115">En este caso, los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) se omiten.</span><span class="sxs-lookup"><span data-stu-id="86c1c-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="86c1c-116">Los identificadores de ámbito sólo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="86c1c-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86c1c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86c1c-117">Requirements</span></span>  
 <span data-ttu-id="86c1c-118">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="86c1c-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c1c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="86c1c-119">See also</span></span>

- [<span data-ttu-id="86c1c-120">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86c1c-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
