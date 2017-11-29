---
title: ISymUnmanagedSymbolSearchInfo (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo
helpviewer_keywords: ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 967511238dceb752ab30ce10dcaba8b65f4dd9fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="cb965-102">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb965-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="cb965-103">Proporciona métodos que obtienen información sobre la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cb965-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="cb965-104">Obtener esta interfaz mediante una llamada a `QueryInterface` en un objeto que implementa el [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="cb965-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb965-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cb965-105">Methods</span></span>  
  
|<span data-ttu-id="cb965-106">Método</span><span class="sxs-lookup"><span data-stu-id="cb965-106">Method</span></span>|<span data-ttu-id="cb965-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb965-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb965-108">GetHRESULT (método)</span><span class="sxs-lookup"><span data-stu-id="cb965-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="cb965-109">Obtiene el valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="cb965-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="cb965-110">GetSearchPath (método)</span><span class="sxs-lookup"><span data-stu-id="cb965-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="cb965-111">Obtiene la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cb965-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="cb965-112">GetSearchPathLength (método)</span><span class="sxs-lookup"><span data-stu-id="cb965-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="cb965-113">Obtiene la longitud de ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cb965-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb965-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb965-114">Requirements</span></span>  
 <span data-ttu-id="cb965-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cb965-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb965-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb965-116">See Also</span></span>  
 [<span data-ttu-id="cb965-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="cb965-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
