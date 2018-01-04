---
title: "ISymUnmanagedENCUpdate::UpdateMethodLines (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.UpdateMethodLines
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e8ffecba62b6531c852e6510013ba56b9258b64
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="ada9f-102">ISymUnmanagedENCUpdate::UpdateMethodLines (Método)</span><span class="sxs-lookup"><span data-stu-id="ada9f-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="ada9f-103">Permite actualizar la información de línea para un método que no se han recopilado, pero cuyos líneas se han movido por separado.</span><span class="sxs-lookup"><span data-stu-id="ada9f-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="ada9f-104">Se permite un carácter delta para cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="ada9f-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ada9f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ada9f-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ada9f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ada9f-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="ada9f-107">[in] Los metadatos del token del método.</span><span class="sxs-lookup"><span data-stu-id="ada9f-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="ada9f-108">[in] Una matriz de `INT32` valores que indica los caracteres delta para cada punto de secuencia en el método.</span><span class="sxs-lookup"><span data-stu-id="ada9f-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="ada9f-109">[in] A `ULONG` que contiene el tamaño de la `pDeltas` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ada9f-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ada9f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ada9f-110">Return Value</span></span>  
 <span data-ttu-id="ada9f-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ada9f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ada9f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ada9f-112">Requirements</span></span>  
 <span data-ttu-id="ada9f-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ada9f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ada9f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ada9f-114">See Also</span></span>  
 [<span data-ttu-id="ada9f-115">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ada9f-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
