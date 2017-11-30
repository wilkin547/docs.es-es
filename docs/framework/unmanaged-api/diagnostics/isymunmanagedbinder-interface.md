---
title: ISymUnmanagedBinder (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder
helpviewer_keywords: ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5061ce28c4a09f445267c99420bf1942d99076bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="8b3ad-102">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b3ad-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="8b3ad-103">Representa un enlazador de símbolos de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="8b3ad-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b3ad-104">Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="8b3ad-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b3ad-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8b3ad-105">Methods</span></span>  
  
|<span data-ttu-id="8b3ad-106">Método</span><span class="sxs-lookup"><span data-stu-id="8b3ad-106">Method</span></span>|<span data-ttu-id="8b3ad-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b3ad-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b3ad-108">GetReaderForFile (método)</span><span class="sxs-lookup"><span data-stu-id="8b3ad-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="8b3ad-109">A partir de una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> estructura que va a leer los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="8b3ad-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="8b3ad-110">GetReaderFromStream (método)</span><span class="sxs-lookup"><span data-stu-id="8b3ad-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="8b3ad-111">A partir de una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve el valor correcto <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> símbolos estructura que va a leer la depuración desde el almacén de símbolos especificado.</span><span class="sxs-lookup"><span data-stu-id="8b3ad-111">Given a metadata interface and a stream that contains the symbol store, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b3ad-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b3ad-112">Requirements</span></span>  
 <span data-ttu-id="8b3ad-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8b3ad-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b3ad-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b3ad-114">See Also</span></span>  
 [<span data-ttu-id="8b3ad-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="8b3ad-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="8b3ad-116">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b3ad-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="8b3ad-117">ISymUnmanagedBinder3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b3ad-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
