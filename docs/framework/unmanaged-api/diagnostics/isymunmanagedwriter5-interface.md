---
description: 'Más información acerca de: interfaz ISymUnmanagedWriter5'
title: ISymUnmanagedWriter5 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: 0902385576e1eed17cea672b04858c7e3ef7add8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761634"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="1fc43-103">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1fc43-103">ISymUnmanagedWriter5 Interface</span></span>

<span data-ttu-id="1fc43-104">Interfaz ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="1fc43-104">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fc43-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fc43-105">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="1fc43-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="1fc43-106">Methods</span></span>  

 <span data-ttu-id="1fc43-107">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="1fc43-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="1fc43-108">Método</span><span class="sxs-lookup"><span data-stu-id="1fc43-108">Method</span></span>|<span data-ttu-id="1fc43-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1fc43-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1fc43-110">Método CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="1fc43-110">CloseMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="1fc43-111">Cierre la sección datos personalizados especiales para obtener información sobre la asignación de intervalos de token a origen.</span><span class="sxs-lookup"><span data-stu-id="1fc43-111">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="1fc43-112">Una vez cerrado, no se puede agregar más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="1fc43-112">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="1fc43-113">Método MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="1fc43-113">MapTokenToSourceSpan Method</span></span>](isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="1fc43-114">Asigna el token de metadatos especificado al intervalo de la línea de código fuente especificado en el archivo de código fuente especificado.</span><span class="sxs-lookup"><span data-stu-id="1fc43-114">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="1fc43-115">Se debe llamar entre las llamadas al [método openmaptokenstosourcespans (](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y al [método closemaptokenstosourcespans (](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="1fc43-115">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="1fc43-116">Método OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="1fc43-116">OpenMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="1fc43-117">Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de token a origen en.</span><span class="sxs-lookup"><span data-stu-id="1fc43-117">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="1fc43-118">Abrir esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="1fc43-118">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1fc43-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1fc43-119">Requirements</span></span>  

 <span data-ttu-id="1fc43-120">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1fc43-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc43-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fc43-121">See also</span></span>

- [<span data-ttu-id="1fc43-122">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="1fc43-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="1fc43-123">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1fc43-123">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
