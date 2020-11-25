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
ms.openlocfilehash: 6413935df86b85a959fa4f354c6233d18baf99d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727580"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="fd74e-102">ISymUnmanagedWriter::DefineDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="fd74e-102">ISymUnmanagedWriter::DefineDocument Method</span></span>

<span data-ttu-id="fd74e-103">Define un documento de origen.</span><span class="sxs-lookup"><span data-stu-id="fd74e-103">Defines a source document.</span></span> <span data-ttu-id="fd74e-104">Se proporcionan GUID para los lenguajes, proveedores y tipos de documento conocidos.</span><span class="sxs-lookup"><span data-stu-id="fd74e-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd74e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd74e-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd74e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd74e-106">Parameters</span></span>  

 `url`  
 <span data-ttu-id="fd74e-107">de Un puntero a `WCHAR` que define el localizador uniforme de recursos (URL) que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="fd74e-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="fd74e-108">de Un puntero a un GUID que define el idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="fd74e-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="fd74e-109">de Un puntero a un GUID que define la identidad del proveedor para el idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="fd74e-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="fd74e-110">de Un puntero a un GUID que define el tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="fd74e-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fd74e-111">enuncia Puntero a la interfaz [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="fd74e-111">[out] A pointer to the returned [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd74e-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd74e-112">Return Value</span></span>  

 <span data-ttu-id="fd74e-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="fd74e-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd74e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd74e-114">Requirements</span></span>  

 <span data-ttu-id="fd74e-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="fd74e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd74e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd74e-116">See also</span></span>

- [<span data-ttu-id="fd74e-117">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd74e-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
