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
ms.openlocfilehash: 1534955c1f7cfd37732a08b0b33cda5bff8a8aab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113027"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="9a6cd-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT (Método)</span><span class="sxs-lookup"><span data-stu-id="9a6cd-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="9a6cd-103">Obtiene el valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="9a6cd-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a6cd-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a6cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a6cd-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="9a6cd-106">[out] Un puntero a HRESULT.</span><span class="sxs-lookup"><span data-stu-id="9a6cd-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a6cd-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a6cd-107">Return Value</span></span>  
 <span data-ttu-id="9a6cd-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9a6cd-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a6cd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a6cd-109">Requirements</span></span>  
 <span data-ttu-id="9a6cd-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9a6cd-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6cd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a6cd-111">See also</span></span>

- [<span data-ttu-id="9a6cd-112">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a6cd-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
