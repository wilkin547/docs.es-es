---
description: 'Más información acerca de: ISymUnmanagedWriter:: SetScopeRange ((método)'
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
ms.openlocfilehash: 43cfbeaa0d366b9f2d25068cfa7b91a0fea8ac59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762063"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="52745-103">ISymUnmanagedWriter::SetScopeRange (Método)</span><span class="sxs-lookup"><span data-stu-id="52745-103">ISymUnmanagedWriter::SetScopeRange Method</span></span>

<span data-ttu-id="52745-104">Define el intervalo de desplazamiento del ámbito léxico especificado.</span><span class="sxs-lookup"><span data-stu-id="52745-104">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="52745-105">El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos.</span><span class="sxs-lookup"><span data-stu-id="52745-105">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="52745-106">Los ámbitos deben formar una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="52745-106">Scopes must form a hierarchy.</span></span> <span data-ttu-id="52745-107">No se permite que los elementos del mismo nivel se superpongan.</span><span class="sxs-lookup"><span data-stu-id="52745-107">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52745-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52745-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52745-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52745-109">Parameters</span></span>  

 `scopeId`  
 <span data-ttu-id="52745-110">de Identificador de ámbito para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="52745-110">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="52745-111">de Desplazamiento, en bytes, de la primera instrucción del ámbito léxico desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="52745-111">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="52745-112">de Desplazamiento, en bytes, de la última instrucción del ámbito léxico desde el principio del método.</span><span class="sxs-lookup"><span data-stu-id="52745-112">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52745-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52745-113">Return Value</span></span>  

 <span data-ttu-id="52745-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="52745-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52745-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52745-115">Remarks</span></span>  

 <span data-ttu-id="52745-116">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que se puede usar con `ISymUnmanagedWriter::SetScopeRange` para definir el desplazamiento inicial y final de un ámbito en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="52745-116">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="52745-117">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [ISymUnmanagedWriter:: closescope (](isymunmanagedwriter-closescope-method.md) .</span><span class="sxs-lookup"><span data-stu-id="52745-117">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="52745-118">Los identificadores de ámbito solo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="52745-118">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52745-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52745-119">Requirements</span></span>  

 <span data-ttu-id="52745-120">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="52745-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52745-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="52745-121">See also</span></span>

- [<span data-ttu-id="52745-122">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="52745-122">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
