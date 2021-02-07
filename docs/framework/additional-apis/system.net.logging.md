---
description: 'Más información sobre: clase de registro'
title: Clase de registro (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Logging
- System.Net.Logging.Associate
- System.Net.Logging.Enter
- System.Net.Logging.Exception
- System.Net.Logging.Exit
- System.Net.Logging.get_Http
- System.Net.Logging.get_On
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 1ae3079ab21502ee3f5bf71db57f0695da9a8571
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726213"
---
# <a name="logging-class"></a>Clase Logging

Proporciona la funcionalidad de registro de seguimiento.

```csharp
internal class Logging
```

> [!WARNING]
> Esta clase es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="associate-method"></a>Associate (método)

Registra información que dos objetos están asociados entre sí.

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `objA` <xref:System.Object>

  Objeto con el que se va a asociar `objB` .

- `objB` <xref:System.Object>

  Objeto con el que se va a asociar `objA` .

## <a name="entertracesource-object-string-string-method"></a>Enter (TraceSource, Object, String, String) (método)

Registra la entrada a un método.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `obj` <xref:System.Object>

  Objeto en el que se llamó al método.

- `method` <xref:System.String>

  Método que se va a escribir.

- `param` <xref:System.String>

  Los parámetros que se pasaron al método.

## <a name="entertracesource-object-string-object-method"></a>Enter (TraceSource, Object, String, Object) (método)

Registra la entrada a un método.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `obj` <xref:System.Object>

  Objeto en el que se llamó al método.

- `method` <xref:System.String>

  Método que se va a escribir.

- `paramObject` <xref:System.Object>

  Los parámetros que se pasaron al método.

## <a name="entertracesource-string-string-string-method"></a>Enter (TraceSource, String, String, String) (método)

Registra la entrada a un método.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `obj` <xref:System.String>

  Objeto en el que se llamó al método.

- `method` <xref:System.String>

  Método que se va a escribir.

- `param` <xref:System.String>

  Los parámetros que se pasaron al método.

## <a name="entertracesource-string-string-object-method"></a>Enter (TraceSource, String, String, Object) (método)

Registra la entrada a un método.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `obj` <xref:System.String>

  Objeto en el que se llamó al método.

- `method` <xref:System.String>

  Método que se va a escribir.

- `paramObject` <xref:System.Object>

  Los parámetros que se pasaron al método.

## <a name="entertracesource-string-string-method"></a>Enter (TraceSource, String, String) (método)

Registra la entrada a un método.

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `method` <xref:System.String>

  Método que se va a escribir.

- `parameters` <xref:System.String>

  Los parámetros que se pasaron al método.

## <a name="entertracesource-string-method"></a>Enter (TraceSource, String) (método)

Registra la entrada a un método.

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `msg` <xref:System.String>

  Mensaje de entrada que se va a registrar en el origen de seguimiento.

## <a name="exception-method"></a>Exception (método)

Registra una excepción y restaura la sangría.

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `obj` <xref:System.Object>

  Objeto en el que se llamó al método que inició una excepción.

- `method` <xref:System.String>

  El método que produjo la excepción.

- `e` <xref:System.Exception>

  La excepción que se produjo.

## <a name="exittracesource-object-string-object-method"></a>Exit (TraceSource, Object, String, Object) (método)

Los registros salen de una función.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `obj` <xref:System.Object>

  Objeto en el que se llamó al método.

- `method` <xref:System.String>

  El método que se está saliendo.

- `retObject` <xref:System.Object>

  Valor que devuelve el método.

## <a name="exittracesource-string-string-object-method"></a>Exit (TraceSource, String, String, Object) (método)

Los registros salen de una función.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `obj` <xref:System.String>

  Objeto en el que se llamó al método.

- `method` <xref:System.String>

  El método que se está saliendo.

- `retObject` <xref:System.Object>

  Valor que devuelve el método.

## <a name="exittracesource-object-string-string-method"></a>Exit (TraceSource, Object, String, String) (método)

Los registros salen de una función.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `obj` <xref:System.Object>

  Objeto en el que se llamó al método.

- `method` <xref:System.String>

  El método que se está saliendo.

- `retValue` <xref:System.String>

  Valor que devuelve el método.

## <a name="exittracesource-string-string-string-method"></a>Exit (TraceSource, cadena, cadena, cadena) (método)

Los registros salen de una función.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `obj` <xref:System.String>

  Objeto en el que se llamó al método.

- `method` <xref:System.String>

  El método que se está saliendo.

- `retValue` <xref:System.String>

  Valor que devuelve el método.

## <a name="exittracesource-string-string-method"></a>Exit (TraceSource, String, String) (método)

Los registros salen de una función.

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `method` <xref:System.String>

  El método que se está saliendo.

- `parameters` <xref:System.String>

  Los parámetros que se pasaron al método que se está cerrando.

## <a name="exittracesource-string-method"></a>Exit (TraceSource, String) (método)

Los registros salen de una función.

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>Parámetros

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Origen de seguimiento en el que se va a registrar el evento.

- `msg` <xref:System.String>

  Mensaje de salida que se va a registrar en el origen de seguimiento.

## <a name="http-property"></a>Propiedad http

Obtiene el origen de seguimiento para "System .net. http".

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a>Valor de propiedad

<xref:System.Diagnostics.TraceSource>\
El origen de seguimiento para "System .net. http" o `null` si el registro no está habilitado.

## <a name="on-property"></a>On (propiedad)

Obtiene un valor que indica si el registro está habilitado.

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a>Valor de propiedad

<xref:System.Boolean>\
`true` si el registro está habilitado; de lo contrario, `false`.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)
