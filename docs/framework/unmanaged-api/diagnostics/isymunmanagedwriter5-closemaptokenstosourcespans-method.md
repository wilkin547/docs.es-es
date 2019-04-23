---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3dea6b9710f1ee5ccf8c51261f59b2de026f5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127782"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="549fd-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="549fd-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="549fd-103">Cerrar la sección de datos personalizado especial para información sobre la asignación de intervalo de origen de token.</span><span class="sxs-lookup"><span data-stu-id="549fd-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="549fd-104">Después de cerrar, no se puede agregar ninguna información de asignación.</span><span class="sxs-lookup"><span data-stu-id="549fd-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="549fd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="549fd-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="549fd-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="549fd-106">Return Value</span></span>  
 <span data-ttu-id="549fd-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="549fd-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="549fd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="549fd-108">Requirements</span></span>  
 <span data-ttu-id="549fd-109">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="549fd-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="549fd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="549fd-110">See also</span></span>

- [<span data-ttu-id="549fd-111">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="549fd-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
