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
ms.openlocfilehash: 886ba693183a6b99eb03635e95a9661d105de40e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610865"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="0b1ee-102">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b1ee-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="0b1ee-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="0b1ee-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="0b1ee-104">Esta interfaz extiende la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) con métodos que obtienen información sobre las constantes definidas dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="0b1ee-104">This interface extends the [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b1ee-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0b1ee-105">Methods</span></span>  
  
|<span data-ttu-id="0b1ee-106">Método</span><span class="sxs-lookup"><span data-stu-id="0b1ee-106">Method</span></span>|<span data-ttu-id="0b1ee-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b1ee-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b1ee-108">Método GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="0b1ee-108">GetConstantCount Method</span></span>](isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="0b1ee-109">Obtiene un recuento de las constantes definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="0b1ee-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="0b1ee-110">Método GetConstants</span><span class="sxs-lookup"><span data-stu-id="0b1ee-110">GetConstants Method</span></span>](isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="0b1ee-111">Obtiene las constantes locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="0b1ee-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b1ee-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b1ee-112">Requirements</span></span>  
 <span data-ttu-id="0b1ee-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0b1ee-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b1ee-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0b1ee-114">See also</span></span>

- [<span data-ttu-id="0b1ee-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="0b1ee-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="0b1ee-116">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b1ee-116">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
