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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfd8e8fc419809a3a490639ada1c533f286fe8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940002"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="cacec-102">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cacec-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="cacec-103">Extiende la interfaz de enlazador de símbolos.</span><span class="sxs-lookup"><span data-stu-id="cacec-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="cacec-104">Esta interfaz se obtiene mediante una llamada a `QueryInterface` en un objeto que implementa el `ISymUnmanagedBinder` interfaz.</span><span class="sxs-lookup"><span data-stu-id="cacec-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cacec-105">Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="cacec-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cacec-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="cacec-106">Methods</span></span>  
  
|<span data-ttu-id="cacec-107">Método</span><span class="sxs-lookup"><span data-stu-id="cacec-107">Method</span></span>|<span data-ttu-id="cacec-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cacec-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cacec-109">GetReaderFromCallback (método)</span><span class="sxs-lookup"><span data-stu-id="cacec-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="cacec-110">Permite al usuario implementar o proporcionar a través de la devolución de llamada, ya sea un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` para obtener la información de directorio de depuración de la memoria</span><span class="sxs-lookup"><span data-stu-id="cacec-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cacec-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cacec-111">Requirements</span></span>  
 <span data-ttu-id="cacec-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cacec-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cacec-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cacec-113">See also</span></span>

- [<span data-ttu-id="cacec-114">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="cacec-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="cacec-115">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cacec-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="cacec-116">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cacec-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
