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
ms.openlocfilehash: 9aace77c4b3549c033433d4c305b07daa1f7a8c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448995"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="e56fc-102">ISymUnmanagedENCUpdate::UpdateMethodLines (Método)</span><span class="sxs-lookup"><span data-stu-id="e56fc-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="e56fc-103">Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han desplace por separado.</span><span class="sxs-lookup"><span data-stu-id="e56fc-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="e56fc-104">Se permite una diferencia de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="e56fc-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e56fc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e56fc-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e56fc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e56fc-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="e56fc-107">de Metadatos del token de método.</span><span class="sxs-lookup"><span data-stu-id="e56fc-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="e56fc-108">de Matriz de valores de `INT32` que indica deltas para cada punto de secuencia del método.</span><span class="sxs-lookup"><span data-stu-id="e56fc-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="e56fc-109">de `ULONG` que contiene el tamaño del parámetro de `pDeltas`.</span><span class="sxs-lookup"><span data-stu-id="e56fc-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e56fc-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e56fc-110">Return Value</span></span>  
 <span data-ttu-id="e56fc-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e56fc-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e56fc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e56fc-112">Requirements</span></span>  
 <span data-ttu-id="e56fc-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e56fc-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e56fc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e56fc-114">See also</span></span>

- [<span data-ttu-id="e56fc-115">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e56fc-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
