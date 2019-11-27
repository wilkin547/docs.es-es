---
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
ms.openlocfilehash: bdb691570a9a2bf7bd2bb21af500b06c10b0bc53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448525"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="e8669-102">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e8669-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="e8669-103">En este tema se describen las interfaces no administradas que permiten a un compilador generar información de símbolos para su uso por parte de un depurador.</span><span class="sxs-lookup"><span data-stu-id="e8669-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8669-104">Esta sección</span><span class="sxs-lookup"><span data-stu-id="e8669-104">In This Section</span></span>  
 [<span data-ttu-id="e8669-105">IBindingDisplay (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="e8669-106">Proporciona métodos que muestran información de enlace actual sobre la aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="e8669-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="e8669-107">IDebugAutoAttach (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="e8669-108">Define la interfaz para una asociación automática del depurador invocado por el servidor.</span><span class="sxs-lookup"><span data-stu-id="e8669-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="e8669-109">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="e8669-110">Declara los métodos para registrar y anular el registro de un origen de notificación de conexión.</span><span class="sxs-lookup"><span data-stu-id="e8669-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="e8669-111">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="e8669-112">Declara los métodos para la notificación de receptor.</span><span class="sxs-lookup"><span data-stu-id="e8669-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="e8669-113">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="e8669-114">Declara un método para establecer los filtros de notificación.</span><span class="sxs-lookup"><span data-stu-id="e8669-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="e8669-115">ISymENCUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="e8669-116">Proporciona información para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="e8669-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="e8669-117">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="e8669-118">Esta interfaz es el complemento de lectura de la [interfaz ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e8669-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="e8669-119">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="e8669-120">Permite la definición de información de método asincrónico opcional por símbolo de método.</span><span class="sxs-lookup"><span data-stu-id="e8669-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="e8669-121">Debe usar con un método abierto (es decir, entre llamadas al [método openmethod (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)y al [método CloseMethod (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="e8669-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="e8669-122">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="e8669-123">Representa un enlazador de símbolos para código no administrado.</span><span class="sxs-lookup"><span data-stu-id="e8669-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="e8669-124">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="e8669-125">Representa un enlazador de símbolos para código no administrado y extiende la interfaz `ISymUnmanagedBinder`.</span><span class="sxs-lookup"><span data-stu-id="e8669-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="e8669-126">ISymUnmanagedBinder3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="e8669-127">Representa un enlazador de símbolos para código no administrado y extiende la interfaz `ISymUnmanagedBinder`.</span><span class="sxs-lookup"><span data-stu-id="e8669-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="e8669-128">ISymUnmanagedConstant (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="e8669-129">Proporciona acceso a las constantes no administradas.</span><span class="sxs-lookup"><span data-stu-id="e8669-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="e8669-130">ISymUnmanagedDispose (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="e8669-131">Desecha los recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e8669-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="e8669-132">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="e8669-133">Representa un documento al que hace referencia un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e8669-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="e8669-134">ISymUnmanagedDocumentWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="e8669-135">Proporciona métodos para escribir en un documento al que hace referencia un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e8669-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="e8669-136">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="e8669-137">Proporciona métodos para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="e8669-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="e8669-138">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="e8669-139">Representa un método dentro del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e8669-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="e8669-140">ISymUnmanagedNamespace (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="e8669-141">Representa un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e8669-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="e8669-142">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="e8669-143">Representa un lector de símbolos que proporciona acceso a los documentos, métodos y variables de un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e8669-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="e8669-144">ISymUnmanagedReader2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="e8669-145">Obtiene un método del lector de símbolos dado un token de método y un número de versión de edición y copia.</span><span class="sxs-lookup"><span data-stu-id="e8669-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="e8669-146">ISymUnmanagedReaderSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="e8669-147">Proporciona métodos que obtienen información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e8669-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="e8669-148">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="e8669-149">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="e8669-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="e8669-150">ISymUnmanagedScope2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="e8669-151">Representa un ámbito léxico dentro de un método y extiende la interfaz `ISymUnmanagedScope` con métodos que obtienen información sobre las constantes definidas dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="e8669-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="e8669-152">ISymUnmanagedSourceServerModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="e8669-153">Proporciona datos del servidor de origen para un módulo.</span><span class="sxs-lookup"><span data-stu-id="e8669-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="e8669-154">ISymUnmanagedSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="e8669-155">Proporciona métodos que obtienen información sobre la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e8669-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="e8669-156">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="e8669-157">Representa una variable, como un parámetro, una variable local o un campo.</span><span class="sxs-lookup"><span data-stu-id="e8669-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="e8669-158">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="e8669-159">Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.</span><span class="sxs-lookup"><span data-stu-id="e8669-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="e8669-160">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="e8669-161">Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.</span><span class="sxs-lookup"><span data-stu-id="e8669-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="e8669-162">Extiende la interfaz `ISymUnmanagedWriter`.</span><span class="sxs-lookup"><span data-stu-id="e8669-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="e8669-163">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="e8669-164">Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.</span><span class="sxs-lookup"><span data-stu-id="e8669-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="e8669-165">Extiende la interfaz `ISymUnmanagedWriter`.</span><span class="sxs-lookup"><span data-stu-id="e8669-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="e8669-166">ISymUnmanagedWriter4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="e8669-167">Interfaz Isymunmanagedwriter4 (.</span><span class="sxs-lookup"><span data-stu-id="e8669-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="e8669-168">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8669-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="e8669-169">Interfaz ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="e8669-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e8669-170">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e8669-170">Related Sections</span></span>  
 [<span data-ttu-id="e8669-171">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e8669-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="e8669-172">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e8669-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="e8669-173">Depuración</span><span class="sxs-lookup"><span data-stu-id="e8669-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
