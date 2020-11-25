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
ms.openlocfilehash: 0cb0b91f2dca8203c37599400b3b61f84eb7d282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727320"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="a5afe-102">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5afe-102">ISymUnmanagedBinder3 Interface</span></span>

<span data-ttu-id="a5afe-103">Extiende la interfaz de enlazador de símbolos.</span><span class="sxs-lookup"><span data-stu-id="a5afe-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="a5afe-104">Obtenga esta interfaz llamando a `QueryInterface` en un objeto que implementa la `ISymUnmanagedBinder` interfaz.</span><span class="sxs-lookup"><span data-stu-id="a5afe-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a5afe-105">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="a5afe-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5afe-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="a5afe-106">Methods</span></span>  
  
|<span data-ttu-id="a5afe-107">Método</span><span class="sxs-lookup"><span data-stu-id="a5afe-107">Method</span></span>|<span data-ttu-id="a5afe-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5afe-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5afe-109">Método GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="a5afe-109">GetReaderFromCallback Method</span></span>](isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="a5afe-110">Permite al usuario implementar o proporcionar a través `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` de la devolución de llamada o para obtener la información del directorio de depuración de la memoria.</span><span class="sxs-lookup"><span data-stu-id="a5afe-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5afe-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5afe-111">Requirements</span></span>  

 <span data-ttu-id="a5afe-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a5afe-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5afe-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5afe-113">See also</span></span>

- [<span data-ttu-id="a5afe-114">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="a5afe-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="a5afe-115">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5afe-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="a5afe-116">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5afe-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
