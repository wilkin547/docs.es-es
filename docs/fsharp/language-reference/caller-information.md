---
title: 'Información del llamador (F #)'
description: Describe cómo utilizar atributos de argumento de información del autor de llamada para obtener información del llamador de un método.
ms.date: 04/25/2017
ms.openlocfilehash: 0f2f4b16804d9156d234cc29d1f72ebe80a5b556
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353452"
---
# <a name="caller-information"></a>Información del llamador

Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método. Puede obtener la ruta de acceso al código fuente, el número de línea en el código fuente y el nombre de miembro del llamador. Esta información resulta útil para el seguimiento y la depuración, así como para crear herramientas de diagnóstico.

Para obtener esta información, se usan los atributos que se aplican a los parámetros opcionales, que tienen valores predeterminados. En la tabla siguiente se enumera los atributos de información del llamador que se definen en el [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) espacio de nombres:

|Atributo|Descripción|Tipo|
|---------|-----------|----|
|[CallerFilePath](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|Ruta de acceso completa del archivo de código fuente que contiene el llamador. Esta es la ruta de acceso en tiempo de compilación.|`String`
|[CallerLineNumber](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|Número de línea en el archivo de código fuente en el que se llama al método.|`Integer`|
|[CallerMemberName](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|Método o nombre de propiedad del llamador. Consulte la sección de los nombres de miembro más adelante en este tema.|`String`|

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo puede usar estos atributos para realizar un seguimiento de un autor de llamada.

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a>Comentarios

Atributos de información del autor de llamada solo pueden aplicarse a los parámetros opcionales. Debe proporcionar un valor explícito para cada parámetro opcional. Los atributos de información del llamador que el compilador escribir el valor adecuado para cada parámetro opcional representado con un atributo de información del llamador.

Los valores de información del llamador se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación. A diferencia de los resultados de la [StackTrace](/dotnet/api/system.diagnostics.stacktrace) propiedad para las excepciones, los resultados no se ven afectados por ofuscación.

Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.

## <a name="member-names"></a>Nombres de miembro

Puede usar el [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atributo para evitar especificar el nombre de miembro como un `String` argumento al método llamado. Mediante esta técnica, se evita el problema que cambiar el nombre de refactorización no cambia el `String` valores. Esta ventaja es especialmente útil para las siguientes tareas:

* Usar el seguimiento y las rutinas de diagnóstico.
* Implementar el [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) al enlazar datos de la interfaz. Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada. Sin el [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atributo, debe especificar el nombre de propiedad como un literal.

El siguiente gráfico muestra al miembro de los nombres que se devuelven cuando se usa el atributo CallerMemberName.

|Las llamadas se producen en|Resultado del nombre de miembro|
|-------------------|------------------|
|Método, propiedad o evento|Nombre del método, propiedad o evento en el que se originó la llamada.|
|Constructor|Cadena ".ctor"|
|Constructor estático|Cadena ".cctor"|
|Destructor|Cadena "Finalize"|
|Conversiones u operadores definidos por el usuario|Nombre generado para el miembro, por ejemplo, "op_Addition".|
|Constructor de atributo|Nombre del miembro al que se aplica el atributo. Si el atributo es cualquier elemento dentro de un miembro (como un parámetro, un valor devuelto o un parámetro de tipo genérico), el resultado es el nombre del miembro asociado a este elemento.|
|Ningún miembro contenedor (por ejemplo, nivel de ensamblado o atributos que se aplican a tipos)|El valor predeterminado del parámetro opcional.|

## <a name="see-also"></a>Vea también

- [Atributos](attributes.md)  
- [Argumentos con nombre](parameters-and-arguments.md#named-arguments)  
- [Parámetros opcionales](parameters-and-arguments.md#optional-parameters)  
