---
title: ISymUnmanagedWriter5 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6ed8c6e61c558a4bc9e3f92d559615ac93ecff8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144240"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="2da99-102">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2da99-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="2da99-103">ISymUnmanagedWriter5 (interfaz).</span><span class="sxs-lookup"><span data-stu-id="2da99-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2da99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2da99-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="2da99-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2da99-105">Methods</span></span>  
 <span data-ttu-id="2da99-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="2da99-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="2da99-107">Método</span><span class="sxs-lookup"><span data-stu-id="2da99-107">Method</span></span>|<span data-ttu-id="2da99-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2da99-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2da99-109">Método CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="2da99-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="2da99-110">Cerrar la sección de datos personalizado especial para información sobre la asignación de intervalo de origen de token.</span><span class="sxs-lookup"><span data-stu-id="2da99-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="2da99-111">Después de cerrar, no se puede agregar ninguna información de asignación.</span><span class="sxs-lookup"><span data-stu-id="2da99-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="2da99-112">Método MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="2da99-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="2da99-113">Asignaciones que abarcan el token de metadatos especificado a la línea de origen especificado en el archivo de origen especificado.</span><span class="sxs-lookup"><span data-stu-id="2da99-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="2da99-114">Debe llamarse entre las llamadas a [OpenMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y [CloseMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="2da99-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="2da99-115">Método OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="2da99-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="2da99-116">Abra una sección especial de datos personalizados para emitir la información de asignación de intervalo de origen de token en.</span><span class="sxs-lookup"><span data-stu-id="2da99-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="2da99-117">Apertura de esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="2da99-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2da99-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2da99-118">Requirements</span></span>  
 <span data-ttu-id="2da99-119">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2da99-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da99-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2da99-120">See also</span></span>

- [<span data-ttu-id="2da99-121">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="2da99-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="2da99-122">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2da99-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
