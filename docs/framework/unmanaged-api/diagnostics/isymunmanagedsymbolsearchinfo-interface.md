---
title: ISymUnmanagedSymbolSearchInfo (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: 308c501e17446719067d2dc0580d698c1770bf53
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610670"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="1c143-102">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c143-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="1c143-103">Proporciona métodos que obtienen información sobre la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1c143-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="1c143-104">Obtenga esta interfaz mediante una llamada a `QueryInterface` en un objeto que implementa la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1c143-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c143-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1c143-105">Methods</span></span>  
  
|<span data-ttu-id="1c143-106">Método</span><span class="sxs-lookup"><span data-stu-id="1c143-106">Method</span></span>|<span data-ttu-id="1c143-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c143-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c143-108">Método GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="1c143-108">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="1c143-109">Obtiene el HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1c143-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="1c143-110">Método GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="1c143-110">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="1c143-111">Obtiene la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1c143-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="1c143-112">Método GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="1c143-112">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="1c143-113">Obtiene la longitud de la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1c143-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c143-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c143-114">Requirements</span></span>  
 <span data-ttu-id="1c143-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1c143-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c143-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1c143-116">See also</span></span>

- [<span data-ttu-id="1c143-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="1c143-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
