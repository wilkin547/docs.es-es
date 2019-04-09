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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092947"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="e4b72-102">ISymUnmanagedVariable::GetAddressKind (Método)</span><span class="sxs-lookup"><span data-stu-id="e4b72-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="e4b72-103">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="e4b72-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4b72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4b72-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4b72-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4b72-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e4b72-106">[out] Un puntero a un `ULONG32` que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="e4b72-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="e4b72-107">Los valores posibles se definen en el [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="e4b72-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4b72-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e4b72-108">Return Value</span></span>  
 <span data-ttu-id="e4b72-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e4b72-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4b72-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4b72-110">Requirements</span></span>  
 <span data-ttu-id="e4b72-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e4b72-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b72-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4b72-112">See also</span></span>

- [<span data-ttu-id="e4b72-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4b72-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
