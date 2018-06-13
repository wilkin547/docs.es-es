---
title: ISymUnmanagedVariable::GetAddressKind (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 18e83582a73ba3b2eb2538bcdf60984c46131768
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426960"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="41c9d-102">ISymUnmanagedVariable::GetAddressKind (Método)</span><span class="sxs-lookup"><span data-stu-id="41c9d-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="41c9d-103">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="41c9d-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41c9d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41c9d-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41c9d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41c9d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="41c9d-106">[out] Un puntero a un `ULONG32` que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="41c9d-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="41c9d-107">Los valores posibles se definen en el [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="41c9d-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41c9d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="41c9d-108">Return Value</span></span>  
 <span data-ttu-id="41c9d-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="41c9d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41c9d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41c9d-110">Requirements</span></span>  
 <span data-ttu-id="41c9d-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="41c9d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c9d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="41c9d-112">See Also</span></span>  
 [<span data-ttu-id="41c9d-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41c9d-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
