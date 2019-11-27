---
title: ISymUnmanagedConstant::GetValue (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
ms.openlocfilehash: 00be35e9a15349b8bca5f76b948b8477dd240888
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449239"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="cacd9-102">ISymUnmanagedConstant::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="cacd9-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="cacd9-103">Obtiene el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="cacd9-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cacd9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cacd9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cacd9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cacd9-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="cacd9-106">enuncia Puntero a una variable que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="cacd9-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cacd9-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cacd9-107">Return Value</span></span>  
 <span data-ttu-id="cacd9-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="cacd9-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cacd9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cacd9-109">Requirements</span></span>  
 <span data-ttu-id="cacd9-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cacd9-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cacd9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="cacd9-111">See also</span></span>

- [<span data-ttu-id="cacd9-112">ISymUnmanagedConstant (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cacd9-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="cacd9-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="cacd9-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="cacd9-114">GetSignature (método)</span><span class="sxs-lookup"><span data-stu-id="cacd9-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
