---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3dea6b9710f1ee5ccf8c51261f59b2de026f5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962284"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="ae874-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="ae874-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="ae874-103">Cerrar la sección de datos personalizado especial para información sobre la asignación de intervalo de origen de token.</span><span class="sxs-lookup"><span data-stu-id="ae874-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="ae874-104">Después de cerrar, no se puede agregar ninguna información de asignación.</span><span class="sxs-lookup"><span data-stu-id="ae874-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae874-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae874-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ae874-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae874-106">Return Value</span></span>  
 <span data-ttu-id="ae874-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ae874-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae874-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae874-108">Requirements</span></span>  
 <span data-ttu-id="ae874-109">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ae874-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae874-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae874-110">See also</span></span>

- [<span data-ttu-id="ae874-111">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae874-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
