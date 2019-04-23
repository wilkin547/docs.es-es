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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137701"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="4d3e0-102">ISymUnmanagedVariable::GetAddressField2 (Método)</span><span class="sxs-lookup"><span data-stu-id="4d3e0-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="4d3e0-103">Obtiene el segundo campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="4d3e0-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="4d3e0-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="4d3e0-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d3e0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d3e0-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d3e0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d3e0-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4d3e0-107">[out] Un puntero a un `ULONG32` que recibe el segundo campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="4d3e0-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d3e0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d3e0-108">Return Value</span></span>  
 <span data-ttu-id="4d3e0-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4d3e0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d3e0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d3e0-110">Requirements</span></span>  
 <span data-ttu-id="4d3e0-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4d3e0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d3e0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d3e0-112">See also</span></span>

- [<span data-ttu-id="4d3e0-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d3e0-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="4d3e0-114">GetAddressField1 (método)</span><span class="sxs-lookup"><span data-stu-id="4d3e0-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="4d3e0-115">GetAddressField3 (método)</span><span class="sxs-lookup"><span data-stu-id="4d3e0-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="4d3e0-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="4d3e0-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
