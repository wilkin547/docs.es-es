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
ms.openlocfilehash: a1da070f261f224d212d1fba81c287285a54d0d0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501697"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="80e7f-102">ISymUnmanagedWriter::SetScopeRange (Método)</span><span class="sxs-lookup"><span data-stu-id="80e7f-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="80e7f-103">Define el intervalo de desplazamiento del ámbito léxico especificado.</span><span class="sxs-lookup"><span data-stu-id="80e7f-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="80e7f-104">El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos.</span><span class="sxs-lookup"><span data-stu-id="80e7f-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="80e7f-105">Los ámbitos deben formar una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="80e7f-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="80e7f-106">No se permite que los elementos del mismo nivel se superpongan.</span><span class="sxs-lookup"><span data-stu-id="80e7f-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80e7f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80e7f-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80e7f-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80e7f-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="80e7f-109">de Identificador de ámbito para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="80e7f-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="80e7f-110">de Desplazamiento, en bytes, de la primera instrucción del ámbito léxico desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="80e7f-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="80e7f-111">de Desplazamiento, en bytes, de la última instrucción del ámbito léxico desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="80e7f-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80e7f-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80e7f-112">Return Value</span></span>  
 <span data-ttu-id="80e7f-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="80e7f-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80e7f-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80e7f-114">Remarks</span></span>  
 <span data-ttu-id="80e7f-115">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que se puede usar con `ISymUnmanagedWriter::SetScopeRange` para definir el desplazamiento inicial y final de un ámbito en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="80e7f-115">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="80e7f-116">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [ISymUnmanagedWriter:: closescope (](isymunmanagedwriter-closescope-method.md) .</span><span class="sxs-lookup"><span data-stu-id="80e7f-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="80e7f-117">Los identificadores de ámbito solo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="80e7f-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80e7f-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80e7f-118">Requirements</span></span>  
 <span data-ttu-id="80e7f-119">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="80e7f-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80e7f-120">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="80e7f-120">See also</span></span>

- [<span data-ttu-id="80e7f-121">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80e7f-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
