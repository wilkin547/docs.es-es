---
title: ISymUnmanagedReader (Interfaz)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0782533f773b69eeeb0b89175e5b22c61e822ed9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986367"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="ffbdc-102">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="ffbdc-103">Representa un lector de símbolos que proporciona acceso a documentos, métodos y variables dentro de un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffbdc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ffbdc-104">Methods</span></span>  
  
|<span data-ttu-id="ffbdc-105">Método</span><span class="sxs-lookup"><span data-stu-id="ffbdc-105">Method</span></span>|<span data-ttu-id="ffbdc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffbdc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffbdc-107">GetDocument (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="ffbdc-108">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-108">Finds a document.</span></span>|  
|[<span data-ttu-id="ffbdc-109">GetDocuments (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="ffbdc-110">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="ffbdc-111">GetDocumentVersion (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="ffbdc-112">Obtiene la versión especificada del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="ffbdc-113">GetGlobalVariables (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="ffbdc-114">Devuelve todas las variables globales.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="ffbdc-115">GetMethod (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="ffbdc-116">Obtiene un método del lector de símbolos, dado un token de método.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="ffbdc-117">GetMethodByVersion (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="ffbdc-118">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de editar y copiar.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="ffbdc-119">GetMethodFromDocumentPosition (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="ffbdc-120">Devuelve el método que contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="ffbdc-121">GetMethodsFromDocumentPosition (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="ffbdc-122">Devuelve una matriz de métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="ffbdc-123">GetMethodVersion (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="ffbdc-124">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="ffbdc-125">GetNamespaces (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="ffbdc-126">Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="ffbdc-127">GetSymAttribute (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="ffbdc-128">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="ffbdc-129">GetSymbolStoreFileName (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="ffbdc-130">Proporciona el nombre de archivo en el disco del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="ffbdc-131">GetUserEntryPoint (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="ffbdc-132">Devuelve el método que se especificó como el punto de entrada de usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="ffbdc-133">GetVariables (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="ffbdc-134">Devuelve una variable no local, dada su elemento primario y su nombre.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="ffbdc-135">Initialize (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="ffbdc-136">Inicializa el lector de símbolos con la interfaz de importador de metadatos que se asociará con, junto con el nombre de archivo del módulo de este lector.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="ffbdc-137">ReplaceSymbolStore (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="ffbdc-138">Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="ffbdc-139">UpdateSymbolStore (método)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="ffbdc-140">Actualiza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="ffbdc-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffbdc-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ffbdc-141">Requirements</span></span>  
 <span data-ttu-id="ffbdc-142">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ffbdc-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffbdc-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffbdc-143">See also</span></span>

- [<span data-ttu-id="ffbdc-144">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="ffbdc-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ffbdc-145">ISymUnmanagedReader2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffbdc-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
