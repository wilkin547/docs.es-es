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
ms.openlocfilehash: 4604d78f66b872a30457c51bf65890caf613c4fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707638"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="562cd-102">ISymUnmanagedReader::GetDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="562cd-102">ISymUnmanagedReader::GetDocument Method</span></span>

<span data-ttu-id="562cd-103">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="562cd-103">Finds a document.</span></span> <span data-ttu-id="562cd-104">El idioma del documento, el proveedor y el tipo son opcionales.</span><span class="sxs-lookup"><span data-stu-id="562cd-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="562cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="562cd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="562cd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="562cd-106">Parameters</span></span>  

 `url`  
 <span data-ttu-id="562cd-107">de Dirección URL que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="562cd-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="562cd-108">de Lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="562cd-108">[in] The document language.</span></span> <span data-ttu-id="562cd-109">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="562cd-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="562cd-110">de La identidad del proveedor para el idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="562cd-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="562cd-111">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="562cd-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="562cd-112">de Tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="562cd-112">[in] The type of the document.</span></span> <span data-ttu-id="562cd-113">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="562cd-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="562cd-114">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="562cd-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="562cd-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="562cd-115">Return Value</span></span>  

 <span data-ttu-id="562cd-116">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="562cd-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="562cd-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="562cd-117">Requirements</span></span>  

 <span data-ttu-id="562cd-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="562cd-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="562cd-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="562cd-119">See also</span></span>

- [<span data-ttu-id="562cd-120">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="562cd-120">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
