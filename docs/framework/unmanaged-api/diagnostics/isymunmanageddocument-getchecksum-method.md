---
title: "ISymUnmanagedDocument::GetCheckSum (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b0b2ce6facf99b44f54e8880d4436ab7fe96e50a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="74f8d-102">ISymUnmanagedDocument::GetCheckSum (Método)</span><span class="sxs-lookup"><span data-stu-id="74f8d-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="74f8d-103">Obtiene la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="74f8d-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f8d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74f8d-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74f8d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74f8d-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="74f8d-106">[in] La longitud del búfer proporcionado por el `data` parámetro</span><span class="sxs-lookup"><span data-stu-id="74f8d-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="74f8d-107">[out] El tamaño y la longitud de la suma de comprobación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="74f8d-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="74f8d-108">[out] Búfer que recibe la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="74f8d-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74f8d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="74f8d-109">Return Value</span></span>  
 <span data-ttu-id="74f8d-110">S_OK si el método tiene éxito; en caso contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="74f8d-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f8d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="74f8d-111">See Also</span></span>  
 [<span data-ttu-id="74f8d-112">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74f8d-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
