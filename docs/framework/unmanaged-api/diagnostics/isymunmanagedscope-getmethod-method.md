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
ms.openlocfilehash: cdbffe71540b51ff539a45861546efd761761892
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615376"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="50b83-102">ISymUnmanagedScope::GetMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="50b83-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="50b83-103">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="50b83-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50b83-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50b83-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50b83-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50b83-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="50b83-106">enuncia Puntero a la interfaz [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="50b83-106">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50b83-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="50b83-107">Return Value</span></span>  
 <span data-ttu-id="50b83-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="50b83-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50b83-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50b83-109">Requirements</span></span>  
 <span data-ttu-id="50b83-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="50b83-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b83-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="50b83-111">See also</span></span>

- [<span data-ttu-id="50b83-112">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50b83-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
