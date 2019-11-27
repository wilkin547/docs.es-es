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
ms.openlocfilehash: c26c0a5f8c597613266e2e6d1998edfca8f17b82
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448326"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="666e2-102">ISymUnmanagedReader::GetDocuments (Método)</span><span class="sxs-lookup"><span data-stu-id="666e2-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="666e2-103">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="666e2-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="666e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="666e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="666e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="666e2-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="666e2-106">[in] Tamaño de la matriz `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="666e2-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="666e2-107">enuncia Puntero a una variable que recibe la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="666e2-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="666e2-108">enuncia Puntero a una variable que recibe la matriz del documento.</span><span class="sxs-lookup"><span data-stu-id="666e2-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="666e2-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="666e2-109">Return Value</span></span>  
 <span data-ttu-id="666e2-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="666e2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="666e2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="666e2-111">Requirements</span></span>  
 <span data-ttu-id="666e2-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="666e2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666e2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="666e2-113">See also</span></span>

- [<span data-ttu-id="666e2-114">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="666e2-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
