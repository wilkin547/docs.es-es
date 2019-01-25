---
title: ISymUnmanagedWriter::CloseScope (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e33d69e319d7817a54dca76526b6c3ee9bb6384f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729975"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="fea1d-102">ISymUnmanagedWriter::CloseScope (Método)</span><span class="sxs-lookup"><span data-stu-id="fea1d-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="fea1d-103">Cierra el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="fea1d-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fea1d-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fea1d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fea1d-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="fea1d-106">[in] El desplazamiento desde el principio del método del punto al final de la última instrucción del ámbito léxico, en bytes.</span><span class="sxs-lookup"><span data-stu-id="fea1d-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fea1d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fea1d-107">Return Value</span></span>  
 <span data-ttu-id="fea1d-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="fea1d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fea1d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fea1d-109">Remarks</span></span>  
 <span data-ttu-id="fea1d-110">Una vez cerrado un ámbito, no hay más variables se pueden definir dentro de él.</span><span class="sxs-lookup"><span data-stu-id="fea1d-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="fea1d-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que puede utilizarse con [SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) definir más adelante un ámbito de desplazamiento inicial y final.</span><span class="sxs-lookup"><span data-stu-id="fea1d-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="fea1d-112">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y `ISymUnmanagedWriter::CloseScope`.</span><span class="sxs-lookup"><span data-stu-id="fea1d-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="fea1d-113">Los identificadores de ámbito sólo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="fea1d-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fea1d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fea1d-114">Requirements</span></span>  
 <span data-ttu-id="fea1d-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fea1d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea1d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fea1d-116">See also</span></span>
- [<span data-ttu-id="fea1d-117">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fea1d-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
