---
title: ISymUnmanagedBinder2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9fbb8364fb967e739eb9807b26cbc65f0ebec1d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944190"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="36b9a-102">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36b9a-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="36b9a-103">Representa un enlazador de símbolos para código no administrado y extiende la interfaz [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="36b9a-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="36b9a-104">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="36b9a-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36b9a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="36b9a-105">Methods</span></span>  
  
|<span data-ttu-id="36b9a-106">Método</span><span class="sxs-lookup"><span data-stu-id="36b9a-106">Method</span></span>|<span data-ttu-id="36b9a-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="36b9a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36b9a-108">GetReaderForFile2 (método)</span><span class="sxs-lookup"><span data-stu-id="36b9a-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="36b9a-109">Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="36b9a-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="36b9a-110">Proporciona una búsqueda más extensa que el método [ISymUnmanagedBinder:: GetReaderForFile (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="36b9a-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36b9a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36b9a-111">Requirements</span></span>  
 <span data-ttu-id="36b9a-112">**Encabezado**: CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="36b9a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b9a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="36b9a-113">See also</span></span>

- [<span data-ttu-id="36b9a-114">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="36b9a-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="36b9a-115">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36b9a-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="36b9a-116">ISymUnmanagedBinder3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36b9a-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
