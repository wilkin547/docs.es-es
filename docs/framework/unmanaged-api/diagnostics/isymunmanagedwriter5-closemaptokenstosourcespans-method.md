---
title: "ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f5f23c3fe39adcebcfdfadb9e9c2b639f16330d1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="7cf7b-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="7cf7b-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="7cf7b-103">Cierre la sección especial de datos personalizado para la información de asignación de intervalo de origen de token.</span><span class="sxs-lookup"><span data-stu-id="7cf7b-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="7cf7b-104">Una vez que se ha cerrado puede agregarse no hay más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="7cf7b-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf7b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cf7b-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7cf7b-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7cf7b-106">Return Value</span></span>  
 <span data-ttu-id="7cf7b-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7cf7b-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cf7b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cf7b-108">Requirements</span></span>  
 <span data-ttu-id="7cf7b-109">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7cf7b-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf7b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cf7b-110">See Also</span></span>  
 [<span data-ttu-id="7cf7b-111">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cf7b-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
