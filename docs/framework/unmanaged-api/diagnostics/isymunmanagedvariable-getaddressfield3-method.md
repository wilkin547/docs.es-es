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
ms.workload: dotnet
ms.openlocfilehash: eb7bfa17729321df21dfc69c79d65baf2a92a44a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="a1bcf-102">ISymUnmanagedVariable::GetAddressField3 (Método)</span><span class="sxs-lookup"><span data-stu-id="a1bcf-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="a1bcf-103">Obtiene el tercer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="a1bcf-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="a1bcf-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="a1bcf-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bcf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1bcf-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1bcf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1bcf-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a1bcf-107">[out] Un puntero a un `ULONG32` que recibe el tercer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="a1bcf-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1bcf-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a1bcf-108">Return Value</span></span>  
 <span data-ttu-id="a1bcf-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a1bcf-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1bcf-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1bcf-110">Requirements</span></span>  
 <span data-ttu-id="a1bcf-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a1bcf-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bcf-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1bcf-112">See Also</span></span>  
 [<span data-ttu-id="a1bcf-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1bcf-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="a1bcf-114">GetAddressField1 (método)</span><span class="sxs-lookup"><span data-stu-id="a1bcf-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="a1bcf-115">GetAddressField2 (método)</span><span class="sxs-lookup"><span data-stu-id="a1bcf-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="a1bcf-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="a1bcf-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
