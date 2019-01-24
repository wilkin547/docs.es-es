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
ms.openlocfilehash: 8f5fc951b629a3158fc2c2d6047234fb661f3741
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494904"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="7d147-102">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d147-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="7d147-103">Proporciona métodos que obtienen información acerca de la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d147-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="7d147-104">Esta interfaz se obtiene mediante una llamada a `QueryInterface` en un objeto que implementa el [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="7d147-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d147-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7d147-105">Methods</span></span>  
  
|<span data-ttu-id="7d147-106">Método</span><span class="sxs-lookup"><span data-stu-id="7d147-106">Method</span></span>|<span data-ttu-id="7d147-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d147-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d147-108">GetHRESULT (método)</span><span class="sxs-lookup"><span data-stu-id="7d147-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="7d147-109">Obtiene el valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="7d147-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="7d147-110">GetSearchPath (método)</span><span class="sxs-lookup"><span data-stu-id="7d147-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="7d147-111">Obtiene la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d147-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="7d147-112">GetSearchPathLength (método)</span><span class="sxs-lookup"><span data-stu-id="7d147-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="7d147-113">Obtiene la longitud de ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d147-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d147-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d147-114">Requirements</span></span>  
 <span data-ttu-id="7d147-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7d147-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d147-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d147-116">See also</span></span>
- [<span data-ttu-id="7d147-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="7d147-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
