---
title: ISymUnmanagedWriter5 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88a9fa2f720db403c45d4254b17dfaf4689cd0f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706909"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="118ac-102">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="118ac-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="118ac-103">ISymUnmanagedWriter5 (interfaz).</span><span class="sxs-lookup"><span data-stu-id="118ac-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="118ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="118ac-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="118ac-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="118ac-105">Methods</span></span>  
 <span data-ttu-id="118ac-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="118ac-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="118ac-107">Método</span><span class="sxs-lookup"><span data-stu-id="118ac-107">Method</span></span>|<span data-ttu-id="118ac-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="118ac-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="118ac-109">CloseMapTokensToSourceSpans (método)</span><span class="sxs-lookup"><span data-stu-id="118ac-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="118ac-110">Cerrar la sección de datos personalizado especial para información sobre la asignación de intervalo de origen de token.</span><span class="sxs-lookup"><span data-stu-id="118ac-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="118ac-111">Después de cerrar, no se puede agregar ninguna información de asignación.</span><span class="sxs-lookup"><span data-stu-id="118ac-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="118ac-112">MapTokenToSourceSpan (método)</span><span class="sxs-lookup"><span data-stu-id="118ac-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="118ac-113">Asignaciones que abarcan el token de metadatos especificado a la línea de origen especificado en el archivo de origen especificado.</span><span class="sxs-lookup"><span data-stu-id="118ac-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="118ac-114">Debe llamarse entre las llamadas a [OpenMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y [CloseMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="118ac-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="118ac-115">OpenMapTokensToSourceSpans (método)</span><span class="sxs-lookup"><span data-stu-id="118ac-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="118ac-116">Abra una sección especial de datos personalizados para emitir la información de asignación de intervalo de origen de token en.</span><span class="sxs-lookup"><span data-stu-id="118ac-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="118ac-117">Apertura de esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="118ac-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="118ac-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="118ac-118">Requirements</span></span>  
 <span data-ttu-id="118ac-119">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="118ac-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118ac-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="118ac-120">See also</span></span>
- [<span data-ttu-id="118ac-121">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="118ac-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="118ac-122">ISymUnmanagedWriter4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="118ac-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
