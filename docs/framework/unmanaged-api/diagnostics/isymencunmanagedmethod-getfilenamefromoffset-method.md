---
title: "ISymENCUnmanagedMethod::GetFileNameFromOffset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9dcdbf7813c7ce3d451a27c0abf08c661a8f17b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="5504d-102">ISymENCUnmanagedMethod::GetFileNameFromOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="5504d-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="5504d-103">Obtiene el nombre de archivo de la línea asociada con un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="5504d-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5504d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5504d-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5504d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5504d-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="5504d-106">[in] Un `ULONG32` que contiene el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="5504d-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5504d-107">[in] A `ULONG32` que indica el tamaño de la `szName` búfer.</span><span class="sxs-lookup"><span data-stu-id="5504d-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5504d-108">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="5504d-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="5504d-109">[out] Búfer que contiene los nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="5504d-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5504d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5504d-110">Return Value</span></span>  
 <span data-ttu-id="5504d-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5504d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5504d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5504d-112">Requirements</span></span>  
 <span data-ttu-id="5504d-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5504d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5504d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5504d-114">See Also</span></span>  
 [<span data-ttu-id="5504d-115">ISymENCUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5504d-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
