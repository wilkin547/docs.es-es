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
ms.openlocfilehash: 7a1c795f4a162699078e91bcaa274253169234e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732845"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="d29a2-102">ISymUnmanagedConstant::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="d29a2-102">ISymUnmanagedConstant::GetValue Method</span></span>

<span data-ttu-id="d29a2-103"> Obtiene el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="d29a2-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d29a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d29a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d29a2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d29a2-105">Parameters</span></span>  

 `pValue`  
 <span data-ttu-id="d29a2-106">enuncia Puntero a una variable que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="d29a2-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d29a2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d29a2-107">Return Value</span></span>  

 <span data-ttu-id="d29a2-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d29a2-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d29a2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d29a2-109">Requirements</span></span>  

 <span data-ttu-id="d29a2-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d29a2-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d29a2-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d29a2-111">See also</span></span>

- [<span data-ttu-id="d29a2-112">ISymUnmanagedConstant (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d29a2-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="d29a2-113">GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="d29a2-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="d29a2-114">GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="d29a2-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
