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
ms.openlocfilehash: 561a6348b9976789b02961fadb37d9127f5a6a13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713046"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="3f296-102">ISymUnmanagedWriter::CloseScope (Método)</span><span class="sxs-lookup"><span data-stu-id="3f296-102">ISymUnmanagedWriter::CloseScope Method</span></span>

<span data-ttu-id="3f296-103">Cierra el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="3f296-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f296-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f296-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f296-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f296-105">Parameters</span></span>  

 `endOffset`  
 <span data-ttu-id="3f296-106">de Desplazamiento desde el principio del método del punto al final de la última instrucción del ámbito léxico, en bytes.</span><span class="sxs-lookup"><span data-stu-id="3f296-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f296-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3f296-107">Return Value</span></span>  

 <span data-ttu-id="3f296-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3f296-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f296-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f296-109">Remarks</span></span>  

 <span data-ttu-id="3f296-110">Una vez que se cierra un ámbito, no se pueden definir más variables en él.</span><span class="sxs-lookup"><span data-stu-id="3f296-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="3f296-111">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que se puede usar con [ISymUnmanagedWriter:: SetScopeRange (](isymunmanagedwriter-setscoperange-method.md) para definir más adelante el desplazamiento inicial y final de un ámbito.</span><span class="sxs-lookup"><span data-stu-id="3f296-111">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="3f296-112">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y `ISymUnmanagedWriter::CloseScope`.</span><span class="sxs-lookup"><span data-stu-id="3f296-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="3f296-113">Los identificadores de ámbito solo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="3f296-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f296-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f296-114">Requirements</span></span>  

 <span data-ttu-id="3f296-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3f296-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f296-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f296-116">See also</span></span>

- [<span data-ttu-id="3f296-117">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f296-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
