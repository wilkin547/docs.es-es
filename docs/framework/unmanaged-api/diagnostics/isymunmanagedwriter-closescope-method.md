---
description: 'Más información acerca de: ISymUnmanagedWriter:: Closescope ((método)'
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
ms.openlocfilehash: bb41e69955632d1e4d86250a63a9f25a7d1ae807
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762557"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="b930c-103">ISymUnmanagedWriter::CloseScope (Método)</span><span class="sxs-lookup"><span data-stu-id="b930c-103">ISymUnmanagedWriter::CloseScope Method</span></span>

<span data-ttu-id="b930c-104">Cierra el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="b930c-104">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b930c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b930c-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b930c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b930c-106">Parameters</span></span>  

 `endOffset`  
 <span data-ttu-id="b930c-107">de Desplazamiento desde el principio del método del punto al final de la última instrucción del ámbito léxico, en bytes.</span><span class="sxs-lookup"><span data-stu-id="b930c-107">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b930c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b930c-108">Return Value</span></span>  

 <span data-ttu-id="b930c-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b930c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b930c-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b930c-110">Remarks</span></span>  

 <span data-ttu-id="b930c-111">Una vez que se cierra un ámbito, no se pueden definir más variables en él.</span><span class="sxs-lookup"><span data-stu-id="b930c-111">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="b930c-112">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que se puede usar con [ISymUnmanagedWriter:: SetScopeRange (](isymunmanagedwriter-setscoperange-method.md) para definir más adelante el desplazamiento inicial y final de un ámbito.</span><span class="sxs-lookup"><span data-stu-id="b930c-112">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="b930c-113">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y `ISymUnmanagedWriter::CloseScope`.</span><span class="sxs-lookup"><span data-stu-id="b930c-113">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="b930c-114">Los identificadores de ámbito solo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="b930c-114">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b930c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b930c-115">Requirements</span></span>  

 <span data-ttu-id="b930c-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b930c-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b930c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b930c-117">See also</span></span>

- [<span data-ttu-id="b930c-118">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b930c-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
