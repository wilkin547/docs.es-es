---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a33d8b489551dc69542e1b12bcf83602ec5a2008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427253"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="7887e-102">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7887e-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="7887e-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="7887e-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="7887e-104">Esta interfaz extiende la [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaz con métodos que obtienen información sobre las constantes definidas dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="7887e-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7887e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7887e-105">Methods</span></span>  
  
|<span data-ttu-id="7887e-106">Método</span><span class="sxs-lookup"><span data-stu-id="7887e-106">Method</span></span>|<span data-ttu-id="7887e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7887e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7887e-108">GetConstantCount (método)</span><span class="sxs-lookup"><span data-stu-id="7887e-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="7887e-109">Obtiene un recuento de las constantes definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="7887e-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="7887e-110">GetConstants (método)</span><span class="sxs-lookup"><span data-stu-id="7887e-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="7887e-111">Obtiene las constantes locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="7887e-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7887e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7887e-112">Requirements</span></span>  
 <span data-ttu-id="7887e-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7887e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7887e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7887e-114">See Also</span></span>  
 [<span data-ttu-id="7887e-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="7887e-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="7887e-116">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7887e-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
