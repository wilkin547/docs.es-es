---
title: ISymUnmanagedReader::GetDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f20f7aabc05bb9e15b040d968c08d10444efd8fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485816"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="20209-102">ISymUnmanagedReader::GetDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="20209-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="20209-103">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="20209-103">Finds a document.</span></span> <span data-ttu-id="20209-104">El lenguaje del documento, el proveedor y el tipo son opcionales.</span><span class="sxs-lookup"><span data-stu-id="20209-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20209-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20209-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20209-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20209-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="20209-107">[in] La dirección URL que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="20209-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="20209-108">[in] El lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="20209-108">[in] The document language.</span></span> <span data-ttu-id="20209-109">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="20209-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="20209-110">[in] La identidad del proveedor para el lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="20209-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="20209-111">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="20209-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="20209-112">[in] El tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="20209-112">[in] The type of the document.</span></span> <span data-ttu-id="20209-113">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="20209-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="20209-114">[out] Un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="20209-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20209-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20209-115">Return Value</span></span>  
 <span data-ttu-id="20209-116">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="20209-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20209-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20209-117">Requirements</span></span>  
 <span data-ttu-id="20209-118">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="20209-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20209-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="20209-119">See also</span></span>
- [<span data-ttu-id="20209-120">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20209-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
