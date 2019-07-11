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
ms.openlocfilehash: 32b7505a9e512f3c3e3e7a9fcbff40276e98ecf4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759351"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="2685d-102">ISymUnmanagedReader::GetDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="2685d-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="2685d-103">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="2685d-103">Finds a document.</span></span> <span data-ttu-id="2685d-104">El lenguaje del documento, el proveedor y el tipo son opcionales.</span><span class="sxs-lookup"><span data-stu-id="2685d-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2685d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2685d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2685d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2685d-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="2685d-107">[in] La dirección URL que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="2685d-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="2685d-108">[in] El lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="2685d-108">[in] The document language.</span></span> <span data-ttu-id="2685d-109">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="2685d-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="2685d-110">[in] La identidad del proveedor para el lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="2685d-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="2685d-111">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="2685d-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="2685d-112">[in] El tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="2685d-112">[in] The type of the document.</span></span> <span data-ttu-id="2685d-113">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="2685d-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2685d-114">[out] Un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="2685d-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2685d-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2685d-115">Return Value</span></span>  
 <span data-ttu-id="2685d-116">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2685d-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2685d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2685d-117">Requirements</span></span>  
 <span data-ttu-id="2685d-118">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2685d-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2685d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2685d-119">See also</span></span>

- [<span data-ttu-id="2685d-120">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2685d-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
