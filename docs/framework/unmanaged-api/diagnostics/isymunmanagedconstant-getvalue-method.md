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
ms.openlocfilehash: 8e20d2e0f3d5cb6dc7444c8e78665b6c8b82d2de
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441479"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="f7865-102">ISymUnmanagedConstant::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="f7865-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="f7865-103"> Obtiene el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="f7865-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7865-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7865-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7865-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7865-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="f7865-106">enuncia Puntero a una variable que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="f7865-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7865-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f7865-107">Return Value</span></span>  
 <span data-ttu-id="f7865-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f7865-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7865-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7865-109">Requirements</span></span>  
 <span data-ttu-id="f7865-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f7865-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7865-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="f7865-111">See also</span></span>

- [<span data-ttu-id="f7865-112">ISymUnmanagedConstant (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7865-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="f7865-113">Método GetName</span><span class="sxs-lookup"><span data-stu-id="f7865-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="f7865-114">GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="f7865-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
