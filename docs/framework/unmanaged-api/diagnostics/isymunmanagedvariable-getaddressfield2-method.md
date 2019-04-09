---
title: ISymUnmanagedVariable::GetAddressField2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2030a0da7a84695750d1dd9781adca9cd66f22ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137701"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="c098c-102">ISymUnmanagedVariable::GetAddressField2 (Método)</span><span class="sxs-lookup"><span data-stu-id="c098c-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="c098c-103">Obtiene el segundo campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="c098c-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="c098c-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="c098c-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c098c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c098c-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c098c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c098c-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c098c-107">[out] Un puntero a un `ULONG32` que recibe el segundo campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="c098c-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c098c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c098c-108">Return Value</span></span>  
 <span data-ttu-id="c098c-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c098c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c098c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c098c-110">Requirements</span></span>  
 <span data-ttu-id="c098c-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c098c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c098c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c098c-112">See also</span></span>

- [<span data-ttu-id="c098c-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c098c-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="c098c-114">Método GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="c098c-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="c098c-115">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="c098c-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="c098c-116">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="c098c-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
