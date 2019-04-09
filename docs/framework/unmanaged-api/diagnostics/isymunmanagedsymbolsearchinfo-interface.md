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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d573264bb7a3cac02dd41afacaa2bc4a6f9e6dcd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207557"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="4e259-102">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e259-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="4e259-103">Proporciona métodos que obtienen información acerca de la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e259-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="4e259-104">Esta interfaz se obtiene mediante una llamada a `QueryInterface` en un objeto que implementa el [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="4e259-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e259-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4e259-105">Methods</span></span>  
  
|<span data-ttu-id="4e259-106">Método</span><span class="sxs-lookup"><span data-stu-id="4e259-106">Method</span></span>|<span data-ttu-id="4e259-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e259-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e259-108">Método GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="4e259-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="4e259-109">Obtiene el valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="4e259-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="4e259-110">Método GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="4e259-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="4e259-111">Obtiene la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e259-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="4e259-112">Método GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="4e259-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="4e259-113">Obtiene la longitud de ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e259-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e259-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e259-114">Requirements</span></span>  
 <span data-ttu-id="4e259-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4e259-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e259-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e259-116">See also</span></span>

- [<span data-ttu-id="4e259-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="4e259-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
