---
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
ms.openlocfilehash: 95ae081d61200e4fd020609a4d23783f265d2cc6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615363"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="1b6f5-102">ISymUnmanagedScope::GetParent (Método)</span><span class="sxs-lookup"><span data-stu-id="1b6f5-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="1b6f5-103">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="1b6f5-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b6f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b6f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b6f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b6f5-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1b6f5-106">enuncia Puntero a la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="1b6f5-106">[out] A pointer to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b6f5-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1b6f5-107">Return Value</span></span>  
 <span data-ttu-id="1b6f5-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1b6f5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b6f5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b6f5-109">Requirements</span></span>  
 <span data-ttu-id="1b6f5-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1b6f5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6f5-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1b6f5-111">See also</span></span>

- [<span data-ttu-id="1b6f5-112">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b6f5-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="1b6f5-113">Método GetChildren</span><span class="sxs-lookup"><span data-stu-id="1b6f5-113">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)
