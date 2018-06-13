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
ms.openlocfilehash: 5dce9653d3fef534ac6567e36a4c8213e13ab231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429174"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="3d4d6-102">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d4d6-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="3d4d6-103">Proporciona métodos que obtienen información sobre la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3d4d6-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="3d4d6-104">Obtener esta interfaz mediante una llamada a `QueryInterface` en un objeto que implementa el [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="3d4d6-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d4d6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3d4d6-105">Methods</span></span>  
  
|<span data-ttu-id="3d4d6-106">Método</span><span class="sxs-lookup"><span data-stu-id="3d4d6-106">Method</span></span>|<span data-ttu-id="3d4d6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d4d6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d4d6-108">GetHRESULT (método)</span><span class="sxs-lookup"><span data-stu-id="3d4d6-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="3d4d6-109">Obtiene el valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="3d4d6-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="3d4d6-110">GetSearchPath (método)</span><span class="sxs-lookup"><span data-stu-id="3d4d6-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="3d4d6-111">Obtiene la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3d4d6-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="3d4d6-112">GetSearchPathLength (método)</span><span class="sxs-lookup"><span data-stu-id="3d4d6-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="3d4d6-113">Obtiene la longitud de ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3d4d6-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d4d6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d4d6-114">Requirements</span></span>  
 <span data-ttu-id="3d4d6-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3d4d6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4d6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d4d6-116">See Also</span></span>  
 [<span data-ttu-id="3d4d6-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="3d4d6-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
