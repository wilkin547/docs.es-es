---
title: ISymUnmanagedDocument::GetCheckSum (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a60bf279c143559e7410d8dfd8213d3da1d05a6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127567"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="025ea-102">ISymUnmanagedDocument::GetCheckSum (Método)</span><span class="sxs-lookup"><span data-stu-id="025ea-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="025ea-103">Obtiene la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="025ea-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="025ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="025ea-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="025ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="025ea-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="025ea-106">[in] La longitud del búfer proporcionado por el `data` parámetro</span><span class="sxs-lookup"><span data-stu-id="025ea-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="025ea-107">[out] El tamaño y la longitud de la suma de comprobación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="025ea-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="025ea-108">[out] Búfer que recibe la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="025ea-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="025ea-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="025ea-109">Return Value</span></span>  
 <span data-ttu-id="025ea-110">S_OK si el método se realiza correctamente; en caso contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="025ea-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="025ea-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="025ea-111">See also</span></span>

- [<span data-ttu-id="025ea-112">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="025ea-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
