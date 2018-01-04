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
ms.workload: dotnet
ms.openlocfilehash: 287eba260ca20bae9da94ed2d00dcf1661fe14cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="8d109-102">ISymUnmanagedDocumentWriter::SetSource (Método)</span><span class="sxs-lookup"><span data-stu-id="8d109-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="8d109-103">Conjuntos de código fuente incrustan para un documento que se está escribiendo.</span><span class="sxs-lookup"><span data-stu-id="8d109-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d109-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d109-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d109-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d109-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="8d109-106">[in] A `ULONG32` que contiene el tamaño de la `source` búfer.</span><span class="sxs-lookup"><span data-stu-id="8d109-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="8d109-107">[in] El búfer que almacena el código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="8d109-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d109-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8d109-108">Return Value</span></span>  
 <span data-ttu-id="8d109-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8d109-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d109-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d109-110">Requirements</span></span>  
 <span data-ttu-id="8d109-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8d109-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d109-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d109-112">See Also</span></span>  
 [<span data-ttu-id="8d109-113">ISymUnmanagedDocumentWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d109-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
