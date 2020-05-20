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
ms.openlocfilehash: b8a3a74888a3caae03da6f88a003bd277939ae59
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615051"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="0a5c2-102">ISymUnmanagedReader::GetDocuments (Método)</span><span class="sxs-lookup"><span data-stu-id="0a5c2-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="0a5c2-103">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="0a5c2-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a5c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a5c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a5c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a5c2-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="0a5c2-106">[in] Tamaño de la matriz `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="0a5c2-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="0a5c2-107">enuncia Puntero a una variable que recibe la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0a5c2-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="0a5c2-108">enuncia Puntero a una variable que recibe la matriz del documento.</span><span class="sxs-lookup"><span data-stu-id="0a5c2-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a5c2-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0a5c2-109">Return Value</span></span>  
 <span data-ttu-id="0a5c2-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0a5c2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a5c2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a5c2-111">Requirements</span></span>  
 <span data-ttu-id="0a5c2-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0a5c2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a5c2-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0a5c2-113">See also</span></span>

- [<span data-ttu-id="0a5c2-114">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a5c2-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
