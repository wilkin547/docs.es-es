---
title: 'Atributos reservados de C#: seguimiento de la información del autor de la llamada'
ms.date: 04/09/2020
description: Estos atributos indican al compilador que genere información sobre el código que llama a un miembro. Use CallerFilePath, CallerLineNumber y CallerMemberName para proporcionar información de seguimiento detallada.
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389827"
---
# <a name="reserved-attributes-determine-caller-information"></a>Atributos reservados: determinación de la información del autor de la llamada

Mediante los atributos de información, se obtiene información sobre el autor de la llamada a un método. Se obtiene la ruta de acceso al código fuente, el número de línea del código fuente y el nombre de miembro del autor de la llamada. Para obtener la información del llamador del miembro, use los atributos que se aplican a los parámetros opcionales. Cada parámetro opcional especifica un valor predeterminado. En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:

|Atributo|Descripción|Tipo|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Ruta de acceso completa del archivo de código fuente que contiene el llamador. La ruta de acceso completa es la ruta de acceso en tiempo de compilación.|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Número de línea del archivo de código fuente desde el que se llama al método.|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Nombre de método o de propiedad del llamador.|`String`|

Esta información facilita la creación de herramientas de seguimiento, depuración y diagnóstico. En el ejemplo siguiente se muestra cómo usar atributos de información del autor de la llamada. En cada llamada al método `TraceMessage`, la información del llamador se sustituye como argumentos para los parámetros opcionales.

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

Debe especificar un valor predeterminado explícito para cada parámetro opcional. No puede aplicar atributos de información del autor de la llamada a los parámetros que no se especifican como opcionales. Los atributos de información del autor de la llamada no crean un parámetro opcional, sino que influyen en el valor predeterminado que se pasa cuando se omite el argumento. Los valores de información del autor de la llamada se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación. A diferencia de los resultados de la propiedad <xref:System.Exception.StackTrace%2A> para las excepciones, los resultados no se ven afectados por confusión. Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.

### <a name="member-names"></a>Nombres de miembro

Se puede utilizar el atributo `CallerMemberName` para evitar especificar el nombre de miembro como un argumento `String` para el método llamado. Mediante esta técnica, se evita el problema de que la **refactorización de cambio de nombre** no cambie los valores `String`. Esta ventaja es especialmente útil para las siguientes tareas:

- Usar el seguimiento y las rutinas de diagnóstico.
- Implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> al enlazar datos. Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada. Sin el atributo `CallerMemberName`, se debe especificar el nombre de propiedad como un literal.

En el gráfico siguiente se muestran los nombres de miembro que se devuelven cuando se utiliza el atributo `CallerMemberName`.

|Las llamadas se producen en|Resultado del nombre de miembro|
|-|-|
|Método, propiedad o evento|Nombre del método, propiedad o evento en el que se originó la llamada.|
|Constructor|Cadena ".ctor"|
|Constructor estático|Cadena ".cctor"|
|Destructor|Cadena "Finalize"|
|Conversiones u operadores definidos por el usuario|Nombre generado para el miembro, por ejemplo, "op_Addition".|
|Constructor de atributo|Nombre del método o la propiedad a la que se aplica el atributo. Si el atributo es cualquier elemento dentro de un miembro (como un parámetro, un valor devuelto o un parámetro de tipo genérico), el resultado es el nombre del miembro asociado a este elemento.|
|Ningún miembro contenedor (por ejemplo, nivel de ensamblado o atributos que se aplican a tipos)|El valor predeterminado del parámetro opcional.|

## <a name="see-also"></a>Vea también

- [Argumentos opcionales y con nombre](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [Atributos](../../../standard/attributes/index.md)
