---
title: ISymUnmanagedReader (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e8daea11292cb37deb8e956e6a666c14579fbfa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="28091-102">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28091-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="28091-103">Representa un lector de símbolos que proporciona acceso a documentos, métodos y variables del sistema en un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="28091-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28091-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="28091-104">Methods</span></span>  
  
|<span data-ttu-id="28091-105">Método</span><span class="sxs-lookup"><span data-stu-id="28091-105">Method</span></span>|<span data-ttu-id="28091-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="28091-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28091-107">GetDocument (método)</span><span class="sxs-lookup"><span data-stu-id="28091-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="28091-108">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="28091-108">Finds a document.</span></span>|  
|[<span data-ttu-id="28091-109">GetDocuments (método)</span><span class="sxs-lookup"><span data-stu-id="28091-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="28091-110">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="28091-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="28091-111">GetDocumentVersion (método)</span><span class="sxs-lookup"><span data-stu-id="28091-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="28091-112">Obtiene la versión especificada del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="28091-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="28091-113">GetGlobalVariables (método)</span><span class="sxs-lookup"><span data-stu-id="28091-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="28091-114">Devuelve todas las variables globales.</span><span class="sxs-lookup"><span data-stu-id="28091-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="28091-115">GetMethod (método)</span><span class="sxs-lookup"><span data-stu-id="28091-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="28091-116">Obtiene un método del lector de símbolos, dado un token de método.</span><span class="sxs-lookup"><span data-stu-id="28091-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="28091-117">GetMethodByVersion (método)</span><span class="sxs-lookup"><span data-stu-id="28091-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="28091-118">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de editar y copiar.</span><span class="sxs-lookup"><span data-stu-id="28091-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="28091-119">GetMethodFromDocumentPosition (método)</span><span class="sxs-lookup"><span data-stu-id="28091-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="28091-120">Devuelve el método que contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="28091-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="28091-121">GetMethodsFromDocumentPosition (método)</span><span class="sxs-lookup"><span data-stu-id="28091-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="28091-122">Devuelve una matriz de los métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="28091-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="28091-123">GetMethodVersion (método)</span><span class="sxs-lookup"><span data-stu-id="28091-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="28091-124">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="28091-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="28091-125">GetNamespaces (método)</span><span class="sxs-lookup"><span data-stu-id="28091-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="28091-126">Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="28091-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="28091-127">GetSymAttribute (método)</span><span class="sxs-lookup"><span data-stu-id="28091-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="28091-128">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="28091-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="28091-129">GetSymbolStoreFileName (método)</span><span class="sxs-lookup"><span data-stu-id="28091-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="28091-130">Proporciona el nombre de archivo en disco del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="28091-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="28091-131">GetUserEntryPoint (método)</span><span class="sxs-lookup"><span data-stu-id="28091-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="28091-132">Devuelve el método que se especificó como el punto de entrada de usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="28091-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="28091-133">GetVariables (método)</span><span class="sxs-lookup"><span data-stu-id="28091-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="28091-134">Devuelve una variable no local, según su elemento primario y el nombre.</span><span class="sxs-lookup"><span data-stu-id="28091-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="28091-135">Initialize (método)</span><span class="sxs-lookup"><span data-stu-id="28091-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="28091-136">Inicializa el lector de símbolos con la interfaz de importador de metadatos que este lector estarán asociado a, junto con el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="28091-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="28091-137">ReplaceSymbolStore (método)</span><span class="sxs-lookup"><span data-stu-id="28091-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="28091-138">Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="28091-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="28091-139">UpdateSymbolStore (método)</span><span class="sxs-lookup"><span data-stu-id="28091-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="28091-140">Actualiza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="28091-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28091-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28091-141">Requirements</span></span>  
 <span data-ttu-id="28091-142">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="28091-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28091-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="28091-143">See Also</span></span>  
 [<span data-ttu-id="28091-144">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="28091-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="28091-145">ISymUnmanagedReader2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28091-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
