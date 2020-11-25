---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: b57174f9f76b174927b8f1997beac3dd1482583a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725916"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="1bc1d-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="1bc1d-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="1bc1d-103">Cierre la sección datos personalizados especiales para obtener información sobre la asignación de intervalos de token a origen.</span><span class="sxs-lookup"><span data-stu-id="1bc1d-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="1bc1d-104">Una vez cerrado, no se puede agregar más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="1bc1d-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bc1d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bc1d-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1bc1d-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1bc1d-106">Return Value</span></span>  

 <span data-ttu-id="1bc1d-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="1bc1d-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bc1d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bc1d-108">Requirements</span></span>  

 <span data-ttu-id="1bc1d-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1bc1d-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc1d-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bc1d-110">See also</span></span>

- [<span data-ttu-id="1bc1d-111">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bc1d-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
