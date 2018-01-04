---
title: "ISymUnmanagedWriter::DefineDocument (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 522cc3a63101ec7ebe47e8e23878b9d1b12bca1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="90077-102">ISymUnmanagedWriter::DefineDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="90077-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="90077-103">Define un documento de origen.</span><span class="sxs-lookup"><span data-stu-id="90077-103">Defines a source document.</span></span> <span data-ttu-id="90077-104">GUID se proporcionan para lenguajes, proveedores y tipos de documentos.</span><span class="sxs-lookup"><span data-stu-id="90077-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90077-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90077-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90077-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90077-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="90077-107">[in] Un puntero a un `WCHAR` que define el localizador uniforme de recursos (URL) que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="90077-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="90077-108">[in] Un puntero a un GUID que define el lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="90077-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="90077-109">[in] Un puntero a un GUID que define la identidad del proveedor del lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="90077-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="90077-110">[in] Un puntero a un GUID que define el tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="90077-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="90077-111">[out] Un puntero para el valor devuelto [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="90077-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90077-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="90077-112">Return Value</span></span>  
 <span data-ttu-id="90077-113">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="90077-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90077-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90077-114">Requirements</span></span>  
 <span data-ttu-id="90077-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="90077-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90077-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="90077-116">See Also</span></span>  
 [<span data-ttu-id="90077-117">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="90077-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
