---
title: "ISymUnmanagedReader::GetMethodByVersion (Método)"
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
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 810cc5cda9de7c61c1b23d1574ceff19bfec3bc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="46b13-102">ISymUnmanagedReader::GetMethodByVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="46b13-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="46b13-103">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de editar y copiar.</span><span class="sxs-lookup"><span data-stu-id="46b13-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="46b13-104">Números de versión empiezan en 1 y se incrementan cada vez que se cambia el método como resultado de una operación de editar y copiar.</span><span class="sxs-lookup"><span data-stu-id="46b13-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b13-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46b13-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46b13-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46b13-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="46b13-107">[in] El token del método.</span><span class="sxs-lookup"><span data-stu-id="46b13-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="46b13-108">[in] La versión del método.</span><span class="sxs-lookup"><span data-stu-id="46b13-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="46b13-109">[out] Un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="46b13-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46b13-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="46b13-110">Return Value</span></span>  
 <span data-ttu-id="46b13-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="46b13-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46b13-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46b13-112">Requirements</span></span>  
 <span data-ttu-id="46b13-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="46b13-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b13-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="46b13-114">See Also</span></span>  
 [<span data-ttu-id="46b13-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46b13-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
