---
description: 'Más información sobre: ISymUnmanagedENCUpdate:: Updatemethodlines ((método)'
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
ms.openlocfilehash: 6174f3aa980ccf2cdc07720e3aa90b7bb74a77af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710067"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="dd83f-103">ISymUnmanagedENCUpdate::UpdateMethodLines (Método)</span><span class="sxs-lookup"><span data-stu-id="dd83f-103">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>

<span data-ttu-id="dd83f-104">Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han desplace por separado.</span><span class="sxs-lookup"><span data-stu-id="dd83f-104">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="dd83f-105">Se permite una diferencia de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="dd83f-105">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd83f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd83f-106">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd83f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd83f-107">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="dd83f-108">de Metadatos del token de método.</span><span class="sxs-lookup"><span data-stu-id="dd83f-108">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="dd83f-109">de Matriz de `INT32` valores que indica deltas para cada punto de secuencia del método.</span><span class="sxs-lookup"><span data-stu-id="dd83f-109">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="dd83f-110">de Un valor `ULONG` de tipo que contiene el tamaño del `pDeltas` parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd83f-110">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd83f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dd83f-111">Return Value</span></span>  

 <span data-ttu-id="dd83f-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="dd83f-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd83f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd83f-113">Requirements</span></span>  

 <span data-ttu-id="dd83f-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="dd83f-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd83f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd83f-115">See also</span></span>

- [<span data-ttu-id="dd83f-116">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd83f-116">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
