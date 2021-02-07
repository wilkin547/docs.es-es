---
description: 'Más información sobre: ISymUnmanagedWriter5:: Closemaptokenstosourcespans ((método)'
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 687a853441a4406c2eb0a9c4b3d5d59df3575e1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761660"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="8ef99-103">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="8ef99-103">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="8ef99-104">Cierre la sección datos personalizados especiales para obtener información sobre la asignación de intervalos de token a origen.</span><span class="sxs-lookup"><span data-stu-id="8ef99-104">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="8ef99-105">Una vez cerrado, no se puede agregar más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="8ef99-105">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef99-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ef99-106">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8ef99-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8ef99-107">Return Value</span></span>  

 <span data-ttu-id="8ef99-108">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8ef99-108">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ef99-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ef99-109">Requirements</span></span>  

 <span data-ttu-id="8ef99-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8ef99-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef99-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ef99-111">See also</span></span>

- [<span data-ttu-id="8ef99-112">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ef99-112">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
