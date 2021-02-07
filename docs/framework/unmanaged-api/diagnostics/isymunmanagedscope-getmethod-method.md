---
description: 'Más información acerca de: ISymUnmanagedScope:: GetMethod (método)'
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
ms.openlocfilehash: 7dfc5f41d849d47bfaf600e40a7ccc9dd45da676
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763402"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="4d337-103">ISymUnmanagedScope::GetMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="4d337-103">ISymUnmanagedScope::GetMethod Method</span></span>

<span data-ttu-id="4d337-104">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="4d337-104">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d337-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d337-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d337-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d337-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="4d337-107">enuncia Puntero a la interfaz [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="4d337-107">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d337-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d337-108">Return Value</span></span>  

 <span data-ttu-id="4d337-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4d337-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d337-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d337-110">Requirements</span></span>  

 <span data-ttu-id="4d337-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4d337-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d337-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d337-112">See also</span></span>

- [<span data-ttu-id="4d337-113">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d337-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
