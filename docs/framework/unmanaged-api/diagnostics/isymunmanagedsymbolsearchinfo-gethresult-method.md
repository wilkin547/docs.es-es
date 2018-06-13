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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 775f5a2129a635c79a48d5218d5eb91ee83ee779
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427888"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="7450b-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT (Método)</span><span class="sxs-lookup"><span data-stu-id="7450b-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="7450b-103">Obtiene el valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="7450b-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7450b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7450b-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7450b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7450b-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="7450b-106">[out] Un puntero para el valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="7450b-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7450b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7450b-107">Return Value</span></span>  
 <span data-ttu-id="7450b-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7450b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7450b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7450b-109">Requirements</span></span>  
 <span data-ttu-id="7450b-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7450b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7450b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7450b-111">See Also</span></span>  
 [<span data-ttu-id="7450b-112">ISymUnmanagedSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7450b-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
