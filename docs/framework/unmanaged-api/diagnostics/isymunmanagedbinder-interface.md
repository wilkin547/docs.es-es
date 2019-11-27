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
ms.openlocfilehash: f23df98abc5355f0b25d7253b5f2ae808b3446a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449372"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="99f5b-102">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99f5b-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="99f5b-103">Representa un enlazador de símbolos para código no administrado.</span><span class="sxs-lookup"><span data-stu-id="99f5b-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="99f5b-104">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="99f5b-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99f5b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="99f5b-105">Methods</span></span>  
  
|<span data-ttu-id="99f5b-106">Método</span><span class="sxs-lookup"><span data-stu-id="99f5b-106">Method</span></span>|<span data-ttu-id="99f5b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="99f5b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99f5b-108">GetReaderForFile (método)</span><span class="sxs-lookup"><span data-stu-id="99f5b-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="99f5b-109">Dada una interfaz de metadatos y un nombre de archivo, devuelve la estructura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="99f5b-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="99f5b-110">GetReaderFromStream (método)</span><span class="sxs-lookup"><span data-stu-id="99f5b-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="99f5b-111">Dada una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve la estructura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración del almacén de símbolos determinado.</span><span class="sxs-lookup"><span data-stu-id="99f5b-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99f5b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99f5b-112">Requirements</span></span>  
 <span data-ttu-id="99f5b-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="99f5b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f5b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="99f5b-114">See also</span></span>

- [<span data-ttu-id="99f5b-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="99f5b-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="99f5b-116">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99f5b-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="99f5b-117">ISymUnmanagedBinder3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99f5b-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
