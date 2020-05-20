---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 053727604c795bf43a9b1658d5841fe85f53090a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614635"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="b0ce9-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="b0ce9-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="b0ce9-103">Cierre la sección datos personalizados especiales para obtener información sobre la asignación de intervalos de token a origen.</span><span class="sxs-lookup"><span data-stu-id="b0ce9-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="b0ce9-104">Una vez cerrado, no se puede agregar más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="b0ce9-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ce9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0ce9-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b0ce9-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b0ce9-106">Return Value</span></span>  
 <span data-ttu-id="b0ce9-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="b0ce9-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0ce9-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0ce9-108">Requirements</span></span>  
 <span data-ttu-id="b0ce9-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b0ce9-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ce9-110">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b0ce9-110">See also</span></span>

- [<span data-ttu-id="b0ce9-111">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0ce9-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
