---
title: Novedades de Visual Basic
ms.date: 10/24/2018
f1_keywords:
- VB.StartPage.WhatsNew
helpviewer_keywords:
- new features, Visual Basic
- what's new [Visual Basic]
- Visual Basic, what's new
ms.assetid: d7e97396-7f42-4873-a81c-4ebcc4b6ca02
ms.openlocfilehash: 45763504c2d25596b0adfb4b8a0236b332d89e8c
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802054"
---
# <a name="whats-new-for-visual-basic"></a>Novedades de Visual Basic

En este tema se enumeran los nombres de las características clave de cada versión de Visual Basic con descripciones detalladas de las características nuevas y mejoradas de las versiones más recientes del lenguaje.

## <a name="current-version"></a>Versión actual

Visual Basic 16.0/Visual Studio 2019, versión 16.0\
Para las nuevas características, vea [Visual Basic 16.0](#visual-basic-160).

## <a name="previous-versions"></a>Versiones anteriores

Visual Basic 15.8/Visual Studio 2017, versión 15.8\
Para consultar las nuevas características, vea [Visual Basic 15.8](#visual-basic-158).

Visual Basic 15.5/Visual Studio 2017, versión 15.5\
Para consultar las nuevas características, vea [Visual Basic 15.5](#visual-basic-155).

Visual Basic 15.3/Visual Studio 2017, versión 15.3\
Para consultar las nuevas características, vea [Visual Basic 15.3](#visual-basic-153).

Visual Basic 2017/Visual Studio 2017\
Para consultar las nuevas características, vea [Visual Basic 2017](#visual-basic-2017).

Visual Basic/Visual Studio 2015\
Para consultar las nuevas características, vea [Visual Basic 14](#visual-basic-14).

Visual Basic/Visual Studio 2013\
Vistas previas de tecnología de .NET Compiler Platform ("Roslyn")

Visual Basic/Visual Studio 2012\
palabras clave `Async` y `await`, iteradores, atributos de información de autor de llamada

Visual Basic, Visual Studio 2010\
Propiedades autoimplementadas, inicializadores de colección, continuación de línea implícita, dinámica, covarianza/contravarianza genérica, acceso de espacio de nombres global

Visual Basic/Visual Studio 2008\
Language Integrated Query (LINQ), literales XML, inferencia de tipo de variable local, inicializadores de objeto, tipos anónimos, métodos de extensión, inferencia de tipo de variable local `var`, expresiones lambda, operador `if`, métodos parciales, tipos de valor que aceptan valores null

Visual Basic/Visual Studio 2005\
El tipo `My` y los tipos del asistente (acceso a la aplicación, equipo, sistema de archivos, red)

Visual Basic/Visual Studio .NET 2003\
Operadores de desplazamiento de bits, declaración de variable de bucle

Visual Basic/Visual Studio .NET 2002\
La primera versión de Visual Basic .NET

## <a name="visual-basic-160"></a>Visual Basic 16.0

Visual Basic 16.0 se centra en proporcionar más características del entorno de ejecución de Visual Basic (microsoft.visualbasic.dll) a .NET Core y es la primera versión de Visual Basic centrada en .NET Core. Muchas partes del entorno de ejecución de Visual Basic dependen de WinForms y se agregarán en una versión posterior de Visual Basic.

**Comentarios permitidos en más lugares dentro de las instrucciones**

En Visual Basic 15.8 y versiones anteriores, solo se permiten comentarios en líneas en blanco, al final de una instrucción o en lugares específicos dentro de una instrucción donde se permita una continuación de línea implícita. A partir de Visual Basic 16.0, también se permiten comentarios después de las continuaciones de línea explícitas y dentro de una instrucción en una línea que comienza con un espacio seguido de un guion bajo.

```vb
Public Sub Main()
    cmd.CommandText = ' Comment is allowed here without _
        "SELECT * FROM Titles JOIN Publishers " _ ' This is a comment
        & "ON Publishers.PubId = Titles.PubID " _
 _ ' This is a comment on a line without code
        & "WHERE Publishers.State = 'CA'"
End Sub
```

## <a name="visual-basic-158"></a>Visual Basic 15.8

**Punto flotante optimizado para la conversión de enteros**

En versiones anteriores de Visual Basic, la conversión de valores [dobles](../language-reference/data-types/double-data-type.md) y [únicos](../language-reference/data-types/single-data-type.md) a enteros ofrecía un rendimiento relativamente bajo. Visual Basic 15.8 mejora significativamente el rendimiento de las conversiones de punto flotante a enteros al pasar el valor devuelto por cualquiera de los métodos siguientes a uno de las [funciones de conversión de enteros de Visual Basic intrínsecas](../language-reference/functions/type-conversion-functions.md) (CByte, CShort, CInt, CLng, CSByte, CUShort, CUInt, CULng) o cuando el valor devuelto por cualquiera de los métodos siguientes se convierte implícitamente a un tipo entero cuando [Opción estricta](../language-reference/statements/option-strict-statement.md) se establece en `Off`:

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

Esta optimización permite que el código se ejecute más rápido, hasta el doble de rápido para código que realiza un gran número de conversiones a tipos enteros. En el ejemplo siguiente se muestran algunas llamadas a métodos simples que se ven afectadas por esta optimización:

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

Tenga en cuenta que esto trunca los valores de punto flotante en lugar de redondearlos.

## <a name="visual-basic-155"></a>Visual Basic 15.5

[Argumentos con nombre no finales](../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md#mixing-arguments-by-position-and-by-name)

En Visual Basic 15.3 y en versiones anteriores, cuando una llamada de método incluía argumentos por posición y por nombre, los argumentos posicionales tenían que preceder a los argumentos con nombre. A partir de Visual Basic 15.5, los argumentos posicionales y los argumentos con nombre pueden aparecer en cualquier orden, siempre y cuando todos los argumentos hasta el último argumento posicional se encuentren en la posición correcta. Esto es muy útil si se usan argumentos con nombre para mejorar la legibilidad del código.

Por ejemplo, la siguiente llamada de método tiene dos argumentos posicionales entre un argumento con nombre. El argumento con nombre deja claro que el valor 19 representa una edad.

```vb
StudentInfo.Display("Mary", age:=19, #9/21/1998#)
```

[Modificador de acceso de miembro `Private Protected`](../language-reference/modifiers/private-protected.md)

Esta nueva combinación de palabras clave define un miembro al que pueden acceder todos los miembros de su clase contenedora y los tipos derivados de dicha clase, pero solo si también se encuentran en el ensamblado contenedor. Dado que las estructuras no se pueden heredar, `Private Protected` solo se pueden aplicar a los miembros de una clase.

**Separador hexadecimal/binario/octal inicial**

En Visual Basic 2017 se ha agregado compatibilidad con el carácter de subrayado (`_`) como separador de dígitos. A partir de Visual Basic 15.5 puede usar el carácter de subrayado como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales. En el ejemplo siguiente se usa un separador de dígitos inicial para definir 3,271,948,384 como número hexadecimal:

```vb
Dim number As Integer = &H_C305_F860
```

Para usar el carácter de subrayado como separador inicial, debe agregar el elemento siguiente al archivo del proyecto de Visual Basic (\*.vbproj):

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="visual-basic-153"></a>Visual Basic 15.3

[**Inferencia en tuplas con nombre**](../programming-guide/language-features/data-types/tuples.md#inferred-tuple-element-names)

Al asignar el valor de elementos de tupla desde variables, Visual Basic infiere el nombre de los elementos de tupla a partir de los nombres de variable correspondientes, por lo que no es necesario asignar un nombre a un elemento de tupla de forma explícita. En el ejemplo siguiente se usa la inferencia para crear una tupla con tres elementos con nombre: `state`, `stateName` y `capital`.

[!code-vb[Inferred tuple names](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

**Modificadores del compilador adicionales**

El compilador de línea de comandos de Visual Basic ahora admite las opciones de compilador [ **-refout**](../reference/command-line-compiler/refout-compiler-option.md) y [ **-refonly**](../reference/command-line-compiler/refonly-compiler-option.md) para controlar la salida de ensamblados de referencia. **-refout** define el directorio de salida del ensamblado de referencia y **-refonly** especifica que solo un ensamblado de referencia se transferirá por compilación.

## <a name="visual-basic-2017"></a>Visual Basic 2017

[**Tuplas**](../programming-guide/language-features/data-types/tuples.md)

Las tuplas son una estructura de datos ligera que se usan normalmente para devolver varios valores de una sola llamada al método. Normalmente, para devolver varios valores de un método, tiene que realizar una de las siguientes acciones:

- Definir un tipo personalizado (`Class` o `Structure`). Esta es una solución pesada.

- Definir uno o más parámetros `ByRef`, además de devolver un valor del método.

La compatibilidad de Visual Basic con las tuplas le permite definir rápidamente una tupla, asignar opcionalmente nombres semánticos a sus valores y recuperar sus valores rápidamente. En el ejemplo siguiente se ajusta una llamada al método <xref:System.Int32.TryParse%2A> y se devuelve una tupla.

[!code-vb[Tuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Después, puede llamar al método y controlar la tupla devuelta con código como el siguiente.

[!code-vb[ReturnTuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

**Literales binarios y separadores de dígitos**

Puede definir un literal binario con el prefijo `&B` o `&b`. Además, puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad. En el ejemplo siguiente se usan ambas características para asignar un valor `Byte` y para mostrarlo como un número binario, hexadecimal y decimal.

[!code-vb[Binary](../../../samples/snippets/visualbasic/getting-started/bin-example.vb#1)]

Para obtener más información, vea la sección "Asignaciones literales" de los tipos de datos [Byte](../language-reference/data-types/byte-data-type.md#literal-assignments), [Integer](../language-reference/data-types/integer-data-type.md#literal-assignments), [Long](../language-reference/data-types/long-data-type.md#literal-assignments), [Short](../language-reference/data-types/short-data-type.md#literal-assignments), [SByte](../language-reference/data-types/sbyte-data-type.md#literal-assignments), [UInteger](../language-reference/data-types/uinteger-data-type.md#literal-assignments), [ULong](../language-reference/data-types/ulong-data-type.md#literal-assignments) y [UShort](../language-reference/data-types/ushort-data-type.md#literal-assignments).

[**Compatibilidad con los valores devueltos de referencia de C#** ](../programming-guide/language-features/procedures/ref-return-values.md)

A partir de C# 7.0, C# admite los valores devueltos de referencia. Es decir, cuando el método de llamada recibe un valor devuelto mediante referencia, puede cambiar el valor de esta. Visual Basic no le permite crear métodos con valores devueltos de referencia, pero le permite consumirlos y modificarlos.

Por ejemplo, la siguiente clase `Sentence` escrita en C# incluye un método `FindNext` que busca la siguiente palabra de una frase que comienza por una subcadena especificada. La cadena se devuelve como un valor devuelto de referencia, y una variable `Boolean` que se ha pasado mediante referencia al método indica si la búsqueda se ha realizado correctamente. Esto significa que el autor de la llamada no solo puede leer el valor devuelto; él o ella también puede modificarlo, y esa modificación se refleja en la clase `Sentence`.

[!code-csharp[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

En su forma más sencilla, puede modificar la palabra que se ha encontrado en la frase con código como el que se muestra a continuación. Tenga en cuenta que no está asignando un valor al método, sino a la expresión que devuelve el método, que es el valor devuelto de referencia.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#1)]

En cambio, un problema con este código es que si no se detecta una coincidencia, el método devuelve la primera palabra. Como el ejemplo no examina el valor del argumento `Boolean` para determinar si se detecta una coincidencia, modifica la primera palabra si no hay ninguna. En el ejemplo siguiente se corrige esto reemplazando la primera palabra por ella misma si no existe ninguna coincidencia.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#2)]

Una solución mejor es usar un método del asistente en el que el valor devuelto de referencia se pase mediante una referencia. El método del asistente puede después modificar el argumento que se ha pasado por referencia. En el siguiente ejemplo se realiza esto.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

Para obtener más información, vea [Valores devueltos de referencia](../programming-guide/language-features/procedures/ref-return-values.md).

## <a name="visual-basic-14"></a>Visual Basic 14

[NameOf](../language-reference/operators/nameof.md)

Puede obtener el nombre de cadena no calificado de un tipo o miembro para usarlo en un mensaje de error sin codificar de forma rígida una cadena.  Esto permite que el código siga siendo correcto al refactorizarlo.  Esta característica también es útil para enlazar los vínculos MVC del controlador de vista de modelos y desencadenar eventos de propiedad cambiada.

[Interpolación de cadenas](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)

Puede usar expresiones de interpolación de cadenas para construir cadenas.  Una expresión de cadena interpolada es similar a una cadena de plantilla que contiene expresiones.  Una cadena interpolada es más fácil de entender con respecto a los argumentos que el [formato compuesto](../../standard/base-types/composite-formatting.md).

[Acceso a miembros condicionales NULL e indexación](../language-reference/operators/null-conditional-operators.md)

Puede probar si hay valores null de forma sintáctica ligera antes de realizar una operación de acceso a miembros (`?.`) o índice (`?[]`).  Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.  Si la referencia de objeto u operando izquierdo es null, la operación devuelve null.

[Literales de cadena multilínea](../../visual-basic/programming-guide/language-features/strings/string-basics.md)

Los literales de cadena pueden contener secuencias de nueva línea.  Ya no necesita la antigua solución alternativa que consistía en usar `<xml><![CDATA[...text with newlines...]]></xml>.Value`

**Comentarios**

Puede colocar comentarios después de las continuaciones de línea implícita, dentro de expresiones de inicializador y entre los términos de la expresión LINQ.

**Resolución de nombres completos más inteligente**

Dado código como `Threading.Thread.Sleep(1000)`, Visual Basic solía buscar el espacio de nombres "Threading", detectaba ambigüedad entre System.Threading y System.Windows.Threading y, a continuación, notificaba un error.  Ahora, Visual Basic considera juntos ambos espacios de nombres posibles.  Si aparece la lista de finalización, el editor de Visual Studio muestra los miembros de ambos tipos en la lista de finalización.

**Literales de fecha con el año en primer lugar**

Puede tener literales de fecha en el formato aaaa-mm-dd, `#2015-03-17 16:10 PM#`.

**Propiedades de interfaz de solo lectura**

Puede implementar propiedades de interfaz de solo lectura mediante una propiedad de lectura y escritura. La interfaz garantiza una funcionalidad mínima y no impide que una clase de implementación pueda establecer la propiedad.

[TypeOf \<expr> IsNot \<type>](../../visual-basic/language-reference/operators/typeof-operator.md)

Para mejorar la legibilidad del código, ahora puede usar `TypeOf` con `IsNot`.

[#Disable Warning \<ID> y #Enable Warning \<ID>](../../visual-basic/language-reference/directives/index.md)

Puede deshabilitar y habilitar advertencias específicas para las regiones dentro de un archivo de origen.

**Mejoras de comentarios de documento XML**

Al escribir comentarios de documento, obtiene compatibilidad inteligente de editor y compilación para validar nombres de parámetro, controlar adecuadamente `crefs` (genéricos, operadores, etc.), colorear y refactorizar.

[Definiciones de módulo parcial e interfaz](../../visual-basic/language-reference/modifiers/partial.md)

Además de clases y structs, puede declarar módulos parciales e interfaces.

[Directivas #Region dentro de cuerpos de método](../../visual-basic/language-reference/directives/region-directive.md)

Puede colocar delimitadores #Region... #End Region en cualquier parte de un archivo, dentro de funciones e incluso abarcando los cuerpos de función.

[Las definiciones de invalidaciones son implícitamente sobrecargas](../../visual-basic/language-reference/modifiers/overrides.md)

Si agrega el modificador `Overrides` a una definición, el compilador agrega implícitamente `Overloads`, de modo que pueda escribir menos código en los casos comunes.

**CObj permitido en argumentos de atributos**

El compilador solía producir un error advirtiendo de que CObj(...) no era una constante cuando se usaba en construcciones de atributo.

**Declaración y consumo de métodos ambiguos desde otras interfaces**

Anteriormente, en el código siguiente producía errores que impedían declarar `IMock` o llamar a `GetDetails` (si estos se habían declarado en C#):

```vb
Interface ICustomer
  Sub GetDetails(x As Integer)
End Interface

Interface ITime
  Sub GetDetails(x As String)
End Interface

Interface IMock : Inherits ICustomer, ITime
  Overloads Sub GetDetails(x As Char)
End Interface

Interface IMock2 : Inherits ICustomer, ITime
End Interface
```

Ahora el compilador usa las reglas de resolución de sobrecarga normales para elegir el `GetDetails` más apropiado que se va a llamar, y se pueden declarar relaciones de interfaz en Visual Basic como las que se muestran en el ejemplo.

## <a name="see-also"></a>Vea también

- [Novedades de Visual Studio 2017](/visualstudio/ide/whats-new-visual-studio-2017)
- [Novedades de Visual Studio 2019](/visualstudio/ide/whats-new-visual-studio-2019)
