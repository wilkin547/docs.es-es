---
description: 'Más información sobre: ISymUnmanagedMethod:: GetRootScope ((método)'
title: ISymUnmanagedMethod::GetRootScope (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: b1e490d8e0c5e0d60143202dd0291237685c950f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710013"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="65571-103">ISymUnmanagedMethod::GetRootScope (Método)</span><span class="sxs-lookup"><span data-stu-id="65571-103">ISymUnmanagedMethod::GetRootScope Method</span></span>

<span data-ttu-id="65571-104">Obtiene el ámbito léxico raíz dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="65571-104">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="65571-105">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="65571-105">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65571-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65571-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65571-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65571-107">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="65571-108">enuncia Puntero que se establece en la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="65571-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65571-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="65571-109">Return Value</span></span>  

 <span data-ttu-id="65571-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="65571-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65571-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65571-111">Requirements</span></span>  

 <span data-ttu-id="65571-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="65571-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65571-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="65571-113">See also</span></span>

- [<span data-ttu-id="65571-114">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65571-114">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
