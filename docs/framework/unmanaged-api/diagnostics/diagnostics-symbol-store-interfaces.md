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
ms.openlocfilehash: e376544a9d428ce5110a7e38b92a8e830f574664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725188"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="4cf6b-102">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="4cf6b-102">Diagnostics Symbol Store Interfaces</span></span>

<span data-ttu-id="4cf6b-103">En este tema se describen las interfaces no administradas que permiten a un compilador generar información de símbolos para su uso por parte de un depurador.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4cf6b-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4cf6b-104">In This Section</span></span>  

 [<span data-ttu-id="4cf6b-105">IBindingDisplay (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-105">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="4cf6b-106">Proporciona métodos que muestran información de enlace actual sobre la aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="4cf6b-107">IDebugAutoAttach (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-107">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="4cf6b-108">Define la interfaz para una asociación automática del depurador invocado por el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="4cf6b-109">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-109">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="4cf6b-110">Declara los métodos para registrar y anular el registro de un origen de notificación de conexión.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="4cf6b-111">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-111">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="4cf6b-112">Declara los métodos para la notificación de receptor.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="4cf6b-113">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="4cf6b-114">Declara un método para establecer los filtros de notificación.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="4cf6b-115">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="4cf6b-116">Proporciona información para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="4cf6b-117">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-117">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="4cf6b-118">Esta interfaz es el complemento de lectura de la [interfaz ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4cf6b-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="4cf6b-119">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="4cf6b-120">Permite la definición de información de método asincrónico opcional por símbolo de método.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="4cf6b-121">Debe usar con un método abierto (es decir, entre llamadas al [método openmethod (](isymunmanagedwriter-openmethod-method.md)y al [método CloseMethod (](isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="4cf6b-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="4cf6b-122">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-122">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="4cf6b-123">Representa un enlazador de símbolos para código no administrado.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="4cf6b-124">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-124">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="4cf6b-125">Representa un enlazador de símbolos para código no administrado y extiende la `ISymUnmanagedBinder` interfaz.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="4cf6b-126">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-126">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="4cf6b-127">Representa un enlazador de símbolos para código no administrado y extiende la `ISymUnmanagedBinder` interfaz.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="4cf6b-128">ISymUnmanagedConstant (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-128">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="4cf6b-129">Proporciona acceso a las constantes no administradas.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="4cf6b-130">ISymUnmanagedDispose (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-130">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="4cf6b-131">Desecha los recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="4cf6b-132">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-132">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="4cf6b-133">Representa un documento al que hace referencia un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="4cf6b-134">ISymUnmanagedDocumentWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-134">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="4cf6b-135">Proporciona métodos para escribir en un documento al que hace referencia un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="4cf6b-136">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-136">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="4cf6b-137">Proporciona métodos para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="4cf6b-138">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-138">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="4cf6b-139">Representa un método dentro del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="4cf6b-140">ISymUnmanagedNamespace (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-140">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="4cf6b-141">Representa un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="4cf6b-142">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-142">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="4cf6b-143">Representa un lector de símbolos que proporciona acceso a los documentos, métodos y variables de un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="4cf6b-144">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-144">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="4cf6b-145">Obtiene un método del lector de símbolos dado un token de método y un número de versión de edición y copia.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="4cf6b-146">ISymUnmanagedReaderSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="4cf6b-147">Proporciona métodos que obtienen información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="4cf6b-148">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-148">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="4cf6b-149">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="4cf6b-150">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-150">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="4cf6b-151">Representa un ámbito léxico dentro de un método y extiende la `ISymUnmanagedScope` interfaz con métodos que obtienen información sobre las constantes definidas dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="4cf6b-152">ISymUnmanagedSourceServerModule (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-152">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="4cf6b-153">Proporciona datos del servidor de origen para un módulo.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="4cf6b-154">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="4cf6b-155">Proporciona métodos que obtienen información sobre la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="4cf6b-156">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-156">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="4cf6b-157">Representa una variable, como un parámetro, una variable local o un campo.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="4cf6b-158">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-158">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="4cf6b-159">Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="4cf6b-160">ISymUnmanagedWriter2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="4cf6b-161">Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="4cf6b-162">Extiende la `ISymUnmanagedWriter` interfaz.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="4cf6b-163">ISymUnmanagedWriter3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-163">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="4cf6b-164">Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="4cf6b-165">Extiende la `ISymUnmanagedWriter` interfaz.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="4cf6b-166">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-166">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="4cf6b-167">Interfaz Isymunmanagedwriter4 (.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="4cf6b-168">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cf6b-168">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="4cf6b-169">Interfaz ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="4cf6b-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4cf6b-170">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4cf6b-170">Related Sections</span></span>  

 [<span data-ttu-id="4cf6b-171">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="4cf6b-171">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="4cf6b-172">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="4cf6b-172">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="4cf6b-173">Depuración</span><span class="sxs-lookup"><span data-stu-id="4cf6b-173">Debugging</span></span>](../debugging/index.md)
