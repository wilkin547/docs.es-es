---
title: ISymUnmanagedWriter5 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5fd7c2bd4fae94d1ef5021b558a04b734803b68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430562"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="7d0d6-102">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d0d6-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="7d0d6-103">ISymUnmanagedWriter5 (interfaz).</span><span class="sxs-lookup"><span data-stu-id="7d0d6-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d0d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d0d6-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="7d0d6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7d0d6-105">Methods</span></span>  
 <span data-ttu-id="7d0d6-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="7d0d6-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="7d0d6-107">Método</span><span class="sxs-lookup"><span data-stu-id="7d0d6-107">Method</span></span>|<span data-ttu-id="7d0d6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d0d6-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d0d6-109">CloseMapTokensToSourceSpans (método)</span><span class="sxs-lookup"><span data-stu-id="7d0d6-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="7d0d6-110">Cierre la sección especial de datos personalizado para la información de asignación de intervalo de origen de token.</span><span class="sxs-lookup"><span data-stu-id="7d0d6-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="7d0d6-111">Una vez que se ha cerrado puede agregarse no hay más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="7d0d6-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="7d0d6-112">MapTokenToSourceSpan (método)</span><span class="sxs-lookup"><span data-stu-id="7d0d6-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="7d0d6-113">Mapas que abarcan el token de metadatos especificado en la línea de código fuente en el archivo de origen especificado.</span><span class="sxs-lookup"><span data-stu-id="7d0d6-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="7d0d6-114">Debe llamarse entre las llamadas a [OpenMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y [CloseMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="7d0d6-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="7d0d6-115">OpenMapTokensToSourceSpans (método)</span><span class="sxs-lookup"><span data-stu-id="7d0d6-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="7d0d6-116">Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de origen de token en.</span><span class="sxs-lookup"><span data-stu-id="7d0d6-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="7d0d6-117">Apertura de esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="7d0d6-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d0d6-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d0d6-118">Requirements</span></span>  
 <span data-ttu-id="7d0d6-119">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7d0d6-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d0d6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d0d6-120">See Also</span></span>  
 [<span data-ttu-id="7d0d6-121">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="7d0d6-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="7d0d6-122">ISymUnmanagedWriter4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d0d6-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
