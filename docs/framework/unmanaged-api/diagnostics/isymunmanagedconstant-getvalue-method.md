---
description: 'Más información sobre: ISymUnmanagedConstant:: GetValue (método)'
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
ms.openlocfilehash: 05818028deb804bf2a2426285b5185b01776199d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689695"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="f1519-103">ISymUnmanagedConstant::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="f1519-103">ISymUnmanagedConstant::GetValue Method</span></span>

<span data-ttu-id="f1519-104"> Obtiene el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="f1519-104">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1519-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1519-105">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1519-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1519-106">Parameters</span></span>  

 `pValue`  
 <span data-ttu-id="f1519-107">enuncia Puntero a una variable que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="f1519-107">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1519-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f1519-108">Return Value</span></span>  

 <span data-ttu-id="f1519-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f1519-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1519-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1519-110">Requirements</span></span>  

 <span data-ttu-id="f1519-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f1519-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1519-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1519-112">See also</span></span>

- [<span data-ttu-id="f1519-113">ISymUnmanagedConstant (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1519-113">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="f1519-114">Método GetName</span><span class="sxs-lookup"><span data-stu-id="f1519-114">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="f1519-115">GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="f1519-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
