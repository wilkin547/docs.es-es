---
title: ISymUnmanagedDocumentWriter::SetSource (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 555926e0e6a669f70bdeff484cff0eb62ae11f7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776941"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="20cf6-102">ISymUnmanagedDocumentWriter::SetSource (Método)</span><span class="sxs-lookup"><span data-stu-id="20cf6-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="20cf6-103">Conjuntos de código fuente incrustan para un documento que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="20cf6-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20cf6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20cf6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20cf6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20cf6-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="20cf6-106">[in] Un `ULONG32` que contiene el tamaño de la `source` búfer.</span><span class="sxs-lookup"><span data-stu-id="20cf6-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="20cf6-107">[in] El búfer que almacena el código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="20cf6-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20cf6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20cf6-108">Return Value</span></span>  
 <span data-ttu-id="20cf6-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="20cf6-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20cf6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20cf6-110">Requirements</span></span>  
 <span data-ttu-id="20cf6-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="20cf6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20cf6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="20cf6-112">See also</span></span>

- [<span data-ttu-id="20cf6-113">ISymUnmanagedDocumentWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20cf6-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
