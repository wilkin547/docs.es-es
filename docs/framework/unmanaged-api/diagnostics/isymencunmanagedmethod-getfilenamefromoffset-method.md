---
title: ISymENCUnmanagedMethod::GetFileNameFromOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: df1e9d317294127a931bebf100295290a0dd6b23
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471842"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="163c9-102">ISymENCUnmanagedMethod::GetFileNameFromOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="163c9-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="163c9-103">Obtiene el nombre de archivo de la línea asociada con un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="163c9-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="163c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="163c9-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="163c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="163c9-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="163c9-106">[in] Un `ULONG32` que contiene el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="163c9-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="163c9-107">[in] Un `ULONG32` que indica el tamaño de la `szName` búfer.</span><span class="sxs-lookup"><span data-stu-id="163c9-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="163c9-108">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="163c9-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="163c9-109">[out] Búfer que contiene los nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="163c9-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="163c9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="163c9-110">Return Value</span></span>  
 <span data-ttu-id="163c9-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="163c9-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="163c9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="163c9-112">Requirements</span></span>  
 <span data-ttu-id="163c9-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="163c9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163c9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="163c9-114">See also</span></span>
- [<span data-ttu-id="163c9-115">ISymENCUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="163c9-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
