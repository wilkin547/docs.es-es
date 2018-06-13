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
ms.openlocfilehash: 7bbdc4b1f15c8dbb154ed7b967bb21c61d11782a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425557"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="86ba9-102">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86ba9-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="86ba9-103">Representa un enlazador de símbolos de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="86ba9-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="86ba9-104">Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="86ba9-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86ba9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="86ba9-105">Methods</span></span>  
  
|<span data-ttu-id="86ba9-106">Método</span><span class="sxs-lookup"><span data-stu-id="86ba9-106">Method</span></span>|<span data-ttu-id="86ba9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="86ba9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86ba9-108">GetReaderForFile (método)</span><span class="sxs-lookup"><span data-stu-id="86ba9-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="86ba9-109">A partir de una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) estructura que va a leer los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="86ba9-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="86ba9-110">GetReaderFromStream (método)</span><span class="sxs-lookup"><span data-stu-id="86ba9-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="86ba9-111">A partir de una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) símbolos estructura que va a leer la depuración desde el almacén de símbolos especificado.</span><span class="sxs-lookup"><span data-stu-id="86ba9-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86ba9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86ba9-112">Requirements</span></span>  
 <span data-ttu-id="86ba9-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="86ba9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ba9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="86ba9-114">See Also</span></span>  
 [<span data-ttu-id="86ba9-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="86ba9-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="86ba9-116">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86ba9-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="86ba9-117">ISymUnmanagedBinder3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86ba9-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
