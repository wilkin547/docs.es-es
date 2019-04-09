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
ms.openlocfilehash: 67634024b04e82aa3a3c0b96dc260114c4c16371
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179704"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="a0ac2-102">ISymUnmanagedVariable::GetAddressField1 (Método)</span><span class="sxs-lookup"><span data-stu-id="a0ac2-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="a0ac2-103">Obtiene el primer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="a0ac2-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="a0ac2-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="a0ac2-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ac2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0ac2-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0ac2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0ac2-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a0ac2-107">[out] Un puntero a un `ULONG32` que recibe el primer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="a0ac2-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0ac2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a0ac2-108">Return Value</span></span>  
 <span data-ttu-id="a0ac2-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a0ac2-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0ac2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0ac2-110">Requirements</span></span>  
 <span data-ttu-id="a0ac2-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a0ac2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ac2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0ac2-112">See also</span></span>

- [<span data-ttu-id="a0ac2-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0ac2-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="a0ac2-114">Método GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="a0ac2-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="a0ac2-115">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="a0ac2-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="a0ac2-116">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="a0ac2-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
