---
title: "ISymUnmanagedReader::GetUserEntryPoint (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetUserEntryPoint
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 328f44e797a49a899545fa43d940a3b0399ee8c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="df321-102">ISymUnmanagedReader::GetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="df321-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="df321-103">Devuelve el método que se especificó como el punto de entrada de usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="df321-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="df321-104">Por ejemplo, este método podría ser el método del usuario principal en lugar de código auxiliar generado por el compilador antes del método principal.</span><span class="sxs-lookup"><span data-stu-id="df321-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df321-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df321-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df321-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df321-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="df321-107">[out] Un puntero a una variable que recibe el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="df321-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df321-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df321-108">Return Value</span></span>  
 <span data-ttu-id="df321-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="df321-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df321-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df321-110">Requirements</span></span>  
 <span data-ttu-id="df321-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df321-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df321-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="df321-112">See Also</span></span>  
 [<span data-ttu-id="df321-113">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="df321-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
