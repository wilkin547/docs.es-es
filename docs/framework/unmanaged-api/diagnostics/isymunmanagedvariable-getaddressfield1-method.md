---
title: ISymUnmanagedVariable::GetAddressField1 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 796a71ac941497801c749295fb2f6bb201547bd7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478315"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="169b7-102">ISymUnmanagedVariable::GetAddressField1 (Método)</span><span class="sxs-lookup"><span data-stu-id="169b7-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="169b7-103">Obtiene el primer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="169b7-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="169b7-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="169b7-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="169b7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="169b7-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="169b7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="169b7-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="169b7-107">[out] Un puntero a un `ULONG32` que recibe el primer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="169b7-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="169b7-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="169b7-108">Return Value</span></span>  
 <span data-ttu-id="169b7-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="169b7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="169b7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="169b7-110">Requirements</span></span>  
 <span data-ttu-id="169b7-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="169b7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169b7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="169b7-112">See also</span></span>
- [<span data-ttu-id="169b7-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="169b7-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="169b7-114">GetAddressField2 (método)</span><span class="sxs-lookup"><span data-stu-id="169b7-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="169b7-115">GetAddressField3 (método)</span><span class="sxs-lookup"><span data-stu-id="169b7-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="169b7-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="169b7-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
