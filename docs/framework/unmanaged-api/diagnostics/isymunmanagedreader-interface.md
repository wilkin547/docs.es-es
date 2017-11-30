---
title: ISymUnmanagedReader (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader
helpviewer_keywords: ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56e0012ae1412c0fb5b434d3b4c0221831296c60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="7d42b-102">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d42b-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="7d42b-103">Representa un lector de símbolos que proporciona acceso a documentos, métodos y variables del sistema en un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7d42b-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d42b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7d42b-104">Methods</span></span>  
  
|<span data-ttu-id="7d42b-105">Método</span><span class="sxs-lookup"><span data-stu-id="7d42b-105">Method</span></span>|<span data-ttu-id="7d42b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d42b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d42b-107">GetDocument (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="7d42b-108">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="7d42b-108">Finds a document.</span></span>|  
|[<span data-ttu-id="7d42b-109">GetDocuments (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="7d42b-110">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7d42b-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="7d42b-111">GetDocumentVersion (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="7d42b-112">Obtiene la versión especificada del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="7d42b-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="7d42b-113">GetGlobalVariables (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="7d42b-114">Devuelve todas las variables globales.</span><span class="sxs-lookup"><span data-stu-id="7d42b-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="7d42b-115">GetMethod (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="7d42b-116">Obtiene un método del lector de símbolos, dado un token de método.</span><span class="sxs-lookup"><span data-stu-id="7d42b-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="7d42b-117">GetMethodByVersion (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="7d42b-118">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de editar y copiar.</span><span class="sxs-lookup"><span data-stu-id="7d42b-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="7d42b-119">GetMethodFromDocumentPosition (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="7d42b-120">Devuelve el método que contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="7d42b-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="7d42b-121">GetMethodsFromDocumentPosition (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="7d42b-122">Devuelve una matriz de los métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="7d42b-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="7d42b-123">GetMethodVersion (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="7d42b-124">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="7d42b-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="7d42b-125">GetNamespaces (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="7d42b-126">Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7d42b-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="7d42b-127">GetSymAttribute (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="7d42b-128">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="7d42b-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="7d42b-129">GetSymbolStoreFileName (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="7d42b-130">Proporciona el nombre de archivo en disco del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7d42b-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="7d42b-131">GetUserEntryPoint (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="7d42b-132">Devuelve el método que se especificó como el punto de entrada de usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="7d42b-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="7d42b-133">GetVariables (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="7d42b-134">Devuelve una variable no local, según su elemento primario y el nombre.</span><span class="sxs-lookup"><span data-stu-id="7d42b-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="7d42b-135">Initialize (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="7d42b-136">Inicializa el lector de símbolos con la interfaz de importador de metadatos que este lector estarán asociado a, junto con el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="7d42b-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="7d42b-137">ReplaceSymbolStore (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="7d42b-138">Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="7d42b-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="7d42b-139">UpdateSymbolStore (método)</span><span class="sxs-lookup"><span data-stu-id="7d42b-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="7d42b-140">Actualiza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="7d42b-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d42b-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d42b-141">Requirements</span></span>  
 <span data-ttu-id="7d42b-142">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7d42b-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d42b-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d42b-143">See Also</span></span>  
 [<span data-ttu-id="7d42b-144">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="7d42b-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="7d42b-145">ISymUnmanagedReader2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d42b-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
