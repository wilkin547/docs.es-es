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
ms.openlocfilehash: 1fcb885b6e19457065c2ca9971f068b42f97147d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448344"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="58813-102">ISymUnmanagedReader::GetDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="58813-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="58813-103">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="58813-103">Finds a document.</span></span> <span data-ttu-id="58813-104">El idioma del documento, el proveedor y el tipo son opcionales.</span><span class="sxs-lookup"><span data-stu-id="58813-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58813-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58813-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58813-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58813-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="58813-107">de Dirección URL que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="58813-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="58813-108">de Lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="58813-108">[in] The document language.</span></span> <span data-ttu-id="58813-109">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="58813-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="58813-110">de La identidad del proveedor para el idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="58813-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="58813-111">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="58813-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="58813-112">de Tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="58813-112">[in] The type of the document.</span></span> <span data-ttu-id="58813-113">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="58813-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="58813-114">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="58813-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58813-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58813-115">Return Value</span></span>  
 <span data-ttu-id="58813-116">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="58813-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58813-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58813-117">Requirements</span></span>  
 <span data-ttu-id="58813-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="58813-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58813-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="58813-119">See also</span></span>

- [<span data-ttu-id="58813-120">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58813-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
