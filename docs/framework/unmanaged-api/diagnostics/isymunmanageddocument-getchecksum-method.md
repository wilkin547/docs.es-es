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
ms.openlocfilehash: 660da82f1e6d6d3ea8ba084885331c895bc64542
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424731"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="64ccc-102">ISymUnmanagedDocument::GetCheckSum (Método)</span><span class="sxs-lookup"><span data-stu-id="64ccc-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="64ccc-103">Obtiene la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="64ccc-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64ccc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64ccc-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64ccc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64ccc-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="64ccc-106">[in] La longitud del búfer proporcionado por el `data` parámetro</span><span class="sxs-lookup"><span data-stu-id="64ccc-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="64ccc-107">[out] El tamaño y la longitud de la suma de comprobación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="64ccc-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="64ccc-108">[out] Búfer que recibe la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="64ccc-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64ccc-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="64ccc-109">Return Value</span></span>  
 <span data-ttu-id="64ccc-110">S_OK si el método tiene éxito; en caso contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="64ccc-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ccc-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="64ccc-111">See Also</span></span>  
 [<span data-ttu-id="64ccc-112">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64ccc-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
