---
title: Información del agente de llamada
description: Describe cómo usar los atributos de argumento de información del llamador para obtener información del llamador de un método.
ms.date: 11/04/2019
ms.openlocfilehash: 700cde26fbe4e6c48155f88bfc63af59af86cfe2
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739781"
---
# <a name="caller-information"></a>Información del agente de llamada

Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método. Puede obtener la ruta de acceso al código fuente, el número de línea en el código fuente y el nombre de miembro del llamador. Esta información resulta útil para el seguimiento y la depuración, así como para crear herramientas de diagnóstico.

Para obtener esta información, se usan los atributos que se aplican a los parámetros opcionales, que tienen valores predeterminados. En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres [System. Runtime. CompilerServices](/dotnet/api/system.runtime.compilerservices) :

|Atributo|Descripción|Tipo|
|---------|-----------|----|
|[CallerFilePath](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|Ruta de acceso completa del archivo de código fuente que contiene el llamador. Esta es la ruta de acceso en tiempo de compilación.|`String`
|[CallerLineNumber](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|Número de línea en el archivo de código fuente en el que se llama al método.|`Integer`|
|[CallerMemberName](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|Método o nombre de propiedad del llamador. Vea la sección nombres de miembro más adelante en este tema.|`String`|

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo puede utilizar estos atributos para realizar el seguimiento de un llamador.

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member _.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf $"Message: {message}")
        Trace.WriteLine(sprintf $"Member name: {memberName}")
        Trace.WriteLine(sprintf $"Source file path: {path}")
        Trace.WriteLine(sprintf $"Source line number: {line}")
```

## <a name="remarks"></a>Comentarios

Los atributos de información del llamador solo se pueden aplicar a los parámetros opcionales. Los atributos de información del llamador hacen que el compilador escriba el valor adecuado para cada parámetro opcional decorado con un atributo de información del llamador.

Los valores de información del llamador se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación. A diferencia de los resultados de la propiedad [StackTrace](/dotnet/api/system.diagnostics.stacktrace) para las excepciones, los resultados no se ven afectados por la ofuscación.

Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.

## <a name="member-names"></a>Nombres de miembro

Puede usar el [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atributo para evitar especificar el nombre de miembro como un `String` argumento para el método llamado. Mediante esta técnica, se evita el problema de que la refactorización de cambio de nombre no cambie los valores `String`. Esta ventaja es especialmente útil para las siguientes tareas:

- Usar el seguimiento y las rutinas de diagnóstico.
- Implementar la interfaz [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) al enlazar datos. Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada. Sin el [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atributo, debe especificar el nombre de la propiedad como un literal.

En el gráfico siguiente se muestran los nombres de miembro que se devuelven cuando se usa el atributo CallerMemberName.

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
