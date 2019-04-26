---
title: ISymUnmanagedSourceServerModule (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ba81c208c4b49342c6a055e09ba898871db1851
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922140"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="8caa4-102">ISymUnmanagedSourceServerModule (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8caa4-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="8caa4-103">Proporciona datos del servidor de origen para un módulo.</span><span class="sxs-lookup"><span data-stu-id="8caa4-103">Provides source server data for a module.</span></span> <span data-ttu-id="8caa4-104">Esta interfaz se obtiene mediante una llamada a `QueryInterface` en un objeto que implementa el [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="8caa4-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8caa4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8caa4-105">Methods</span></span>  
  
|<span data-ttu-id="8caa4-106">Método</span><span class="sxs-lookup"><span data-stu-id="8caa4-106">Method</span></span>|<span data-ttu-id="8caa4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8caa4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8caa4-108">GetSourceServerData (método)</span><span class="sxs-lookup"><span data-stu-id="8caa4-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="8caa4-109">Devuelve los datos del servidor de origen para el módulo.</span><span class="sxs-lookup"><span data-stu-id="8caa4-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8caa4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8caa4-110">Requirements</span></span>  
 <span data-ttu-id="8caa4-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8caa4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8caa4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8caa4-112">See also</span></span>

- [<span data-ttu-id="8caa4-113">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="8caa4-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
