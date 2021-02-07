---
description: 'Más información acerca de: ISymUnmanagedReader (interfaz)'
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
ms.openlocfilehash: bad4fdbac3bf6f03fa0db79ce54a5b0ca897028f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763805"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="33776-103">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33776-103">ISymUnmanagedReader Interface</span></span>

<span data-ttu-id="33776-104">Representa un lector de símbolos que proporciona acceso a los documentos, métodos y variables de un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="33776-104">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33776-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="33776-105">Methods</span></span>  
  
|<span data-ttu-id="33776-106">Método</span><span class="sxs-lookup"><span data-stu-id="33776-106">Method</span></span>|<span data-ttu-id="33776-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="33776-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33776-108">Método GetDocument</span><span class="sxs-lookup"><span data-stu-id="33776-108">GetDocument Method</span></span>](isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="33776-109">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="33776-109">Finds a document.</span></span>|  
|[<span data-ttu-id="33776-110">Método GetDocuments</span><span class="sxs-lookup"><span data-stu-id="33776-110">GetDocuments Method</span></span>](isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="33776-111">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="33776-111">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="33776-112">Método GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="33776-112">GetDocumentVersion Method</span></span>](isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="33776-113">Obtiene la versión especificada del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="33776-113">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="33776-114">Método GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="33776-114">GetGlobalVariables Method</span></span>](isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="33776-115">Devuelve todas las variables globales.</span><span class="sxs-lookup"><span data-stu-id="33776-115">Returns all global variables.</span></span>|  
|[<span data-ttu-id="33776-116">Método GetMethod</span><span class="sxs-lookup"><span data-stu-id="33776-116">GetMethod Method</span></span>](isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="33776-117">Obtiene un método del lector de símbolos, dado un token de método.</span><span class="sxs-lookup"><span data-stu-id="33776-117">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="33776-118">Método GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="33776-118">GetMethodByVersion Method</span></span>](isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="33776-119">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y copia.</span><span class="sxs-lookup"><span data-stu-id="33776-119">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="33776-120">Método GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="33776-120">GetMethodFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="33776-121">Devuelve el método que contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="33776-121">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="33776-122">Método GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="33776-122">GetMethodsFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="33776-123">Devuelve una matriz de métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="33776-123">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="33776-124">Método GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="33776-124">GetMethodVersion Method</span></span>](isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="33776-125">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="33776-125">Gets the method version.</span></span>|  
|[<span data-ttu-id="33776-126">Método GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="33776-126">GetNamespaces Method</span></span>](isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="33776-127">Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="33776-127">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="33776-128">Método GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="33776-128">GetSymAttribute Method</span></span>](isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="33776-129">Obtiene un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="33776-129">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="33776-130">Método GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="33776-130">GetSymbolStoreFileName Method</span></span>](isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="33776-131">Proporciona el nombre de archivo en disco del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="33776-131">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="33776-132">Método GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="33776-132">GetUserEntryPoint Method</span></span>](isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="33776-133">Devuelve el método que se especificó como punto de entrada del usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="33776-133">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="33776-134">Método GetVariables</span><span class="sxs-lookup"><span data-stu-id="33776-134">GetVariables Method</span></span>](isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="33776-135">Devuelve una variable no local, dados su nombre y elemento primario.</span><span class="sxs-lookup"><span data-stu-id="33776-135">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="33776-136">Método Initialize</span><span class="sxs-lookup"><span data-stu-id="33776-136">Initialize Method</span></span>](isymunmanagedreader-initialize-method.md)|<span data-ttu-id="33776-137">Inicializa el lector de símbolos con la interfaz de importador de metadatos a la que se asociará este lector, junto con el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="33776-137">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="33776-138">Método ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="33776-138">ReplaceSymbolStore Method</span></span>](isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="33776-139">Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="33776-139">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="33776-140">Método UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="33776-140">UpdateSymbolStore Method</span></span>](isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="33776-141">Actualiza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="33776-141">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33776-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33776-142">Requirements</span></span>  

 <span data-ttu-id="33776-143">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="33776-143">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33776-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="33776-144">See also</span></span>

- [<span data-ttu-id="33776-145">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="33776-145">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="33776-146">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33776-146">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
