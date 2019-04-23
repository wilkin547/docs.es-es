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
ms.openlocfilehash: 38de9fa878db18222d2666ba86420ca856e4b121
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199120"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="67ae3-102">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="67ae3-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="67ae3-103">Representa un enlazador de símbolos de código no administrado y extiende el [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="67ae3-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="67ae3-104">Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="67ae3-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67ae3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="67ae3-105">Methods</span></span>  
  
|<span data-ttu-id="67ae3-106">Método</span><span class="sxs-lookup"><span data-stu-id="67ae3-106">Method</span></span>|<span data-ttu-id="67ae3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="67ae3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67ae3-108">GetReaderForFile2 (método)</span><span class="sxs-lookup"><span data-stu-id="67ae3-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="67ae3-109">Dada una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaz que va a leer los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="67ae3-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="67ae3-110">Proporciona una búsqueda más amplia que la [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="67ae3-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67ae3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67ae3-111">Requirements</span></span>  
 <span data-ttu-id="67ae3-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="67ae3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ae3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="67ae3-113">See also</span></span>

- [<span data-ttu-id="67ae3-114">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="67ae3-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="67ae3-115">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67ae3-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="67ae3-116">ISymUnmanagedBinder3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67ae3-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
