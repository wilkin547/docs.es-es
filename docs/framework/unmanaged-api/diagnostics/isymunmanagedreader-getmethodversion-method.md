---
title: "ISymUnmanagedReader::GetMethodVersion (Método)"
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
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 713b8a89c9519abe407ac1d68adb2552cd012b1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="b2b51-102">ISymUnmanagedReader::GetMethodVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="b2b51-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="b2b51-103">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="b2b51-103">Gets the method version.</span></span> <span data-ttu-id="b2b51-104">La versión del método comienza en 1 y se incrementa cada vez que se vuelve a compilar el método.</span><span class="sxs-lookup"><span data-stu-id="b2b51-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="b2b51-105">Recompilación puede realizarse sin cambios en el método.</span><span class="sxs-lookup"><span data-stu-id="b2b51-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b51-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2b51-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2b51-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2b51-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="b2b51-108">[in] El método para el que se va a obtener la versión.</span><span class="sxs-lookup"><span data-stu-id="b2b51-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="b2b51-109">[out] Un puntero a una variable que recibe la versión del método.</span><span class="sxs-lookup"><span data-stu-id="b2b51-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2b51-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2b51-110">Return Value</span></span>  
 <span data-ttu-id="b2b51-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b2b51-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2b51-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2b51-112">Requirements</span></span>  
 <span data-ttu-id="b2b51-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b2b51-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b51-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2b51-114">See Also</span></span>  
 [<span data-ttu-id="b2b51-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2b51-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
