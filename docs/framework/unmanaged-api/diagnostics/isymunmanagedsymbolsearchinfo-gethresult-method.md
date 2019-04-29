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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638624"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="e24b9-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT (Método)</span><span class="sxs-lookup"><span data-stu-id="e24b9-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="e24b9-103">Obtiene el valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="e24b9-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e24b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e24b9-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e24b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e24b9-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="e24b9-106">[out] Un puntero a HRESULT.</span><span class="sxs-lookup"><span data-stu-id="e24b9-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e24b9-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e24b9-107">Return Value</span></span>  
 <span data-ttu-id="e24b9-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e24b9-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e24b9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e24b9-109">Requirements</span></span>  
 <span data-ttu-id="e24b9-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e24b9-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e24b9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e24b9-111">See also</span></span>

- [<span data-ttu-id="e24b9-112">ISymUnmanagedSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e24b9-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
