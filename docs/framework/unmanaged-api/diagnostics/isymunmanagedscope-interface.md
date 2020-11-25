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
ms.openlocfilehash: 9256342ad3a91e6770d6fd19d9d2f94fab267d3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725890"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="17177-102">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17177-102">ISymUnmanagedScope Interface</span></span>

<span data-ttu-id="17177-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="17177-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17177-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="17177-104">Methods</span></span>  
  
|<span data-ttu-id="17177-105">Método</span><span class="sxs-lookup"><span data-stu-id="17177-105">Method</span></span>|<span data-ttu-id="17177-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="17177-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17177-107">Método GetChildren</span><span class="sxs-lookup"><span data-stu-id="17177-107">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="17177-108">Obtiene los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="17177-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="17177-109">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="17177-109">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="17177-110">Obtiene el desplazamiento final para este ámbito.</span><span class="sxs-lookup"><span data-stu-id="17177-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="17177-111">Método GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="17177-111">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="17177-112">Obtiene un recuento de las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="17177-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="17177-113">Método GetLocals</span><span class="sxs-lookup"><span data-stu-id="17177-113">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="17177-114">Obtiene las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="17177-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="17177-115">Método GetMethod</span><span class="sxs-lookup"><span data-stu-id="17177-115">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="17177-116">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="17177-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="17177-117">Método GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="17177-117">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="17177-118">Obtiene los espacios de nombres que se usan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="17177-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="17177-119">Método GetParent</span><span class="sxs-lookup"><span data-stu-id="17177-119">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="17177-120">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="17177-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="17177-121">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="17177-121">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="17177-122">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="17177-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17177-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17177-123">Requirements</span></span>  

 <span data-ttu-id="17177-124">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="17177-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17177-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17177-125">See also</span></span>

- [<span data-ttu-id="17177-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="17177-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="17177-127">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17177-127">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
