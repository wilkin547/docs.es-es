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
ms.openlocfilehash: 915b05d0d2ac611678fdcc94dd42bbb1962e6ceb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427897"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="25dd8-102">ISymUnmanagedWriter::OpenScope (Método)</span><span class="sxs-lookup"><span data-stu-id="25dd8-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="25dd8-103">Abre un nuevo ámbito léxico en el método actual.</span><span class="sxs-lookup"><span data-stu-id="25dd8-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="25dd8-104">El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos.</span><span class="sxs-lookup"><span data-stu-id="25dd8-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="25dd8-105">Los ámbitos deben formar una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="25dd8-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="25dd8-106">No se permite que los elementos del mismo nivel se superpongan.</span><span class="sxs-lookup"><span data-stu-id="25dd8-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25dd8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25dd8-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25dd8-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25dd8-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="25dd8-109">de Desplazamiento de la primera instrucción del ámbito léxico, en bytes, desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="25dd8-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="25dd8-110">enuncia Puntero a un `ULONG32` que recibe el identificador de ámbito.</span><span class="sxs-lookup"><span data-stu-id="25dd8-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25dd8-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="25dd8-111">Return Value</span></span>  
 <span data-ttu-id="25dd8-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="25dd8-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25dd8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25dd8-113">Remarks</span></span>  
 <span data-ttu-id="25dd8-114">`ISymUnmanagedWriter::OpenScope` devuelve un identificador de ámbito opaco que se puede usar con [ISymUnmanagedWriter:: SetScopeRange (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) para definir el desplazamiento inicial y final de un ámbito en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="25dd8-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="25dd8-115">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [ISymUnmanagedWriter:: closescope (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) .</span><span class="sxs-lookup"><span data-stu-id="25dd8-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="25dd8-116">Los identificadores de ámbito solo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="25dd8-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25dd8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25dd8-117">Requirements</span></span>  
 <span data-ttu-id="25dd8-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="25dd8-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25dd8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="25dd8-119">See also</span></span>

- [<span data-ttu-id="25dd8-120">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="25dd8-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
