---
title: ISymUnmanagedBinder3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: e4a415b21e3980e7603319d7acbb3831462fac9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449295"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="208a4-102">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="208a4-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="208a4-103">Extiende la interfaz de enlazador de símbolos.</span><span class="sxs-lookup"><span data-stu-id="208a4-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="208a4-104">Obtenga esta interfaz llamando a `QueryInterface` en un objeto que implementa la interfaz `ISymUnmanagedBinder`.</span><span class="sxs-lookup"><span data-stu-id="208a4-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="208a4-105">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="208a4-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="208a4-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="208a4-106">Methods</span></span>  
  
|<span data-ttu-id="208a4-107">Método</span><span class="sxs-lookup"><span data-stu-id="208a4-107">Method</span></span>|<span data-ttu-id="208a4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="208a4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="208a4-109">GetReaderFromCallback (método)</span><span class="sxs-lookup"><span data-stu-id="208a4-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="208a4-110">Permite al usuario implementar o proporcionar a través de una devolución de llamada, o bien un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` para obtener la información del directorio de depuración de la memoria.</span><span class="sxs-lookup"><span data-stu-id="208a4-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="208a4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="208a4-111">Requirements</span></span>  
 <span data-ttu-id="208a4-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="208a4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208a4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="208a4-113">See also</span></span>

- [<span data-ttu-id="208a4-114">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="208a4-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="208a4-115">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="208a4-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="208a4-116">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="208a4-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
