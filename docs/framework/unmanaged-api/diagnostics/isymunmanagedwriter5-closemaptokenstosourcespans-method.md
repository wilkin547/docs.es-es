---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 43c35596d31842b85bbdc96a63413a176a59a172
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121652"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="4f246-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="4f246-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="4f246-103">Cierre la sección datos personalizados especiales para obtener información sobre la asignación de intervalos de token a origen.</span><span class="sxs-lookup"><span data-stu-id="4f246-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="4f246-104">Una vez cerrado, no se puede agregar más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="4f246-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f246-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f246-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4f246-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4f246-106">Return Value</span></span>  
 <span data-ttu-id="4f246-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="4f246-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f246-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f246-108">Requirements</span></span>  
 <span data-ttu-id="4f246-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4f246-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f246-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f246-110">See also</span></span>

- [<span data-ttu-id="4f246-111">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f246-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
