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
ms.openlocfilehash: 68f2cc471a33d2c0ea92ceab59d5ba9ecb86e7f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509593"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="0b277-102">ISymUnmanagedReader::GetDocuments (Método)</span><span class="sxs-lookup"><span data-stu-id="0b277-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="0b277-103">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="0b277-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b277-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b277-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b277-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b277-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="0b277-106">[in] Tamaño de la matriz `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="0b277-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="0b277-107">[out] Un puntero a una variable que recibe la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0b277-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="0b277-108">[out] Un puntero a una variable que recibe la matriz de documentos.</span><span class="sxs-lookup"><span data-stu-id="0b277-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b277-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0b277-109">Return Value</span></span>  
 <span data-ttu-id="0b277-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0b277-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b277-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b277-111">Requirements</span></span>  
 <span data-ttu-id="0b277-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0b277-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b277-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b277-113">See also</span></span>
- [<span data-ttu-id="0b277-114">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b277-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
