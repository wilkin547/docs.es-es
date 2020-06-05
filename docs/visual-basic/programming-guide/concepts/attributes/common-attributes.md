---
title: Atributos comunes
ms.date: 07/20/2015
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
ms.openlocfilehash: 57ef8f103d64a51d896f46d2889d78ec99ff3223
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400724"
---
# <a name="common-attributes-visual-basic"></a>Common Attributes (Visual Basic) (Atributos comunes [Visual Basic])

En este tema se describen los atributos que se usan con más frecuencia en Visual Basic programas.

- [Atributos globales](#Global)

- [Atributo Obsolete](#Obsolete)

- [Atributo Conditional](#Conditional)

- [Atributos de información del llamador](#CallerInfo)

- [Atributos de Visual Basic](#VB)

## <a name="global-attributes"></a><a name="Global"></a>Atributos globales

La mayoría de los atributos se aplican a elementos específicos del lenguaje, como las clases o los métodos, aunque algunos atributos son globales (se aplican a todo un ensamblado o módulo). Por ejemplo, el atributo <xref:System.Reflection.AssemblyVersionAttribute> se puede usar para insertar información de versión en un ensamblado, como en este ejemplo:

```vb
<Assembly: AssemblyVersion("1.0.0.0")>
```

Los atributos globales aparecen en el código fuente después de cualquier instrucción de nivel superior `Imports` y antes de cualquier declaración de espacio de nombres, módulo o tipo. Los atributos globales pueden aparecer en varios archivos de código fuente, pero estos archivos se deben compilar en un solo paso de compilación. En el caso de los proyectos de Visual Basic, los atributos globales normalmente se colocan en el archivo AssemblyInfo. VB (el archivo se crea automáticamente cuando se crea un proyecto en Visual Studio).

Los atributos de ensamblado son valores que proporcionan información sobre un ensamblado. Se dividen en las siguientes categorías:

- Atributos de identidad del ensamblado

- Atributos informativos

- Atributos de manifiesto del ensamblado

### <a name="assembly-identity-attributes"></a>Atributos de identidad del ensamblado

Tres atributos, con un nombre seguro (si procede), determinan la identidad de un ensamblado: nombre, versión y referencia cultural. Estos atributos forman el nombre completo del ensamblado y son necesarios cuando se hace referencia a este en el código. Puede establecer la versión y la referencia cultural de un ensamblado mediante atributos, pero el valor de nombre lo establece el compilador, el IDE de Visual Studio en el [cuadro de diálogo de información de ensamblado](/visualstudio/ide/reference/assembly-information-dialog-box) o la herramienta Assembly Linker (Al.exe) cuando se crea el ensamblado, a partir del archivo que contiene el manifiesto del ensamblado. El atributo <xref:System.Reflection.AssemblyFlagsAttribute> especifica si pueden coexistir varias copias del ensamblado.

En la siguiente tabla se muestran los atributos de identidad.

|Atributo|Propósito|
|---------------|-------------|
|<xref:System.Reflection.AssemblyName>|Describe completamente la identidad de un ensamblado.|
|<xref:System.Reflection.AssemblyVersionAttribute>|Especifica la versión de un ensamblado.|
|<xref:System.Reflection.AssemblyCultureAttribute>|Especifica la cultura que admite el ensamblado.|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Especifica si un ensamblado admite la ejecución en paralelo en el mismo equipo, en el mismo proceso o en el mismo dominio de aplicación.|

### <a name="informational-attributes"></a>Atributos informativos

Puede utilizar atributos informativos para proporcionar información adicional de la compañía o de producto para un ensamblado. En la tabla siguiente se muestran los atributos informativos definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.

|Atributo|Propósito|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|Define un atributo personalizado que especifica un nombre de producto para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Define un atributo personalizado que especifica una marca comercial para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Define un atributo personalizado que especifica una versión informativa para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Define un atributo personalizado que especifica un nombre de compañía para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Define un atributo personalizado que especifica un copyright para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Indica al compilador que use un número de versión específico para el recurso de versión de archivo Win32.|
|<xref:System.CLSCompliantAttribute>|Indica si el ensamblado es compatible con Common Language Specification (CLS).|

### <a name="assembly-manifest-attributes"></a>Atributos de manifiesto del ensamblado

Puede usar los atributos de manifiesto del ensamblado para proporcionar información en el manifiesto del ensamblado (título, descripción, alias predeterminado y configuración). En la tabla siguiente se muestran los atributos de manifiesto del ensamblado definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.

|Atributo|Propósito|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|Define un atributo personalizado que especifica un título de ensamblado para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Define un atributo personalizado que especifica una descripción de ensamblado para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Define un atributo personalizado que especifica una configuración de ensamblado (por ejemplo, comercial o depuración) para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Define un alias descriptivo predeterminado para un manifiesto del ensamblado.|

## <a name="obsolete-attribute"></a><a name="Obsolete"></a>Atributo obsoleto

El atributo `Obsolete` marca una entidad del programa como una entidad cuyo uso ya no se recomienda. Cada uso de una entidad marcada como obsoleta generará posteriormente una advertencia o un error, en función de la configuración del atributo. Por ejemplo:

```vb
<System.Obsolete("use class B")>
Class A
    Sub Method()
    End Sub
End Class

Class B
    <System.Obsolete("use NewMethod", True)>
    Sub OldMethod()
    End Sub

    Sub NewMethod()
    End Sub
End Class
```

En este ejemplo, el atributo `Obsolete` se aplica a la clase `A` y al método `B.OldMethod`. Dado que el segundo argumento del constructor de atributos aplicado a `B.OldMethod` está establecido en `true`, este método producirá un error del compilador, mientras que, si se usa la clase `A`, solo se generará una advertencia. En cambio, si se llama a `B.NewMethod`, no se generará ninguna advertencia o error.

La cadena proporcionada como primer argumento al constructor de atributos se mostrará como parte de la advertencia o error. Por ejemplo, al usarla con las definiciones anteriores, el código siguiente genera dos advertencias y un error:

```vb
' Generates 2 warnings:
' Dim a As New A
' Generate no errors or warnings:

Dim b As New B
b.NewMethod()

' Generates an error, terminating compilation:
' b.OldMethod()
```

Se generan dos advertencias para la clase `A`: una para la declaración de la referencia de clase y otra para el constructor de clases.

El atributo `Obsolete` se puede usar sin argumentos, aunque se recomienda incluir una explicación de por qué el elemento está obsoleto y qué se debe usar en su lugar.

El atributo `Obsolete` es un atributo de uso único y se puede aplicar a cualquier entidad que admita atributos. `Obsolete` es un alias de <xref:System.ObsoleteAttribute>.

## <a name="conditional-attribute"></a><a name="Conditional"></a>Atributo Conditional

El atributo `Conditional` hace que la ejecución de un método dependa de un identificador de preprocesamiento. El atributo `Conditional` es un alias de <xref:System.Diagnostics.ConditionalAttribute> y se puede aplicar a un método o a una clase de atributo.

En este ejemplo, `Conditional` se aplica a un método para habilitar o deshabilitar la visualización de información de diagnóstico específica del programa:

```vb
#Const TRACE_ON = True
Imports System.Diagnostics

Module TestConditionalAttribute
    Public Class Trace
        <Conditional("TRACE_ON")>
        Public Shared Sub Msg(ByVal msg As String)
            Console.WriteLine(msg)
        End Sub

    End Class

    Sub Main()
        Trace.Msg("Now in Main...")
        Console.WriteLine("Done.")
    End Sub
End Module
```

Si el identificador `TRACE_ON` no está definido, no se mostrará ningún resultado del seguimiento.

El atributo `Conditional` se suele usar con el identificador `DEBUG` para habilitar las funciones de seguimiento y de registro para las compilaciones de depuración (pero no en las compilaciones de versión), como en este ejemplo:

```vb
<Conditional("DEBUG")>
Shared Sub DebugMethod()

End Sub
```

Al llamar a un método marcado como condicional, la presencia o ausencia del símbolo de preprocesamiento especificado determina si se incluye o se omite la llamada. Si el símbolo está definido, se incluye la llamada; de lo contrario, se omite la llamada. Usar `Conditional` es una alternativa más limpia, más elegante y menos propensa a generar errores para agregar métodos dentro de los bloques `#if…#endif`, como en el siguiente ejemplo:

```vb
#If DEBUG Then
    Sub ConditionalMethod()
    End Sub
#End If
```

Los métodos condicionales deben ser métodos de una declaración de clase o struct y no deben tener ningún valor devuelto.

### <a name="using-multiple-identifiers"></a>Usar varios identificadores

Si un método tiene varios atributos `Conditional`, se incluye una llamada al método si al menos uno de los símbolos condicionales está definido (es decir, si los símbolos están vinculados lógicamente entre sí mediante el operador OR). En este ejemplo, la presencia de `A` o de `B` dará como resultado una llamada al método:

```vb
<Conditional("A"), Conditional("B")>
Shared Sub DoIfAorB()

End Sub
```

Para lograr el efecto de una vinculación lógica de símbolos mediante el operador AND, puede definir métodos condicionales en serie. Por ejemplo, el segundo método que se muestra a continuación solo se ejecutará si tanto `A` como `B` están definidos:

```vb
<Conditional("A")>
Shared Sub DoIfA()
    DoIfAandB()
End Sub

<Conditional("B")>
Shared Sub DoIfAandB()
    ' Code to execute when both A and B are defined...
End Sub
```

### <a name="using-conditional-with-attribute-classes"></a>Usar Conditional con clases de atributos

El atributo `Conditional` también se puede aplicar a una definición de clase de atributo. En este ejemplo, el atributo personalizado `Documentation` solo agregará información a los metadatos si se define DEBUG.

```vb
<Conditional("DEBUG")>
Public Class Documentation
    Inherits System.Attribute
    Private text As String
    Sub New(ByVal doc_text As String)
        text = doc_text
    End Sub
End Class

Class SampleClass
    ' This attribute will only be included if DEBUG is defined.
    <Documentation("This method displays an integer.")>
    Shared Sub DoWork(ByVal i As Integer)
        System.Console.WriteLine(i)
    End Sub
End Class
```

## <a name="caller-info-attributes"></a><a name="CallerInfo"></a>Atributos de información del llamador

Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método. Puede obtener la ruta de acceso al código fuente, el número de línea del código fuente y el nombre del miembro del llamador.

Para obtener la información del llamador del miembro, use los atributos que se aplican a los parámetros opcionales. Cada parámetro opcional especifica un valor predeterminado. En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:

|Atributo|Descripción|Tipo|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Ruta de acceso completa del archivo de código fuente que contiene el llamador. Esta es la ruta de acceso en tiempo de compilación.|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Número de línea del archivo de código fuente desde el que se llama al método.|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Nombre de método o de propiedad del llamador. Para obtener más información, vea [información del llamador (Visual Basic)](../caller-information.md).|`String`|

Para obtener más información sobre los atributos de información del llamador, vea [información del llamador (Visual Basic)](../caller-information.md).

## <a name="visual-basic-attributes"></a><a name="VB"></a>Atributos de Visual Basic

En la tabla siguiente se enumeran los atributos que son específicos de Visual Basic.

|Atributo|Propósito|
|---------------|-------------|
|<xref:Microsoft.VisualBasic.ComClassAttribute>|Indica al compilador que la clase debe exponerse como un objeto COM.|
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute>|Permite tener acceso a los miembros de módulo usando solo la calificación necesaria para el módulo.|
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute>|Especifica el tamaño de una cadena de longitud fija en una estructura para su uso con funciones de entrada y salida de archivo.|
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|Especifica el tamaño de una matriz fija en una estructura para su uso con funciones de entrada y salida de archivo.|

### <a name="comclassattribute"></a>COMClassAttribute

`COMClassAttribute`Se usa para simplificar el proceso de creación de componentes com a partir de Visual Basic. Los objetos COM son considerablemente diferentes de los ensamblados de .NET Framework y sin `COMClassAttribute` , debe seguir una serie de pasos para generar un objeto com a partir de Visual Basic. En el caso de las clases marcadas con `COMClassAttribute` , el compilador realiza muchos de estos pasos automáticamente.

### <a name="hidemodulenameattribute"></a>HideModuleNameAttribute

Use `HideModuleNameAttribute` para permitir el acceso a los miembros de módulo usando solo la calificación necesaria para el módulo.

### <a name="vbfixedstringattribute"></a>VBFixedStringAttribute

Use `VBFixedStringAttribute` para forzar Visual Basic para crear una cadena de longitud fija. Las cadenas son de longitud variable de forma predeterminada, y este atributo es útil cuando se almacenan cadenas en archivos. El código siguiente muestra este proceso:

```vb
Structure Worker
    ' The runtime uses VBFixedString to determine
    ' if the field should be written out as a fixed size.
    <VBFixedString(10)> Public LastName As String
    <VBFixedString(7)> Public Title As String
    <VBFixedString(2)> Public Rank As String
End Structure
```

### <a name="vbfixedarrayattribute"></a>VBFixedArrayAttribute

Use `VBFixedArrayAttribute` para declarar matrices de tamaño fijo. Al igual que las cadenas de Visual Basic, las matrices son de longitud variable de forma predeterminada. Este atributo es útil al serializar o escribir datos en archivos.

## <a name="see-also"></a>Consulte también

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Guía de programación en Visual Basic](../../index.md)
- [Atributos](../../../../standard/attributes/index.md)
- [Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])
- [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])
