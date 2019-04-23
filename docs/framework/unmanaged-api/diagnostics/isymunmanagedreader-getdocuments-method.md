---
title: ISymUnmanagedReader::GetDocuments (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efcf5b6673fbdc37fad99d082f91ab3077abbea9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130603"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="c3b53-102">ISymUnmanagedReader::GetDocuments (Método)</span><span class="sxs-lookup"><span data-stu-id="c3b53-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="c3b53-103">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="c3b53-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3b53-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b53-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3b53-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="c3b53-106">[in] Tamaño de la matriz `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="c3b53-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="c3b53-107">[out] Un puntero a una variable que recibe la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c3b53-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="c3b53-108">[out] Un puntero a una variable que recibe la matriz de documentos.</span><span class="sxs-lookup"><span data-stu-id="c3b53-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3b53-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c3b53-109">Return Value</span></span>  
 <span data-ttu-id="c3b53-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c3b53-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b53-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3b53-111">Requirements</span></span>  
 <span data-ttu-id="c3b53-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c3b53-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b53-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3b53-113">See also</span></span>

- [<span data-ttu-id="c3b53-114">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3b53-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
