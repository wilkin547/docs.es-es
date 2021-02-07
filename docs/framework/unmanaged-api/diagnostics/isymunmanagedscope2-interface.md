---
description: 'Más información acerca de: interfaz ISymUnmanagedScope2'
title: ISymUnmanagedScope2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: a15094da68b00dbec454b2f6a642ac333f9a34ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763155"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="fb215-103">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb215-103">ISymUnmanagedScope2 Interface</span></span>

<span data-ttu-id="fb215-104">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="fb215-104">Represents a lexical scope within a method.</span></span> <span data-ttu-id="fb215-105">Esta interfaz extiende la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) con métodos que obtienen información sobre las constantes definidas dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="fb215-105">This interface extends the [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb215-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="fb215-106">Methods</span></span>  
  
|<span data-ttu-id="fb215-107">Método</span><span class="sxs-lookup"><span data-stu-id="fb215-107">Method</span></span>|<span data-ttu-id="fb215-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb215-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb215-109">Método GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="fb215-109">GetConstantCount Method</span></span>](isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="fb215-110">Obtiene un recuento de las constantes definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="fb215-110">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="fb215-111">Método GetConstants</span><span class="sxs-lookup"><span data-stu-id="fb215-111">GetConstants Method</span></span>](isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="fb215-112">Obtiene las constantes locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="fb215-112">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb215-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb215-113">Requirements</span></span>  

 <span data-ttu-id="fb215-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="fb215-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb215-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb215-115">See also</span></span>

- [<span data-ttu-id="fb215-116">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fb215-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="fb215-117">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb215-117">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
