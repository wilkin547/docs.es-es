---
description: 'Más información acerca de: ISymUnmanagedScope:: GetParent (método)'
title: ISymUnmanagedScope::GetParent (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
ms.openlocfilehash: c6a056c828bfaefd171ef3f0c546d93d30fb6863
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763337"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="62254-103">ISymUnmanagedScope::GetParent (Método)</span><span class="sxs-lookup"><span data-stu-id="62254-103">ISymUnmanagedScope::GetParent Method</span></span>

<span data-ttu-id="62254-104">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="62254-104">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62254-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62254-105">Syntax</span></span>  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62254-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62254-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="62254-107">enuncia Puntero a la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="62254-107">[out] A pointer to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62254-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="62254-108">Return Value</span></span>  

 <span data-ttu-id="62254-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="62254-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62254-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62254-110">Requirements</span></span>  

 <span data-ttu-id="62254-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="62254-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62254-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="62254-112">See also</span></span>

- [<span data-ttu-id="62254-113">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62254-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="62254-114">Método GetChildren</span><span class="sxs-lookup"><span data-stu-id="62254-114">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)
