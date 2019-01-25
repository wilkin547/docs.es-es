---
title: ISymUnmanagedWriter::DefineDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d1c214918b4a41ac989a3804c9146c4a54c5909f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738214"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="54903-102">ISymUnmanagedWriter::DefineDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="54903-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="54903-103">Define un documento de origen.</span><span class="sxs-lookup"><span data-stu-id="54903-103">Defines a source document.</span></span> <span data-ttu-id="54903-104">Se proporcionan los GUID para lenguajes conocidos, proveedores y tipos de documento.</span><span class="sxs-lookup"><span data-stu-id="54903-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54903-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54903-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54903-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54903-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="54903-107">[in] Un puntero a un `WCHAR` que define el localizador uniforme de recursos (URL) que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="54903-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="54903-108">[in] Un puntero a un GUID que define el lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="54903-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="54903-109">[in] Un puntero a un GUID que define la identidad del proveedor para el lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="54903-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="54903-110">[in] Un puntero a un GUID que define el tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="54903-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="54903-111">[out] Un puntero a la devuelta [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="54903-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54903-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="54903-112">Return Value</span></span>  
 <span data-ttu-id="54903-113">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="54903-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54903-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54903-114">Requirements</span></span>  
 <span data-ttu-id="54903-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="54903-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54903-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="54903-116">See also</span></span>
- [<span data-ttu-id="54903-117">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54903-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
