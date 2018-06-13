---
title: ISymUnmanagedVariable::GetAddressField3 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd474c7f149b8eff542b674c2ba6527b6a0cbcb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427003"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="874f3-102">ISymUnmanagedVariable::GetAddressField3 (Método)</span><span class="sxs-lookup"><span data-stu-id="874f3-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="874f3-103">Obtiene el tercer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="874f3-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="874f3-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="874f3-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="874f3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="874f3-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="874f3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="874f3-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="874f3-107">[out] Un puntero a un `ULONG32` que recibe el tercer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="874f3-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="874f3-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="874f3-108">Return Value</span></span>  
 <span data-ttu-id="874f3-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="874f3-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="874f3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="874f3-110">Requirements</span></span>  
 <span data-ttu-id="874f3-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="874f3-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874f3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="874f3-112">See Also</span></span>  
 [<span data-ttu-id="874f3-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="874f3-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="874f3-114">GetAddressField1 (método)</span><span class="sxs-lookup"><span data-stu-id="874f3-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="874f3-115">GetAddressField2 (método)</span><span class="sxs-lookup"><span data-stu-id="874f3-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="874f3-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="874f3-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
