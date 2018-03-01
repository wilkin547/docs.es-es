---
title: "ISymUnmanagedWriter::SetMethodSourceRange (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09f82be130dba8087cf649d3e89bec8afc065e86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="84397-102">ISymUnmanagedWriter::SetMethodSourceRange (Método)</span><span class="sxs-lookup"><span data-stu-id="84397-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="84397-103">Especifica true inicial y final de un método dentro de un archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="84397-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="84397-104">Utilice este método para especificar el alcance de un método, independientemente de los puntos de secuencia que existan dentro del método.</span><span class="sxs-lookup"><span data-stu-id="84397-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84397-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84397-105">Syntax</span></span>  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84397-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84397-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="84397-107">[in] Un puntero al documento que contiene la posición inicial.</span><span class="sxs-lookup"><span data-stu-id="84397-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="84397-108">[in] El número de línea inicial.</span><span class="sxs-lookup"><span data-stu-id="84397-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="84397-109">[in] La columna inicial.</span><span class="sxs-lookup"><span data-stu-id="84397-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="84397-110">[in] Un puntero al documento que contiene la posición final.</span><span class="sxs-lookup"><span data-stu-id="84397-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="84397-111">[in] El número de línea final.</span><span class="sxs-lookup"><span data-stu-id="84397-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="84397-112">[in] El número de columna final.</span><span class="sxs-lookup"><span data-stu-id="84397-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84397-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="84397-113">Return Value</span></span>  
 <span data-ttu-id="84397-114">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="84397-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84397-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84397-115">Requirements</span></span>  
 <span data-ttu-id="84397-116">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="84397-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84397-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="84397-117">See Also</span></span>  
 [<span data-ttu-id="84397-118">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84397-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
