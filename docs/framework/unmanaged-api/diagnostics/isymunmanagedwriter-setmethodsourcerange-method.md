---
title: ISymUnmanagedWriter::SetMethodSourceRange (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d057201c7d7bec3070027bb1d9de62735d583cf6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429007"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="323d0-102">ISymUnmanagedWriter::SetMethodSourceRange (Método)</span><span class="sxs-lookup"><span data-stu-id="323d0-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="323d0-103">Especifica true inicial y final de un método dentro de un archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="323d0-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="323d0-104">Utilice este método para especificar el alcance de un método, independientemente de los puntos de secuencia que existan dentro del método.</span><span class="sxs-lookup"><span data-stu-id="323d0-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="323d0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="323d0-105">Syntax</span></span>  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="323d0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="323d0-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="323d0-107">[in] Un puntero al documento que contiene la posición inicial.</span><span class="sxs-lookup"><span data-stu-id="323d0-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="323d0-108">[in] El número de línea inicial.</span><span class="sxs-lookup"><span data-stu-id="323d0-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="323d0-109">[in] La columna inicial.</span><span class="sxs-lookup"><span data-stu-id="323d0-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="323d0-110">[in] Un puntero al documento que contiene la posición final.</span><span class="sxs-lookup"><span data-stu-id="323d0-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="323d0-111">[in] El número de línea final.</span><span class="sxs-lookup"><span data-stu-id="323d0-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="323d0-112">[in] El número de columna final.</span><span class="sxs-lookup"><span data-stu-id="323d0-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="323d0-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="323d0-113">Return Value</span></span>  
 <span data-ttu-id="323d0-114">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="323d0-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="323d0-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="323d0-115">Requirements</span></span>  
 <span data-ttu-id="323d0-116">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="323d0-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="323d0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="323d0-117">See Also</span></span>  
 [<span data-ttu-id="323d0-118">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="323d0-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
