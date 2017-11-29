---
title: "ISymUnmanagedDocumentWriter::SetSource (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocumentWriter.SetSource
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 74b917ff4c2853eb31625af2ab1d2c64ced613e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="cae30-102">ISymUnmanagedDocumentWriter::SetSource (Método)</span><span class="sxs-lookup"><span data-stu-id="cae30-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="cae30-103">Conjuntos de código fuente incrustan para un documento que se está escribiendo.</span><span class="sxs-lookup"><span data-stu-id="cae30-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cae30-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cae30-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cae30-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="cae30-106">[in] A `ULONG32` que contiene el tamaño de la `source` búfer.</span><span class="sxs-lookup"><span data-stu-id="cae30-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="cae30-107">[in] El búfer que almacena el código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="cae30-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cae30-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cae30-108">Return Value</span></span>  
 <span data-ttu-id="cae30-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="cae30-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cae30-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cae30-110">Requirements</span></span>  
 <span data-ttu-id="cae30-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cae30-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae30-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cae30-112">See Also</span></span>  
 [<span data-ttu-id="cae30-113">ISymUnmanagedDocumentWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cae30-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
