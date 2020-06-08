---
title: ISymUnmanagedWriter5 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: d9204457b71b670e1c96ed228ad11116bdf41fe6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493583"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="0dae2-102">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0dae2-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="0dae2-103">Interfaz ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="0dae2-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dae2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0dae2-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="0dae2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0dae2-105">Methods</span></span>  
 <span data-ttu-id="0dae2-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="0dae2-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="0dae2-107">Método</span><span class="sxs-lookup"><span data-stu-id="0dae2-107">Method</span></span>|<span data-ttu-id="0dae2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0dae2-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0dae2-109">Método CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="0dae2-109">CloseMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="0dae2-110">Cierre la sección datos personalizados especiales para obtener información sobre la asignación de intervalos de token a origen.</span><span class="sxs-lookup"><span data-stu-id="0dae2-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="0dae2-111">Una vez cerrado, no se puede agregar más información de asignación.</span><span class="sxs-lookup"><span data-stu-id="0dae2-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="0dae2-112">Método MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="0dae2-112">MapTokenToSourceSpan Method</span></span>](isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="0dae2-113">Asigna el token de metadatos especificado al intervalo de la línea de código fuente especificado en el archivo de código fuente especificado.</span><span class="sxs-lookup"><span data-stu-id="0dae2-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="0dae2-114">Se debe llamar entre las llamadas al [método openmaptokenstosourcespans (](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y al [método closemaptokenstosourcespans (](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="0dae2-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="0dae2-115">Método OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="0dae2-115">OpenMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="0dae2-116">Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de token a origen en.</span><span class="sxs-lookup"><span data-stu-id="0dae2-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="0dae2-117">Abrir esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="0dae2-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0dae2-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0dae2-118">Requirements</span></span>  
 <span data-ttu-id="0dae2-119">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0dae2-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dae2-120">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0dae2-120">See also</span></span>

- [<span data-ttu-id="0dae2-121">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="0dae2-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="0dae2-122">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0dae2-122">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
