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
ms.openlocfilehash: bca84fdba575ed9bfe572b9fd7a5869620962de6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675872"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="c2cce-102">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2cce-102">ISymUnmanagedReader Interface</span></span>

<span data-ttu-id="c2cce-103">Representa un lector de símbolos que proporciona acceso a los documentos, métodos y variables de un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="c2cce-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2cce-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c2cce-104">Methods</span></span>  
  
|<span data-ttu-id="c2cce-105">Método</span><span class="sxs-lookup"><span data-stu-id="c2cce-105">Method</span></span>|<span data-ttu-id="c2cce-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2cce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2cce-107">Método GetDocument</span><span class="sxs-lookup"><span data-stu-id="c2cce-107">GetDocument Method</span></span>](isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="c2cce-108">Busca un documento.</span><span class="sxs-lookup"><span data-stu-id="c2cce-108">Finds a document.</span></span>|  
|[<span data-ttu-id="c2cce-109">Método GetDocuments</span><span class="sxs-lookup"><span data-stu-id="c2cce-109">GetDocuments Method</span></span>](isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="c2cce-110">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="c2cce-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="c2cce-111">Método GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="c2cce-111">GetDocumentVersion Method</span></span>](isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="c2cce-112">Obtiene la versión especificada del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="c2cce-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="c2cce-113">Método GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="c2cce-113">GetGlobalVariables Method</span></span>](isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="c2cce-114">Devuelve todas las variables globales.</span><span class="sxs-lookup"><span data-stu-id="c2cce-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="c2cce-115">Método GetMethod</span><span class="sxs-lookup"><span data-stu-id="c2cce-115">GetMethod Method</span></span>](isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="c2cce-116">Obtiene un método del lector de símbolos, dado un token de método.</span><span class="sxs-lookup"><span data-stu-id="c2cce-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="c2cce-117">Método GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="c2cce-117">GetMethodByVersion Method</span></span>](isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="c2cce-118">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y copia.</span><span class="sxs-lookup"><span data-stu-id="c2cce-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="c2cce-119">Método GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="c2cce-119">GetMethodFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="c2cce-120">Devuelve el método que contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="c2cce-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="c2cce-121">Método GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="c2cce-121">GetMethodsFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="c2cce-122">Devuelve una matriz de métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="c2cce-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="c2cce-123">Método GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="c2cce-123">GetMethodVersion Method</span></span>](isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="c2cce-124">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="c2cce-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="c2cce-125">Método GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="c2cce-125">GetNamespaces Method</span></span>](isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="c2cce-126">Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="c2cce-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="c2cce-127">Método GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="c2cce-127">GetSymAttribute Method</span></span>](isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="c2cce-128">Obtiene un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="c2cce-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="c2cce-129">Método GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="c2cce-129">GetSymbolStoreFileName Method</span></span>](isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="c2cce-130">Proporciona el nombre de archivo en disco del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="c2cce-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="c2cce-131">Método GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="c2cce-131">GetUserEntryPoint Method</span></span>](isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="c2cce-132">Devuelve el método que se especificó como punto de entrada del usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="c2cce-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="c2cce-133">Método GetVariables</span><span class="sxs-lookup"><span data-stu-id="c2cce-133">GetVariables Method</span></span>](isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="c2cce-134">Devuelve una variable no local, dados su nombre y elemento primario.</span><span class="sxs-lookup"><span data-stu-id="c2cce-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="c2cce-135">Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="c2cce-135">Initialize Method</span></span>](isymunmanagedreader-initialize-method.md)|<span data-ttu-id="c2cce-136">Inicializa el lector de símbolos con la interfaz de importador de metadatos a la que se asociará este lector, junto con el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="c2cce-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="c2cce-137">Método ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="c2cce-137">ReplaceSymbolStore Method</span></span>](isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="c2cce-138">Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="c2cce-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="c2cce-139">Método UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="c2cce-139">UpdateSymbolStore Method</span></span>](isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="c2cce-140">Actualiza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="c2cce-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2cce-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2cce-141">Requirements</span></span>  

 <span data-ttu-id="c2cce-142">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c2cce-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2cce-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2cce-143">See also</span></span>

- [<span data-ttu-id="c2cce-144">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="c2cce-144">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c2cce-145">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2cce-145">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
