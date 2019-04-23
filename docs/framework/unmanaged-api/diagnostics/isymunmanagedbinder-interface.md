---
title: ISymUnmanagedBinder (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6d91f68ac737ce28cdbef926119bb3711bc1096
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105824"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="e3db6-102">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3db6-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="e3db6-103">Representa un enlazador de símbolos de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="e3db6-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3db6-104">Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="e3db6-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3db6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e3db6-105">Methods</span></span>  
  
|<span data-ttu-id="e3db6-106">Método</span><span class="sxs-lookup"><span data-stu-id="e3db6-106">Method</span></span>|<span data-ttu-id="e3db6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3db6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3db6-108">GetReaderForFile (método)</span><span class="sxs-lookup"><span data-stu-id="e3db6-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="e3db6-109">Dada una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) estructura que va a leer los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="e3db6-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="e3db6-110">GetReaderFromStream (método)</span><span class="sxs-lookup"><span data-stu-id="e3db6-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="e3db6-111">Dada una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) estructura que leerá la depuración de símbolos desde el almacén de símbolos especificado.</span><span class="sxs-lookup"><span data-stu-id="e3db6-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3db6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3db6-112">Requirements</span></span>  
 <span data-ttu-id="e3db6-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e3db6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3db6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3db6-114">See also</span></span>

- [<span data-ttu-id="e3db6-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e3db6-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e3db6-116">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3db6-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="e3db6-117">ISymUnmanagedBinder3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3db6-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
