---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37e9926c8f9677e3b38202c5fb3c43f7b1159edf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953574"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="a61de-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength (Método)</span><span class="sxs-lookup"><span data-stu-id="a61de-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="a61de-103">Obtiene la longitud de ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a61de-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a61de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a61de-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a61de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a61de-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="a61de-106">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la longitud de ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a61de-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a61de-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a61de-107">Return Value</span></span>  
 <span data-ttu-id="a61de-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a61de-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a61de-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a61de-109">Requirements</span></span>  
 <span data-ttu-id="a61de-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a61de-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a61de-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a61de-111">See also</span></span>

- [<span data-ttu-id="a61de-112">ISymUnmanagedSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a61de-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
