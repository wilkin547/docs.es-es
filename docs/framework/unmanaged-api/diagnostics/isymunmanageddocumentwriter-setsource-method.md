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
ms.openlocfilehash: 64982308c6eb7e9df4b94b4e123857c65939f044
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142485"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="469f0-102">ISymUnmanagedDocumentWriter::SetSource (Método)</span><span class="sxs-lookup"><span data-stu-id="469f0-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="469f0-103">Conjuntos de código fuente incrustan para un documento que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="469f0-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="469f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="469f0-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="469f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="469f0-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="469f0-106">[in] Un `ULONG32` que contiene el tamaño de la `source` búfer.</span><span class="sxs-lookup"><span data-stu-id="469f0-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="469f0-107">[in] El búfer que almacena el código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="469f0-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="469f0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="469f0-108">Return Value</span></span>  
 <span data-ttu-id="469f0-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="469f0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="469f0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="469f0-110">Requirements</span></span>  
 <span data-ttu-id="469f0-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="469f0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="469f0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="469f0-112">See also</span></span>

- [<span data-ttu-id="469f0-113">ISymUnmanagedDocumentWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="469f0-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
