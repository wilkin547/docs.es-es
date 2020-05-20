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
ms.openlocfilehash: 9dcd8282adf200932e86c950bee0b073780ce02d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615311"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="1ed13-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT (Método)</span><span class="sxs-lookup"><span data-stu-id="1ed13-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="1ed13-103">Obtiene el HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1ed13-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ed13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ed13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ed13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ed13-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="1ed13-106">enuncia Puntero al HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1ed13-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ed13-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ed13-107">Return Value</span></span>  
 <span data-ttu-id="1ed13-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1ed13-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ed13-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ed13-109">Requirements</span></span>  
 <span data-ttu-id="1ed13-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1ed13-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed13-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1ed13-111">See also</span></span>

- [<span data-ttu-id="1ed13-112">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ed13-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
