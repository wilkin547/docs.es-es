---
description: 'Más información acerca de: ISymUnmanagedScope (interfaz)'
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
ms.openlocfilehash: f1175656fb49ee16fd1cd676d08f6ebb76f40c6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763272"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="15c57-103">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15c57-103">ISymUnmanagedScope Interface</span></span>

<span data-ttu-id="15c57-104">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="15c57-104">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15c57-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="15c57-105">Methods</span></span>  
  
|<span data-ttu-id="15c57-106">Método</span><span class="sxs-lookup"><span data-stu-id="15c57-106">Method</span></span>|<span data-ttu-id="15c57-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="15c57-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15c57-108">Método GetChildren</span><span class="sxs-lookup"><span data-stu-id="15c57-108">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="15c57-109">Obtiene los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="15c57-109">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="15c57-110">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="15c57-110">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="15c57-111">Obtiene el desplazamiento final para este ámbito.</span><span class="sxs-lookup"><span data-stu-id="15c57-111">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="15c57-112">Método GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="15c57-112">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="15c57-113">Obtiene un recuento de las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="15c57-113">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="15c57-114">Método GetLocals</span><span class="sxs-lookup"><span data-stu-id="15c57-114">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="15c57-115">Obtiene las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="15c57-115">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="15c57-116">Método GetMethod</span><span class="sxs-lookup"><span data-stu-id="15c57-116">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="15c57-117">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="15c57-117">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="15c57-118">Método GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="15c57-118">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="15c57-119">Obtiene los espacios de nombres que se usan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="15c57-119">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="15c57-120">Método GetParent</span><span class="sxs-lookup"><span data-stu-id="15c57-120">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="15c57-121">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="15c57-121">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="15c57-122">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="15c57-122">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="15c57-123">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="15c57-123">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15c57-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15c57-124">Requirements</span></span>  

 <span data-ttu-id="15c57-125">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="15c57-125">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c57-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="15c57-126">See also</span></span>

- [<span data-ttu-id="15c57-127">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="15c57-127">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="15c57-128">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15c57-128">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
