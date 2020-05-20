---
title: ISymUnmanagedScope (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 1ee406c97fa4ccb7f87098cba2925568d8ce069f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615350"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="c19d8-102">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c19d8-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="c19d8-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="c19d8-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c19d8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c19d8-104">Methods</span></span>  
  
|<span data-ttu-id="c19d8-105">Método</span><span class="sxs-lookup"><span data-stu-id="c19d8-105">Method</span></span>|<span data-ttu-id="c19d8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c19d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c19d8-107">Método GetChildren</span><span class="sxs-lookup"><span data-stu-id="c19d8-107">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="c19d8-108">Obtiene los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c19d8-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="c19d8-109">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="c19d8-109">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="c19d8-110">Obtiene el desplazamiento final para este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c19d8-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="c19d8-111">Método GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="c19d8-111">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="c19d8-112">Obtiene un recuento de las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c19d8-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="c19d8-113">Método GetLocals</span><span class="sxs-lookup"><span data-stu-id="c19d8-113">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="c19d8-114">Obtiene las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c19d8-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="c19d8-115">Método GetMethod</span><span class="sxs-lookup"><span data-stu-id="c19d8-115">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="c19d8-116">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c19d8-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="c19d8-117">Método GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="c19d8-117">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="c19d8-118">Obtiene los espacios de nombres que se usan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c19d8-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="c19d8-119">Método GetParent</span><span class="sxs-lookup"><span data-stu-id="c19d8-119">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="c19d8-120">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c19d8-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="c19d8-121">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="c19d8-121">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="c19d8-122">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c19d8-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c19d8-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c19d8-123">Requirements</span></span>  
 <span data-ttu-id="c19d8-124">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c19d8-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c19d8-125">Consulta también</span><span class="sxs-lookup"><span data-stu-id="c19d8-125">See also</span></span>

- [<span data-ttu-id="c19d8-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="c19d8-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c19d8-127">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c19d8-127">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
