---
title: "ISymUnmanagedVariable::GetAddressField3 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAddressField3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1dfeb3f02b0c767dfc200a625fa4c617692dc11f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="52b7d-102">ISymUnmanagedVariable::GetAddressField3 (Método)</span><span class="sxs-lookup"><span data-stu-id="52b7d-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="52b7d-103">Obtiene el tercer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="52b7d-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="52b7d-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="52b7d-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52b7d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52b7d-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52b7d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52b7d-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="52b7d-107">[out] Un puntero a un `ULONG32` que recibe el tercer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="52b7d-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52b7d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52b7d-108">Return Value</span></span>  
 <span data-ttu-id="52b7d-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="52b7d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52b7d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52b7d-110">Requirements</span></span>  
 <span data-ttu-id="52b7d-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="52b7d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b7d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="52b7d-112">See Also</span></span>  
 [<span data-ttu-id="52b7d-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52b7d-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="52b7d-114">GetAddressField1 (método)</span><span class="sxs-lookup"><span data-stu-id="52b7d-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="52b7d-115">GetAddressField2 (método)</span><span class="sxs-lookup"><span data-stu-id="52b7d-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="52b7d-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="52b7d-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
