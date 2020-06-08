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
ms.openlocfilehash: e2e911fb1d737ebb6b2106c89ac11335788ace4f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501734"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="8107a-102">ISymUnmanagedWriter::CloseScope (Método)</span><span class="sxs-lookup"><span data-stu-id="8107a-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="8107a-103">Cierra el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="8107a-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8107a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8107a-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8107a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8107a-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="8107a-106">de Desplazamiento desde el principio del método del punto al final de la última instrucción del ámbito léxico, en bytes.</span><span class="sxs-lookup"><span data-stu-id="8107a-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8107a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8107a-107">Return Value</span></span>  
 <span data-ttu-id="8107a-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8107a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8107a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8107a-109">Remarks</span></span>  
 <span data-ttu-id="8107a-110">Una vez que se cierra un ámbito, no se pueden definir más variables en él.</span><span class="sxs-lookup"><span data-stu-id="8107a-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="8107a-111">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que se puede usar con [ISymUnmanagedWriter:: SetScopeRange (](isymunmanagedwriter-setscoperange-method.md) para definir más adelante el desplazamiento inicial y final de un ámbito.</span><span class="sxs-lookup"><span data-stu-id="8107a-111">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="8107a-112">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y `ISymUnmanagedWriter::CloseScope`.</span><span class="sxs-lookup"><span data-stu-id="8107a-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="8107a-113">Los identificadores de ámbito solo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="8107a-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8107a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8107a-114">Requirements</span></span>  
 <span data-ttu-id="8107a-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8107a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8107a-116">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="8107a-116">See also</span></span>

- [<span data-ttu-id="8107a-117">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8107a-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
