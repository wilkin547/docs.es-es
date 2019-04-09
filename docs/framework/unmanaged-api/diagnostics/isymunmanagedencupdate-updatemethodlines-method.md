---
title: ISymUnmanagedENCUpdate::UpdateMethodLines (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd1f101e2e9cf9baeb28290c7607ccab3d8d7440
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178924"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="ff0ea-102">ISymUnmanagedENCUpdate::UpdateMethodLines (Método)</span><span class="sxs-lookup"><span data-stu-id="ff0ea-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="ff0ea-103">Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han movido por separado.</span><span class="sxs-lookup"><span data-stu-id="ff0ea-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="ff0ea-104">Se permite un carácter delta para cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="ff0ea-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff0ea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff0ea-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff0ea-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff0ea-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="ff0ea-107">[in] Los metadatos del token del método.</span><span class="sxs-lookup"><span data-stu-id="ff0ea-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="ff0ea-108">[in] Una matriz de `INT32` valores que indica los valores delta para cada punto de secuencia en el método.</span><span class="sxs-lookup"><span data-stu-id="ff0ea-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="ff0ea-109">[in] Un `ULONG` que contiene el tamaño de la `pDeltas` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ff0ea-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff0ea-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff0ea-110">Return Value</span></span>  
 <span data-ttu-id="ff0ea-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ff0ea-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff0ea-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff0ea-112">Requirements</span></span>  
 <span data-ttu-id="ff0ea-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ff0ea-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff0ea-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff0ea-114">See also</span></span>

- [<span data-ttu-id="ff0ea-115">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff0ea-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
