---
description: 'Más información acerca de: ISymUnmanagedWriter:: OpenScope (método)'
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
ms.openlocfilehash: 1e47d97941b053fedcf08c7582e1083988a9fed4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762115"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="33d25-103">ISymUnmanagedWriter::OpenScope (Método)</span><span class="sxs-lookup"><span data-stu-id="33d25-103">ISymUnmanagedWriter::OpenScope Method</span></span>

<span data-ttu-id="33d25-104">Abre un nuevo ámbito léxico en el método actual.</span><span class="sxs-lookup"><span data-stu-id="33d25-104">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="33d25-105">El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos.</span><span class="sxs-lookup"><span data-stu-id="33d25-105">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="33d25-106">Los ámbitos deben formar una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="33d25-106">Scopes must form a hierarchy.</span></span> <span data-ttu-id="33d25-107">No se permite que los elementos del mismo nivel se superpongan.</span><span class="sxs-lookup"><span data-stu-id="33d25-107">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33d25-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33d25-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33d25-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33d25-109">Parameters</span></span>  

 `startOffset`  
 <span data-ttu-id="33d25-110">de Desplazamiento de la primera instrucción del ámbito léxico, en bytes, desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="33d25-110">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="33d25-111">enuncia Un puntero a un `ULONG32` que recibe el identificador de ámbito.</span><span class="sxs-lookup"><span data-stu-id="33d25-111">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33d25-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33d25-112">Return Value</span></span>  

 <span data-ttu-id="33d25-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="33d25-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33d25-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33d25-114">Remarks</span></span>  

 <span data-ttu-id="33d25-115">`ISymUnmanagedWriter::OpenScope` Devuelve un identificador de ámbito opaco que se puede usar con [ISymUnmanagedWriter:: SetScopeRange (](isymunmanagedwriter-setscoperange-method.md) para definir el desplazamiento inicial y final de un ámbito en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="33d25-115">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="33d25-116">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [ISymUnmanagedWriter:: closescope (](isymunmanagedwriter-closescope-method.md) .</span><span class="sxs-lookup"><span data-stu-id="33d25-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="33d25-117">Los identificadores de ámbito solo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="33d25-117">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33d25-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33d25-118">Requirements</span></span>  

 <span data-ttu-id="33d25-119">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="33d25-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d25-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="33d25-120">See also</span></span>

- [<span data-ttu-id="33d25-121">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33d25-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
