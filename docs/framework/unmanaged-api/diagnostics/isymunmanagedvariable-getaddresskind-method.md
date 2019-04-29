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
ms.openlocfilehash: eae5b21af3bcdca911ec13067a61bb957d4ae6ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797584"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="be5a8-102">ISymUnmanagedVariable::GetAddressKind (Método)</span><span class="sxs-lookup"><span data-stu-id="be5a8-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="be5a8-103">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="be5a8-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be5a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be5a8-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be5a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be5a8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="be5a8-106">[out] Un puntero a un `ULONG32` que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="be5a8-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="be5a8-107">Los valores posibles se definen en el [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="be5a8-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be5a8-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="be5a8-108">Return Value</span></span>  
 <span data-ttu-id="be5a8-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="be5a8-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be5a8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be5a8-110">Requirements</span></span>  
 <span data-ttu-id="be5a8-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="be5a8-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be5a8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="be5a8-112">See also</span></span>

- [<span data-ttu-id="be5a8-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="be5a8-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
