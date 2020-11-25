---
title: ISymUnmanagedSymbolSearchInfo::GetHRESULT (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: a931c15b1c4a9f099d11c43edd324cfcc2793090
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722276"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="78d69-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT (Método)</span><span class="sxs-lookup"><span data-stu-id="78d69-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>

<span data-ttu-id="78d69-103">Obtiene el HRESULT.</span><span class="sxs-lookup"><span data-stu-id="78d69-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78d69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78d69-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78d69-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78d69-105">Parameters</span></span>  

 `phr`  
 <span data-ttu-id="78d69-106">enuncia Puntero al HRESULT.</span><span class="sxs-lookup"><span data-stu-id="78d69-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78d69-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="78d69-107">Return Value</span></span>  

 <span data-ttu-id="78d69-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="78d69-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78d69-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78d69-109">Requirements</span></span>  

 <span data-ttu-id="78d69-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="78d69-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d69-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78d69-111">See also</span></span>

- [<span data-ttu-id="78d69-112">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="78d69-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
