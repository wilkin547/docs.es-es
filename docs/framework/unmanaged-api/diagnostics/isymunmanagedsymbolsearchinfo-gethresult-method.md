---
description: 'Más información sobre: ISymUnmanagedSymbolSearchInfo:: Gethresult ((método)'
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
ms.openlocfilehash: 5d351d84ba4e91ccb9acb531e77407a2d1caceec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763116"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="a320a-103">ISymUnmanagedSymbolSearchInfo::GetHRESULT (Método)</span><span class="sxs-lookup"><span data-stu-id="a320a-103">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>

<span data-ttu-id="a320a-104">Obtiene el HRESULT.</span><span class="sxs-lookup"><span data-stu-id="a320a-104">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a320a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a320a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a320a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a320a-106">Parameters</span></span>  

 `phr`  
 <span data-ttu-id="a320a-107">enuncia Puntero al HRESULT.</span><span class="sxs-lookup"><span data-stu-id="a320a-107">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a320a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a320a-108">Return Value</span></span>  

 <span data-ttu-id="a320a-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a320a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a320a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a320a-110">Requirements</span></span>  

 <span data-ttu-id="a320a-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a320a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a320a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a320a-112">See also</span></span>

- [<span data-ttu-id="a320a-113">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a320a-113">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
