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
ms.openlocfilehash: 99499b8717f219616b6b368e6393b4b7ca0a79d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699591"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="9153e-102">ISymUnmanagedENCUpdate::UpdateMethodLines (Método)</span><span class="sxs-lookup"><span data-stu-id="9153e-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>

<span data-ttu-id="9153e-103">Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han desplace por separado.</span><span class="sxs-lookup"><span data-stu-id="9153e-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="9153e-104">Se permite una diferencia de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="9153e-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9153e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9153e-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9153e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9153e-106">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="9153e-107">de Metadatos del token de método.</span><span class="sxs-lookup"><span data-stu-id="9153e-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="9153e-108">de Matriz de `INT32` valores que indica deltas para cada punto de secuencia del método.</span><span class="sxs-lookup"><span data-stu-id="9153e-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="9153e-109">de Un valor `ULONG` de tipo que contiene el tamaño del `pDeltas` parámetro.</span><span class="sxs-lookup"><span data-stu-id="9153e-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9153e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9153e-110">Return Value</span></span>  

 <span data-ttu-id="9153e-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9153e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9153e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9153e-112">Requirements</span></span>  

 <span data-ttu-id="9153e-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9153e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9153e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9153e-114">See also</span></span>

- [<span data-ttu-id="9153e-115">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9153e-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
