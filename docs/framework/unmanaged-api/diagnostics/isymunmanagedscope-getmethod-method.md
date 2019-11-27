---
title: ISymUnmanagedScope::GetMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
ms.openlocfilehash: 348a8cebe0fd746f3ae490484ffcca2fcb77684b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446317"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="726f4-102">ISymUnmanagedScope::GetMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="726f4-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="726f4-103">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="726f4-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="726f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="726f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="726f4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="726f4-106">enuncia Puntero a la interfaz [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="726f4-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="726f4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="726f4-107">Return Value</span></span>  
 <span data-ttu-id="726f4-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="726f4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="726f4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="726f4-109">Requirements</span></span>  
 <span data-ttu-id="726f4-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="726f4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726f4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="726f4-111">See also</span></span>

- [<span data-ttu-id="726f4-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="726f4-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
