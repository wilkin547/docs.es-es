---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 653dd933066898c1954cfbcc57c0c0493e47b4be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428617"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="48f44-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="48f44-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="48f44-103">Cierre la sección especial de datos personalizado para la información de asignación de intervalo de origen de token.</span><span class="sxs-lookup"><span data-stu-id="48f44-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="48f44-104">Una vez que se ha cerrado puede agregarse no hay más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="48f44-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f44-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48f44-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="48f44-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="48f44-106">Return Value</span></span>  
 <span data-ttu-id="48f44-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="48f44-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f44-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48f44-108">Requirements</span></span>  
 <span data-ttu-id="48f44-109">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="48f44-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f44-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="48f44-110">See Also</span></span>  
 [<span data-ttu-id="48f44-111">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48f44-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
