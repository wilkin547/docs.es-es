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
ms.openlocfilehash: d37de6dee14ad2c24c21a2d1a97d112fd0b9f3d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706409"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="6a563-102">ISymUnmanagedVariable::GetAddressField1 (Método)</span><span class="sxs-lookup"><span data-stu-id="6a563-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="6a563-103">Obtiene el primer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="6a563-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="6a563-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="6a563-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a563-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a563-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a563-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a563-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6a563-107">[out] Un puntero a un `ULONG32` que recibe el primer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="6a563-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a563-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6a563-108">Return Value</span></span>  
 <span data-ttu-id="6a563-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="6a563-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a563-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a563-110">Requirements</span></span>  
 <span data-ttu-id="6a563-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6a563-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a563-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a563-112">See also</span></span>
- [<span data-ttu-id="6a563-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a563-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="6a563-114">GetAddressField2 (método)</span><span class="sxs-lookup"><span data-stu-id="6a563-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="6a563-115">GetAddressField3 (método)</span><span class="sxs-lookup"><span data-stu-id="6a563-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="6a563-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="6a563-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
