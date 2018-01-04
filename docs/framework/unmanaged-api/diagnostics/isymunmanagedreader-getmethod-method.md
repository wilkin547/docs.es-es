---
title: "ISymUnmanagedReader::GetMethod (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7af3f56bc258ba48abba5cba4230de3ca6904ec0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="8e625-102">ISymUnmanagedReader::GetMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="8e625-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="8e625-103">Obtiene un método del lector de símbolos, dado un token de método.</span><span class="sxs-lookup"><span data-stu-id="8e625-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e625-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e625-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e625-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e625-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="8e625-106">[in] El token del método.</span><span class="sxs-lookup"><span data-stu-id="8e625-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="8e625-107">[out] Un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="8e625-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e625-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e625-108">Return Value</span></span>  
 <span data-ttu-id="8e625-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8e625-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e625-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e625-110">Requirements</span></span>  
 <span data-ttu-id="8e625-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8e625-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e625-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e625-112">See Also</span></span>  
 [<span data-ttu-id="8e625-113">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e625-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
