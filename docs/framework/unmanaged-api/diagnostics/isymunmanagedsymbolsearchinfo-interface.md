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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944576"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="ba548-102">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba548-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="ba548-103">Proporciona métodos que obtienen información acerca de la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ba548-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="ba548-104">Esta interfaz se obtiene mediante una llamada a `QueryInterface` en un objeto que implementa el [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="ba548-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba548-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ba548-105">Methods</span></span>  
  
|<span data-ttu-id="ba548-106">Método</span><span class="sxs-lookup"><span data-stu-id="ba548-106">Method</span></span>|<span data-ttu-id="ba548-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba548-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba548-108">GetHRESULT (método)</span><span class="sxs-lookup"><span data-stu-id="ba548-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="ba548-109">Obtiene el valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ba548-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="ba548-110">GetSearchPath (método)</span><span class="sxs-lookup"><span data-stu-id="ba548-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="ba548-111">Obtiene la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ba548-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="ba548-112">GetSearchPathLength (método)</span><span class="sxs-lookup"><span data-stu-id="ba548-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="ba548-113">Obtiene la longitud de ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ba548-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba548-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba548-114">Requirements</span></span>  
 <span data-ttu-id="ba548-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ba548-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba548-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba548-116">See also</span></span>

- [<span data-ttu-id="ba548-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="ba548-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
