---
title: ISymUnmanagedWriter5 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 701b8de977d49a7d93f393b320bcb9d0d780c7bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="735ff-102">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="735ff-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="735ff-103">ISymUnmanagedWriter5 (interfaz).</span><span class="sxs-lookup"><span data-stu-id="735ff-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="735ff-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="735ff-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="735ff-105">Methods</span></span>  
 <span data-ttu-id="735ff-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="735ff-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="735ff-107">Método</span><span class="sxs-lookup"><span data-stu-id="735ff-107">Method</span></span>|<span data-ttu-id="735ff-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="735ff-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="735ff-109">CloseMapTokensToSourceSpans (método)</span><span class="sxs-lookup"><span data-stu-id="735ff-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="735ff-110">Cierre la sección especial de datos personalizado para la información de asignación de intervalo de origen de token.</span><span class="sxs-lookup"><span data-stu-id="735ff-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="735ff-111">Una vez que se ha cerrado puede agregarse no hay más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="735ff-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="735ff-112">MapTokenToSourceSpan (método)</span><span class="sxs-lookup"><span data-stu-id="735ff-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="735ff-113">Mapas que abarcan el token de metadatos especificado en la línea de código fuente en el archivo de origen especificado.</span><span class="sxs-lookup"><span data-stu-id="735ff-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="735ff-114">Debe llamarse entre las llamadas a [OpenMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y [CloseMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="735ff-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="735ff-115">OpenMapTokensToSourceSpans (método)</span><span class="sxs-lookup"><span data-stu-id="735ff-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="735ff-116">Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de origen de token en.</span><span class="sxs-lookup"><span data-stu-id="735ff-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="735ff-117">Apertura de esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="735ff-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="735ff-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="735ff-118">Requirements</span></span>  
 <span data-ttu-id="735ff-119">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="735ff-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735ff-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="735ff-120">See Also</span></span>  
 [<span data-ttu-id="735ff-121">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="735ff-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="735ff-122">ISymUnmanagedWriter4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="735ff-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
