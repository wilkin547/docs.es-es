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
ms.openlocfilehash: 0109b25b1cdc42204fc4873577e495641c4ec4fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761577"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="ac163-102">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac163-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="ac163-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="ac163-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="ac163-104">Esta interfaz extiende la [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaz con métodos que obtienen información sobre las constantes definidas dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="ac163-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac163-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ac163-105">Methods</span></span>  
  
|<span data-ttu-id="ac163-106">Método</span><span class="sxs-lookup"><span data-stu-id="ac163-106">Method</span></span>|<span data-ttu-id="ac163-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac163-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac163-108">GetConstantCount (método)</span><span class="sxs-lookup"><span data-stu-id="ac163-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="ac163-109">Obtiene un recuento de las constantes definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="ac163-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="ac163-110">GetConstants (método)</span><span class="sxs-lookup"><span data-stu-id="ac163-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="ac163-111">Obtiene las constantes locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="ac163-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac163-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac163-112">Requirements</span></span>  
 <span data-ttu-id="ac163-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ac163-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac163-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac163-114">See also</span></span>

- [<span data-ttu-id="ac163-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="ac163-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ac163-116">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac163-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
