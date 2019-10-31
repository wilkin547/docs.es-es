---
title: ISymUnmanagedWriter5 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: 18371b6aefb002f5adf27d43f85194c6c35f6ef5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121638"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="5aa7e-102">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5aa7e-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="5aa7e-103">Interfaz ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="5aa7e-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aa7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5aa7e-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="5aa7e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5aa7e-105">Methods</span></span>  
 <span data-ttu-id="5aa7e-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="5aa7e-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="5aa7e-107">Método</span><span class="sxs-lookup"><span data-stu-id="5aa7e-107">Method</span></span>|<span data-ttu-id="5aa7e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5aa7e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5aa7e-109">CloseMapTokensToSourceSpans (método)</span><span class="sxs-lookup"><span data-stu-id="5aa7e-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="5aa7e-110">Cierre la sección datos personalizados especiales para obtener información sobre la asignación de intervalos de token a origen.</span><span class="sxs-lookup"><span data-stu-id="5aa7e-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="5aa7e-111">Una vez cerrado, no se puede agregar más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="5aa7e-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="5aa7e-112">MapTokenToSourceSpan (método)</span><span class="sxs-lookup"><span data-stu-id="5aa7e-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="5aa7e-113">Asigna el token de metadatos especificado al intervalo de la línea de código fuente especificado en el archivo de código fuente especificado.</span><span class="sxs-lookup"><span data-stu-id="5aa7e-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="5aa7e-114">Se debe llamar entre las llamadas al [método openmaptokenstosourcespans (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y al [método closemaptokenstosourcespans (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="5aa7e-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="5aa7e-115">OpenMapTokensToSourceSpans (método)</span><span class="sxs-lookup"><span data-stu-id="5aa7e-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="5aa7e-116">Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de token a origen en.</span><span class="sxs-lookup"><span data-stu-id="5aa7e-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="5aa7e-117">Abrir esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="5aa7e-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5aa7e-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5aa7e-118">Requirements</span></span>  
 <span data-ttu-id="5aa7e-119">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5aa7e-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa7e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5aa7e-120">See also</span></span>

- [<span data-ttu-id="5aa7e-121">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="5aa7e-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="5aa7e-122">ISymUnmanagedWriter4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5aa7e-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
