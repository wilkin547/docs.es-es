---
title: "ISymUnmanagedMethod::GetToken (Método)"
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
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bfdc070c21c7929166bfa957c0e0dd63da80f761
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="40550-102">ISymUnmanagedMethod::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="40550-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="40550-103">Devuelve el token de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="40550-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40550-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40550-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40550-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40550-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="40550-106">[out] Un puntero a un `mdMethodDef` que recibe el tamaño, en caracteres, del búfer necesario para contener los metadatos.</span><span class="sxs-lookup"><span data-stu-id="40550-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40550-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="40550-107">Return Value</span></span>  
 <span data-ttu-id="40550-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="40550-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40550-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40550-109">Requirements</span></span>  
 <span data-ttu-id="40550-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="40550-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40550-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="40550-111">See Also</span></span>  
 [<span data-ttu-id="40550-112">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40550-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
