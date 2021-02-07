---
description: 'Más información acerca de: interfaz Isymunmanagedbinder3 ('
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
ms.openlocfilehash: 6d2172fb119076cea6d0f912fb3f403d36856599
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689838"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="341e1-103">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="341e1-103">ISymUnmanagedBinder3 Interface</span></span>

<span data-ttu-id="341e1-104">Extiende la interfaz de enlazador de símbolos.</span><span class="sxs-lookup"><span data-stu-id="341e1-104">Extends the symbol binder interface.</span></span> <span data-ttu-id="341e1-105">Obtenga esta interfaz llamando a `QueryInterface` en un objeto que implementa la `ISymUnmanagedBinder` interfaz.</span><span class="sxs-lookup"><span data-stu-id="341e1-105">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="341e1-106">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="341e1-106">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="341e1-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="341e1-107">Methods</span></span>  
  
|<span data-ttu-id="341e1-108">Método</span><span class="sxs-lookup"><span data-stu-id="341e1-108">Method</span></span>|<span data-ttu-id="341e1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="341e1-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="341e1-110">Método GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="341e1-110">GetReaderFromCallback Method</span></span>](isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="341e1-111">Permite al usuario implementar o proporcionar a través `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` de la devolución de llamada o para obtener la información del directorio de depuración de la memoria.</span><span class="sxs-lookup"><span data-stu-id="341e1-111">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="341e1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="341e1-112">Requirements</span></span>  

 <span data-ttu-id="341e1-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="341e1-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="341e1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="341e1-114">See also</span></span>

- [<span data-ttu-id="341e1-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="341e1-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="341e1-116">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="341e1-116">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="341e1-117">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="341e1-117">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
