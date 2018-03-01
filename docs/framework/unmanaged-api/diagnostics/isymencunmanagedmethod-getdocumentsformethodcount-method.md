---
title: "ISymENCUnmanagedMethod::GetDocumentsForMethodCount (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 804c760c22860aa3f9ded6c8a8fa9ad9b011e9a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="7e191-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount (Método)</span><span class="sxs-lookup"><span data-stu-id="7e191-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="7e191-103">Obtiene el número de documentos que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="7e191-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e191-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e191-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e191-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e191-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7e191-106">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los documentos.</span><span class="sxs-lookup"><span data-stu-id="7e191-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e191-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7e191-107">Return Value</span></span>  
 <span data-ttu-id="7e191-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7e191-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e191-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e191-109">Requirements</span></span>  
 <span data-ttu-id="7e191-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7e191-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e191-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e191-111">See Also</span></span>  
 [<span data-ttu-id="7e191-112">ISymENCUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e191-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
