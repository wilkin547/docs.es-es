---
description: 'Más información sobre: interfaces de almacén de símbolos de diagnóstico'
title: Interfaces de almacén de símbolos de diagnósticos
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
ms.openlocfilehash: 253a6e5eaa97c91332bca62f8fc47ad2945bf741
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800440"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="e1648-103">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e1648-103">Diagnostics Symbol Store Interfaces</span></span>

<span data-ttu-id="e1648-104">En este tema se describen las interfaces no administradas que permiten a un compilador generar información de símbolos para su uso por parte de un depurador.</span><span class="sxs-lookup"><span data-stu-id="e1648-104">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1648-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e1648-105">In This Section</span></span>  

 [<span data-ttu-id="e1648-106">IBindingDisplay (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-106">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="e1648-107">Proporciona métodos que muestran información de enlace actual sobre la aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="e1648-107">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="e1648-108">IDebugAutoAttach (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-108">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="e1648-109">Define la interfaz para una asociación automática del depurador invocado por el servidor.</span><span class="sxs-lookup"><span data-stu-id="e1648-109">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="e1648-110">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-110">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="e1648-111">Declara los métodos para registrar y anular el registro de un origen de notificación de conexión.</span><span class="sxs-lookup"><span data-stu-id="e1648-111">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="e1648-112">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-112">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="e1648-113">Declara los métodos para la notificación de receptor.</span><span class="sxs-lookup"><span data-stu-id="e1648-113">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="e1648-114">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="e1648-115">Declara un método para establecer los filtros de notificación.</span><span class="sxs-lookup"><span data-stu-id="e1648-115">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="e1648-116">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-116">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="e1648-117">Proporciona información para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="e1648-117">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="e1648-118">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-118">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="e1648-119">Esta interfaz es el complemento de lectura de la [interfaz ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e1648-119">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="e1648-120">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-120">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="e1648-121">Permite la definición de información de método asincrónico opcional por símbolo de método.</span><span class="sxs-lookup"><span data-stu-id="e1648-121">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="e1648-122">Debe usar con un método abierto (es decir, entre llamadas al [método openmethod (](isymunmanagedwriter-openmethod-method.md)y al [método CloseMethod (](isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="e1648-122">Must use with an opened method (that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="e1648-123">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-123">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="e1648-124">Representa un enlazador de símbolos para código no administrado.</span><span class="sxs-lookup"><span data-stu-id="e1648-124">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="e1648-125">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-125">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="e1648-126">Representa un enlazador de símbolos para código no administrado y extiende la `ISymUnmanagedBinder` interfaz.</span><span class="sxs-lookup"><span data-stu-id="e1648-126">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="e1648-127">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-127">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="e1648-128">Representa un enlazador de símbolos para código no administrado y extiende la `ISymUnmanagedBinder` interfaz.</span><span class="sxs-lookup"><span data-stu-id="e1648-128">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="e1648-129">ISymUnmanagedConstant (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-129">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="e1648-130">Proporciona acceso a las constantes no administradas.</span><span class="sxs-lookup"><span data-stu-id="e1648-130">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="e1648-131">ISymUnmanagedDispose (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-131">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="e1648-132">Desecha los recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e1648-132">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="e1648-133">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-133">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="e1648-134">Representa un documento al que hace referencia un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e1648-134">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="e1648-135">ISymUnmanagedDocumentWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-135">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="e1648-136">Proporciona métodos para escribir en un documento al que hace referencia un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e1648-136">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="e1648-137">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-137">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="e1648-138">Proporciona métodos para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="e1648-138">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="e1648-139">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-139">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="e1648-140">Representa un método dentro del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e1648-140">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="e1648-141">ISymUnmanagedNamespace (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-141">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="e1648-142">Representa un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e1648-142">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="e1648-143">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-143">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="e1648-144">Representa un lector de símbolos que proporciona acceso a los documentos, métodos y variables de un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e1648-144">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="e1648-145">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-145">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="e1648-146">Obtiene un método del lector de símbolos dado un token de método y un número de versión de edición y copia.</span><span class="sxs-lookup"><span data-stu-id="e1648-146">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="e1648-147">ISymUnmanagedReaderSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-147">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="e1648-148">Proporciona métodos que obtienen información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e1648-148">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="e1648-149">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-149">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="e1648-150">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="e1648-150">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="e1648-151">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-151">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="e1648-152">Representa un ámbito léxico dentro de un método y extiende la `ISymUnmanagedScope` interfaz con métodos que obtienen información sobre las constantes definidas dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="e1648-152">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="e1648-153">ISymUnmanagedSourceServerModule (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-153">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="e1648-154">Proporciona datos del servidor de origen para un módulo.</span><span class="sxs-lookup"><span data-stu-id="e1648-154">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="e1648-155">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-155">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="e1648-156">Proporciona métodos que obtienen información sobre la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e1648-156">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="e1648-157">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-157">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="e1648-158">Representa una variable, como un parámetro, una variable local o un campo.</span><span class="sxs-lookup"><span data-stu-id="e1648-158">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="e1648-159">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-159">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="e1648-160">Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.</span><span class="sxs-lookup"><span data-stu-id="e1648-160">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="e1648-161">ISymUnmanagedWriter2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-161">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="e1648-162">Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.</span><span class="sxs-lookup"><span data-stu-id="e1648-162">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="e1648-163">Extiende la `ISymUnmanagedWriter` interfaz.</span><span class="sxs-lookup"><span data-stu-id="e1648-163">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="e1648-164">ISymUnmanagedWriter3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-164">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="e1648-165">Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.</span><span class="sxs-lookup"><span data-stu-id="e1648-165">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="e1648-166">Extiende la `ISymUnmanagedWriter` interfaz.</span><span class="sxs-lookup"><span data-stu-id="e1648-166">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="e1648-167">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-167">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="e1648-168">Interfaz Isymunmanagedwriter4 (.</span><span class="sxs-lookup"><span data-stu-id="e1648-168">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="e1648-169">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1648-169">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="e1648-170">Interfaz ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="e1648-170">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e1648-171">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e1648-171">Related Sections</span></span>  

 [<span data-ttu-id="e1648-172">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e1648-172">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="e1648-173">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e1648-173">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="e1648-174">Depuración</span><span class="sxs-lookup"><span data-stu-id="e1648-174">Debugging</span></span>](../debugging/index.md)
