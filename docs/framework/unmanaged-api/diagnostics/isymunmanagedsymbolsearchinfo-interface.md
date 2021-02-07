---
description: 'Más información acerca de: interfaz ISymUnmanagedSymbolSearchInfo'
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
ms.openlocfilehash: 2f2ab198d2c54a9fcc5fa2e24b9196a38c583f81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762986"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="a36c1-103">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a36c1-103">ISymUnmanagedSymbolSearchInfo Interface</span></span>

<span data-ttu-id="a36c1-104">Proporciona métodos que obtienen información sobre la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a36c1-104">Provides methods that get information about the search path.</span></span> <span data-ttu-id="a36c1-105">Obtenga esta interfaz mediante una llamada a `QueryInterface` en un objeto que implementa la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a36c1-105">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a36c1-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="a36c1-106">Methods</span></span>  
  
|<span data-ttu-id="a36c1-107">Método</span><span class="sxs-lookup"><span data-stu-id="a36c1-107">Method</span></span>|<span data-ttu-id="a36c1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a36c1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a36c1-109">Método GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="a36c1-109">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="a36c1-110">Obtiene el HRESULT.</span><span class="sxs-lookup"><span data-stu-id="a36c1-110">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="a36c1-111">Método GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="a36c1-111">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="a36c1-112">Obtiene la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a36c1-112">Gets the search path.</span></span>|  
|[<span data-ttu-id="a36c1-113">Método GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="a36c1-113">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="a36c1-114">Obtiene la longitud de la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a36c1-114">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a36c1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a36c1-115">Requirements</span></span>  

 <span data-ttu-id="a36c1-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a36c1-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a36c1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a36c1-117">See also</span></span>

- [<span data-ttu-id="a36c1-118">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="a36c1-118">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
