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
ms.openlocfilehash: 950fb3b9c51ae2c9470b5aadd31c877d7aa6b6f6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615064"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="905f2-102">ISymUnmanagedReader::GetDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="905f2-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="905f2-103">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="905f2-103">Finds a document.</span></span> <span data-ttu-id="905f2-104">El idioma del documento, el proveedor y el tipo son opcionales.</span><span class="sxs-lookup"><span data-stu-id="905f2-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="905f2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="905f2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="905f2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="905f2-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="905f2-107">de Dirección URL que identifica el documento.</span><span class="sxs-lookup"><span data-stu-id="905f2-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="905f2-108">de Lenguaje del documento.</span><span class="sxs-lookup"><span data-stu-id="905f2-108">[in] The document language.</span></span> <span data-ttu-id="905f2-109">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="905f2-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="905f2-110">de La identidad del proveedor para el idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="905f2-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="905f2-111">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="905f2-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="905f2-112">de Tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="905f2-112">[in] The type of the document.</span></span> <span data-ttu-id="905f2-113">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="905f2-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="905f2-114">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="905f2-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="905f2-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="905f2-115">Return Value</span></span>  
 <span data-ttu-id="905f2-116">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="905f2-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="905f2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="905f2-117">Requirements</span></span>  
 <span data-ttu-id="905f2-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="905f2-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="905f2-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="905f2-119">See also</span></span>

- [<span data-ttu-id="905f2-120">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="905f2-120">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
