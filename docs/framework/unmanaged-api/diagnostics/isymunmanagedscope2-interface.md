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
ms.openlocfilehash: 40c437e109eaa4352a83c5566185593cbc6b0eba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725838"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="341f4-102">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="341f4-102">ISymUnmanagedScope2 Interface</span></span>

<span data-ttu-id="341f4-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="341f4-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="341f4-104">Esta interfaz extiende la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) con métodos que obtienen información sobre las constantes definidas dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="341f4-104">This interface extends the [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="341f4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="341f4-105">Methods</span></span>  
  
|<span data-ttu-id="341f4-106">Método</span><span class="sxs-lookup"><span data-stu-id="341f4-106">Method</span></span>|<span data-ttu-id="341f4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="341f4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="341f4-108">Método GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="341f4-108">GetConstantCount Method</span></span>](isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="341f4-109">Obtiene un recuento de las constantes definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="341f4-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="341f4-110">Método GetConstants</span><span class="sxs-lookup"><span data-stu-id="341f4-110">GetConstants Method</span></span>](isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="341f4-111">Obtiene las constantes locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="341f4-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="341f4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="341f4-112">Requirements</span></span>  

 <span data-ttu-id="341f4-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="341f4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="341f4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="341f4-114">See also</span></span>

- [<span data-ttu-id="341f4-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="341f4-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="341f4-116">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="341f4-116">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
