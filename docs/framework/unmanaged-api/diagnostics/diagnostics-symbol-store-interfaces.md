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
# <a name="diagnostics-symbol-store-interfaces"></a>Interfaces de almacén de símbolos de diagnósticos

En este tema se describen las interfaces no administradas que permiten a un compilador generar información de símbolos para su uso por parte de un depurador.  
  
## <a name="in-this-section"></a>En esta sección  

 [IBindingDisplay (Interfaz)](ibindingdisplay-interface.md)  
 Proporciona métodos que muestran información de enlace actual sobre la aplicación en ejecución.  
  
 [IDebugAutoAttach (Interfaz)](idebugautoattach-interface.md)  
 Define la interfaz para una asociación automática del depurador invocado por el servidor.  
  
 [INotifyConnection2 (Interfaz)](inotifyconnection2-interface.md)  
 Declara los métodos para registrar y anular el registro de un origen de notificación de conexión.  
  
 [INotifySink2 (Interfaz)](inotifysink2-interface.md)  
 Declara los métodos para la notificación de receptor.  
  
 [INotifySource2 (Interfaz)](inotifysource2-interface.md)  
 Declara un método para establecer los filtros de notificación.  
  
 [ISymENCUnmanagedMethod (Interfaz)](isymencunmanagedmethod-interface.md)  
 Proporciona información para la característica editar y continuar.  
  
 [ISymUnmanagedAsyncMethod (Interfaz)](isymunmanagedasyncmethod-interface.md)  
 Esta interfaz es el complemento de lectura de la [interfaz ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
 [ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Permite la definición de información de método asincrónico opcional por símbolo de método. Debe usar con un método abierto (es decir, entre llamadas al [método openmethod (](isymunmanagedwriter-openmethod-method.md)y al [método CloseMethod (](isymunmanagedwriter-closemethod-method.md)).  
  
 [ISymUnmanagedBinder (Interfaz)](isymunmanagedbinder-interface.md)  
 Representa un enlazador de símbolos para código no administrado.  
  
 [ISymUnmanagedBinder2 (Interfaz)](isymunmanagedbinder2-interface.md)  
 Representa un enlazador de símbolos para código no administrado y extiende la `ISymUnmanagedBinder` interfaz.  
  
 [ISymUnmanagedBinder3 (Interfaz)](isymunmanagedbinder3-interface.md)  
 Representa un enlazador de símbolos para código no administrado y extiende la `ISymUnmanagedBinder` interfaz.  
  
 [ISymUnmanagedConstant (Interfaz)](isymunmanagedconstant-interface.md)  
 Proporciona acceso a las constantes no administradas.  
  
 [ISymUnmanagedDispose (Interfaz)](isymunmanageddispose-interface.md)  
 Desecha los recursos no administrados.  
  
 [ISymUnmanagedDocument (Interfaz)](isymunmanageddocument-interface.md)  
 Representa un documento al que hace referencia un almacén de símbolos.  
  
 [ISymUnmanagedDocumentWriter (Interfaz)](isymunmanageddocumentwriter-interface.md)  
 Proporciona métodos para escribir en un documento al que hace referencia un almacén de símbolos.  
  
 [ISymUnmanagedENCUpdate (Interfaz)](isymunmanagedencupdate-interface.md)  
 Proporciona métodos para la característica editar y continuar.  
  
 [ISymUnmanagedMethod (Interfaz)](isymunmanagedmethod-interface.md)  
 Representa un método dentro del almacén de símbolos.  
  
 [ISymUnmanagedNamespace (Interfaz)](isymunmanagednamespace-interface.md)  
 Representa un espacio de nombres.  
  
 [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)  
 Representa un lector de símbolos que proporciona acceso a los documentos, métodos y variables de un almacén de símbolos.  
  
 [ISymUnmanagedReader2 (Interfaz)](isymunmanagedreader2-interface.md)  
 Obtiene un método del lector de símbolos dado un token de método y un número de versión de edición y copia.  
  
 [ISymUnmanagedReaderSymbolSearchInfo (Interfaz)](isymunmanagedreadersymbolsearchinfo-interface.md)  
 Proporciona métodos que obtienen información de búsqueda de símbolos.  
  
 [ISymUnmanagedScope (Interfaz)](isymunmanagedscope-interface.md)  
 Representa un ámbito léxico dentro de un método.  
  
 [ISymUnmanagedScope2 (Interfaz)](isymunmanagedscope2-interface.md)  
 Representa un ámbito léxico dentro de un método y extiende la `ISymUnmanagedScope` interfaz con métodos que obtienen información sobre las constantes definidas dentro del ámbito.  
  
 [ISymUnmanagedSourceServerModule (Interfaz)](isymunmanagedsourceservermodule-interface.md)  
 Proporciona datos del servidor de origen para un módulo.  
  
 [ISymUnmanagedSymbolSearchInfo (Interfaz)](isymunmanagedsymbolsearchinfo-interface.md)  
 Proporciona métodos que obtienen información sobre la ruta de acceso de búsqueda.  
  
 [ISymUnmanagedVariable (Interfaz)](isymunmanagedvariable-interface.md)  
 Representa una variable, como un parámetro, una variable local o un campo.  
  
 [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)  
 Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.  
  
 [ISymUnmanagedWriter2 (Interfaz)](isymunmanagedwriter2-interface.md)  
 Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables. Extiende la `ISymUnmanagedWriter` interfaz.  
  
 [ISymUnmanagedWriter3 (Interfaz)](isymunmanagedwriter3-interface.md)  
 Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables. Extiende la `ISymUnmanagedWriter` interfaz.  
  
 [ISymUnmanagedWriter4 (Interfaz)](isymunmanagedwriter4-interface.md)  
 Interfaz Isymunmanagedwriter4 (.  
  
 [ISymUnmanagedWriter5 (Interfaz)](isymunmanagedwriter5-interface.md)  
 Interfaz ISymUnmanagedWriter5.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Enumeraciones de almacén de símbolos de diagnósticos](diagnostics-symbol-store-enumerations.md)  
  
 [Estructuras de almacén de símbolos de diagnósticos](diagnostics-symbol-store-structures.md)  
  
 [Depuración](../debugging/index.md)
