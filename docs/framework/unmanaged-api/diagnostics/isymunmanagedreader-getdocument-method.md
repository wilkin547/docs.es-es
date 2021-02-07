---
description: 'Más información acerca de: ISymUnmanagedReader:: GetDocument (método)'
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
ms.openlocfilehash: 7f2f31467cfd00de68737224a2c1af5b1e78efed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764104"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="554d2-103">ISymUnmanagedReader::GetDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="554d2-103">ISymUnmanagedReader::GetDocument Method</span></span>

<span data-ttu-id="554d2-104">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="554d2-104">Finds a document.</span></span> <span data-ttu-id="554d2-105">El idioma del documento, el proveedor y el tipo son opcionales.</span><span class="sxs-lookup"><span data-stu-id="554d2-105">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="554d2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="554d2-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="554d2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="554d2-107">Parameters</span></span>  

 `url`  
 <span data-ttu-id="554d2-108">de Dirección URL que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="554d2-108">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="554d2-109">de Lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="554d2-109">[in] The document language.</span></span> <span data-ttu-id="554d2-110">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="554d2-110">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="554d2-111">de La identidad del proveedor para el idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="554d2-111">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="554d2-112">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="554d2-112">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="554d2-113">de Tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="554d2-113">[in] The type of the document.</span></span> <span data-ttu-id="554d2-114">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="554d2-114">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="554d2-115">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="554d2-115">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="554d2-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="554d2-116">Return Value</span></span>  

 <span data-ttu-id="554d2-117">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="554d2-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="554d2-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="554d2-118">Requirements</span></span>  

 <span data-ttu-id="554d2-119">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="554d2-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="554d2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="554d2-120">See also</span></span>

- [<span data-ttu-id="554d2-121">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="554d2-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
