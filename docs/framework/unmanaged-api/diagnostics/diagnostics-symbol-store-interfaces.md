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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fca7359888b8b73b2e1cf709ab708d71abf0db6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787899"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Interfaces de almacén de símbolos de diagnósticos
En este tema se describe las interfaces no administradas que permiten a un compilador generar información de símbolos para su uso por un depurador.  
  
## <a name="in-this-section"></a>En esta sección  
 [IBindingDisplay (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 Proporciona métodos que muestran la información de enlace actual sobre la aplicación en ejecución.  
  
 [IDebugAutoAttach (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 Define la interfaz para la asociación automática del depurador que invoca el servidor.  
  
 [INotifyConnection2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 Declara los métodos para registrar y anular el registro de un origen de conexión de notificación.  
  
 [INotifySink2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 Declara los métodos de notificación del receptor.  
  
 [INotifySource2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 Declara un método para establecer filtros de notificación.  
  
 [ISymENCUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 Proporciona información para la característica Editar y continuar.  
  
 [ISymUnmanagedAsyncMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 Esta interfaz es el complemento de lectura a [ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
 [ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Permite la definición de la información de método asincrónico opcional por el símbolo de método. Debe usar con un método abierto (es decir, entre las llamadas a la [OpenMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)y [CloseMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).  
  
 [ISymUnmanagedBinder (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 Representa un enlazador de símbolos de código no administrado.  
  
 [ISymUnmanagedBinder2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 Representa un enlazador de símbolos de código no administrado y extiende el `ISymUnmanagedBinder` interfaz.  
  
 [ISymUnmanagedBinder3 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 Representa un enlazador de símbolos de código no administrado y extiende el `ISymUnmanagedBinder` interfaz.  
  
 [ISymUnmanagedConstant (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 Proporciona acceso a las constantes no administrados.  
  
 [ISymUnmanagedDispose (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 Se deshace de los recursos no administrados.  
  
 [ISymUnmanagedDocument (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 Representa un documento al que hace referencia un almacén de símbolos.  
  
 [ISymUnmanagedDocumentWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 Proporciona métodos para escribir en un documento al que hace referencia un almacén de símbolos.  
  
 [ISymUnmanagedENCUpdate (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 Proporciona métodos para la característica Editar y continuar.  
  
 [ISymUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 Representa un método en el almacén de símbolos.  
  
 [ISymUnmanagedNamespace (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 Representa un espacio de nombres.  
  
 [ISymUnmanagedReader (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 Representa un lector de símbolos que proporciona acceso a documentos, métodos y variables dentro de un almacén de símbolos.  
  
 [ISymUnmanagedReader2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 Obtiene un método del lector de símbolos dado un token de método y un número de versión de editar y copiar.  
  
 [ISymUnmanagedReaderSymbolSearchInfo (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 Proporciona métodos que obtienen información de búsqueda de símbolos.  
  
 [ISymUnmanagedScope (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 Representa un ámbito léxico dentro de un método.  
  
 [ISymUnmanagedScope2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 Representa un ámbito léxico dentro de un método y extiende el `ISymUnmanagedScope` interfaz con métodos que obtienen información sobre las constantes definidas dentro del ámbito...  
  
 [ISymUnmanagedSourceServerModule (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 Proporciona datos del servidor de origen para un módulo.  
  
 [ISymUnmanagedSymbolSearchInfo (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 Proporciona métodos que obtienen información acerca de la ruta de acceso de búsqueda.  
  
 [ISymUnmanagedVariable (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 Representa una variable, como un parámetro, una variable local o un campo.  
  
 [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, los ámbitos léxicos y variables.  
  
 [ISymUnmanagedWriter2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, los ámbitos léxicos y variables. Extiende la `ISymUnmanagedWriter` interfaz.  
  
 [ISymUnmanagedWriter3 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, los ámbitos léxicos y variables. Extiende la `ISymUnmanagedWriter` interfaz.  
  
 [ISymUnmanagedWriter4 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 ISymUnmanagedWriter4 (interfaz).  
  
 [ISymUnmanagedWriter5 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 ISymUnmanagedWriter5 (interfaz).  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Enumeraciones de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [Estructuras de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
