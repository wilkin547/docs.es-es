---
title: Managed Extensibility Framework (MEF)
description: Explore Managed Extensibility Framework (MEF), que permite a los desarrolladores de aplicaciones detectar y usar extensiones sin configuración en .NET 4 o superior.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Managed Extensibility Framework, overview
- MEF, overview
ms.assetid: 6c61b4ec-c6df-4651-80f1-4854f8b14dde
ms.openlocfilehash: 00ed48f2202d4c04039ac264b1fe71474a02432e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281256"
---
# <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)

En este tema se proporciona información general sobre la biblioteca Managed Extensibility Framework incluida en .NET Framework 4.

## <a name="what-is-mef"></a>¿Qué es MEF?

Managed Extensibility Framework o MEF es una biblioteca para crear aplicaciones ligeras y extensibles. Permite a los desarrolladores de aplicaciones detectar y utilizar extensiones sin requisitos de configuración. También permite a los desarrolladores de extensiones encapsular código con facilidad y evitar dependencias lógicas frágiles. MEF no solo permite reutilizar extensiones dentro de las aplicaciones sino también entre aplicaciones.

## <a name="the-problem-of-extensibility"></a>El problema de la extensibilidad

Imagine que es el arquitecto de una aplicación grande que debe admitir la extensibilidad. Su aplicación tiene que incluir un número potencialmente grande de componentes menores, y es responsable de crearlos y ejecutarlos.

El enfoque más sencillo es incluir los componentes como código fuente en su aplicación y llamarlos directamente desde el código. Esto tiene varias desventajas obvias. Mucho más importante es que no puede agregar nuevos componentes sin modificar el código fuente, una restricción que podría ser aceptable en una aplicación web, pero que no es viable en una aplicación cliente. Igualmente problemático es que podría no tener acceso al código fuente de los componentes, porque tal vez haya sido desarrollado por terceros y, por la misma razón, no puede permitirles acceder al suyo.

Un enfoque ligeramente más sofisticado sería proporcionar un punto de extensión o interfaz para permitir la desasociación entre la aplicación y sus componentes. Con este modelo, podría proporcionar una interfaz que un componente pueda implementar, y una API para que pueda interactuar con su aplicación. Así se resuelve el problema del acceso al código fuente, pero todavía presenta dificultades.

Dado que a la aplicación le falta la capacidad para detectar los componentes por sí misma, se debe indicar explícitamente qué componentes están disponibles y deben cargarse. Por lo general, esto se logra registrando explícitamente los componentes disponibles en un archivo de configuración. Esto significa que asegurar que los componentes sean correctos se convierte en una cuestión de mantenimiento, especialmente si usted es el usuario final y no el desarrollador que se espera que haga la actualización.

Además, los componentes no pueden comunicarse entre sí, excepto a través de los canales estrictamente definidos en el código de la propia aplicación. Si el arquitecto de la aplicación no ha previsto la necesidad de una comunicación determinada, normalmente es imposible.

Por último, los desarrolladores de componentes deben aceptar una dependencia fuerte en el ensamblado que contiene la interfaz que implementan. Esto dificulta que un componente se use en más de una aplicación y también puede crear problemas cuando se crea un marco de pruebas para los componentes.

## <a name="what-mef-provides"></a>Qué proporciona MEF

En lugar de este registro explícito de componentes disponibles, MEF proporciona una manera de detectarlos implícitamente, mediante la *composición*. Un componente MEF, denominado *elemento*, especifica mediante declaración tanto sus dependencias (conocidas como *importaciones*) como qué funcionalidades (conocidas como *exportaciones*) están disponibles. Cuando se crea un elemento, el motor de composición de MEF cubre sus importaciones con lo que está disponible en otros elementos.

Este enfoque resuelve los problemas comentados en la sección anterior. Dado que los elementos MEF especifican sus funcionalidades mediante declaración, son reconocibles en tiempo de ejecución, lo que significa que una aplicación puede utilizar elementos sin referencias incluidas en el código o archivos de configuración frágiles. MEF permite a las aplicaciones detectar y examinar elementos por sus metadatos, sin crear instancias ni cargar sus ensamblados. Por consiguiente, no hay necesidad de especificar meticulosamente cuándo y cómo deben cargarse las extensiones.

Además de las exportaciones proporcionadas, un elemento puede especificar las importaciones, que serán completadas por otros elementos. Esto hace que la comunicación entre los elementos sea posible además de sencilla y permite una buena factorización del código. Por ejemplo, los servicios comunes a muchos componentes se pueden tener en cuenta en un elemento independiente, para modificarlos o reemplazarlos con facilidad.

Dado que el modelo MEF no requiere dependencias lógicas en un ensamblado de aplicación determinado, permite reutilizar las extensiones entre una aplicación y otra. Esto también facilita el desarrollo de un agente de prueba, independiente de la aplicación, para probar los componentes de extensión.

Una aplicación extensible escrita con MEF declara una importación que los componentes de extensión pueden completar y también puede declarar exportaciones para exponer servicios de aplicación a extensiones. Cada componente de extensión declara una exportación y también puede declarar importaciones. De esta manera, los componentes de extensión son automáticamente extensibles.

## <a name="where-mef-is-available"></a>Dónde está disponible MEF

MEF es una parte integral de .NET Framework 4 y está disponible dondequiera que se use .NET Framework. Puede utilizar MEF en aplicaciones cliente, que usen Windows Forms, WPF o cualquier otra tecnología, o en aplicaciones servidor que usen ASP.NET.

## <a name="mef-and-maf"></a>MEF y MAF

En versiones anteriores de .NET Framework se presentó Managed Add-in Framework (MAF), diseñado para permitir a las aplicaciones aislar y administrar extensiones. MAF se centra en un nivel ligeramente más alto que MEF y se concentra en el aislamiento de la extensión y la carga y descarga del ensamblado, mientras que MEF se centra en la detectabilidad, extensibilidad y portabilidad. Los dos marcos interoperan fácilmente y una aplicación única puede aprovecharse de ambos.

## <a name="simplecalculator-an-example-application"></a>SimpleCalculator: ejemplo de aplicación

La manera más sencilla de ver qué puede hacer MEF es compilar una aplicación sencilla con él. En este ejemplo, compilará una calculadora muy sencilla denominada SimpleCalculator. El objetivo de SimpleCalculator es crear una aplicación de consola que acepte comandos aritméticos básicos, con el formato "5+3" ó "6-2", y devuelva respuestas correctas. Con MEF, podrá agregar nuevos operadores sin cambiar el código de la aplicación.

Para descargar el código completo de este ejemplo, vea [Ejemplo SimpleCalculator (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/simple-calculator-vb/).

> [!NOTE]
> La finalidad de SimpleCalculator es mostrar los conceptos y la sintaxis de MEF, más que proporcionar un escenario realista para su uso. Muchas de las aplicaciones que más se beneficiarían de todo lo que MEF puede ofrecer son más complejas que SimpleCalculator. Para obtener ejemplos más exhaustivos, consulte [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) en GitHub.

- Para empezar, en Visual Studio, cree un proyecto de Aplicación de consola y asígnele el nombre `SimpleCalculator`.

- Agregue una referencia al ensamblado `System.ComponentModel.Composition`, donde se encuentra MEF.

- Abra *Module1.vb* o *Program.cs*, y agregue instrucciones `Imports` o `using` para `System.ComponentModel.Composition` y `System.ComponentModel.Composition.Hosting`. Estos dos espacios de nombres contienen tipos MEF que necesitará para desarrollar una aplicación extensible.

- Si usa Visual Basic, agregue la palabra clave `Public` a la línea que declara el módulo `Module1`.

## <a name="composition-container-and-catalogs"></a>Contenedor de composición y catálogos

El núcleo del modelo de composición de MEF es el *contenedor de composición*, que contiene todos los elementos disponibles y realiza la composición. La composición es la concordancia de importaciones y exportaciones. El tipo más común de contenedor de composición es <xref:System.ComponentModel.Composition.Hosting.CompositionContainer> y lo utilizará en SimpleCalculator.

Si usa Visual Basic, agregue una clase pública denominada `Program` en *Module1.vb*.

Agregue la línea siguiente a la clase `Program` en *Module1.vb* o *Program.cs*:

```vb
Dim _container As CompositionContainer
```

```csharp
private CompositionContainer _container;
```

Para detectar los elementos disponibles, el contenedor de composición usa un *catálogo*. Un catálogo es un objeto que hace que los elementos disponibles se detecten en algún origen. MEF proporciona catálogos para detectar las partes de un tipo, un ensamblado o un directorio suministrado. Los desarrolladores de aplicaciones pueden crear fácilmente nuevos catálogos para detectar partes de otros orígenes, como un servicio web.

Agregue el siguiente constructor a la clase `Program`:

```vb
Public Sub New()
    ' An aggregate catalog that combines multiple catalogs.
     Dim catalog = New AggregateCatalog()

    ' Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(New AssemblyCatalog(GetType(Program).Assembly))

    ' Create the CompositionContainer with the parts in the catalog.
    _container = New CompositionContainer(catalog)

    ' Fill the imports of this object.
    Try
        _container.ComposeParts(Me)
    Catch ex As CompositionException
        Console.WriteLine(ex.ToString)
    End Try
End Sub
```

```csharp
private Program()
{
    // An aggregate catalog that combines multiple catalogs.
    var catalog = new AggregateCatalog();
    // Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(new AssemblyCatalog(typeof(Program).Assembly));

    // Create the CompositionContainer with the parts in the catalog.
    _container = new CompositionContainer(catalog);

    // Fill the imports of this object.
    try
    {
        this._container.ComposeParts(this);
    }
    catch (CompositionException compositionException)
    {
        Console.WriteLine(compositionException.ToString());
   }
}
```

La llamada a <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> indica al contenedor de composición que cree un conjunto específico de elementos, en este caso la instancia actual de `Program`. En este punto, sin embargo, no sucederá nada, dado que `Program` no tiene importaciones que completar.

## <a name="imports-and-exports-with-attributes"></a>Importaciones y exportaciones con atributos

En primer lugar, haga que `Program` importe una calculadora. Esto permite la separación de los problemas de la interfaz de usuario, como la entrada y salida de consola que irá a `Program`, de la lógica de la calculadora.

Agregue el código siguiente a la clase `Program`:

```vb
<Import(GetType(ICalculator))>
Public Property calculator As ICalculator
```

```csharp
[Import(typeof(ICalculator))]
public ICalculator calculator;
```

Observe que la declaración del objeto `calculator` no es inusual, pero se decora con el atributo <xref:System.ComponentModel.Composition.ImportAttribute>. Este atributo declara que algo es una importación, es decir, el motor de la composición la completará cuando se cree el objeto.

Cada importación tiene un *contrato* que determina con qué exportaciones coincidirá. El contrato puede ser una cadena especificada explícitamente o MEF puede generarla automáticamente a partir de un tipo determinado, en este caso la interfaz `ICalculator`. Cualquier exportación declarada con un contrato coincidente completará esta importación. Tenga en cuenta que mientras el tipo del objeto `calculator` sea de hecho `ICalculator`, esto no es necesario. El contrato es independiente del tipo del objeto de importación. (En este caso, podría omitir `typeof(ICalculator)`. MEF adoptará automáticamente el contrato que se va a basar en el tipo de importación, a menos que lo especifique explícitamente).

Agregue esta sencilla interfaz al módulo o al espacio de nombres `SimpleCalculator`:

```vb
Public Interface ICalculator
    Function Calculate(input As String) As String
End Interface
```

```csharp
public interface ICalculator
{
    String Calculate(String input);
}
```

Ahora que ha definido `ICalculator`, necesita una clase que lo implemente. Agregue la siguiente clase al módulo o al espacio de nombres `SimpleCalculator`:

```vb
<Export(GetType(ICalculator))>
Public Class MySimpleCalculator
   Implements ICalculator

End Class
```

```csharp
[Export(typeof(ICalculator))]
class MySimpleCalculator : ICalculator
{

}
```

Aquí está la exportación que coincidirá con la importación en `Program`. Para que la exportación coincida con la importación, la exportación debe tener el mismo contrato. La exportación sujeta a un contrato basado en `typeof(MySimpleCalculator)` generará una desigualdad y no se completará la importación; el contrato debe coincidir exactamente.

Puesto que el contenedor de composición se rellenará con todos los elementos disponibles de este ensamblado, el elemento `MySimpleCalculator` estará disponible. Cuando el constructor `Program` realiza la composición en el objeto `Program`, su importación se completará con un objeto `MySimpleCalculator`, que se creará con ese fin.

La capa de interfaz de usuario (`Program`) no necesita más información. Por tanto, puede rellenar el resto de la lógica de la interfaz de usuario en el método `Main`.

Agregue el código siguiente al método `Main`:

```vb
Sub Main()
    ' Composition is performed in the constructor.
    Dim p As New Program()
    Dim s As String
    Console.WriteLine("Enter Command:")
    While (True)
        s = Console.ReadLine()
        Console.WriteLine(p.calculator.Calculate(s))
    End While
End Sub
```

```csharp
static void Main(string[] args)
{
    // Composition is performed in the constructor.
    var p = new Program();
    string s;
    Console.WriteLine("Enter Command:");
    while (true)
    {
        s = Console.ReadLine();
        Console.WriteLine(p.calculator.Calculate(s));
    }
}
```

 Este código simplemente lee una línea de entrada y llama a la función `Calculate` de `ICalculator` en el resultado, que lo vuelve a escribir en la consola. Ese es todo el código que necesita en `Program`. El resto del trabajo se hará en los elementos.

## <a name="further-imports-and-importmany"></a>Más importaciones e ImportMany

Para que SimpleCalculator sea extensible, necesita importar una lista de operaciones. Un atributo <xref:System.ComponentModel.Composition.ImportAttribute> ordinario lo completa un atributo <xref:System.ComponentModel.Composition.ExportAttribute> y solo uno. Si hay más de uno disponible, el motor de la composición genera un error. Para crear una importación que pueda ser completada por cualquier número de exportaciones, puede usar el atributo <xref:System.ComponentModel.Composition.ImportManyAttribute>.

Agregue la siguiente propiedad de operaciones a la clase `MySimpleCalculator`:

```vb
<ImportMany()>
Public Property operations As IEnumerable(Of Lazy(Of IOperation, IOperationData))
```

```csharp
[ImportMany]
IEnumerable<Lazy<IOperation, IOperationData>> operations;
```

<xref:System.Lazy%602> es un tipo de colección proporcionado por MEF que contiene referencias indirectas a las exportaciones. Aquí, además del propio objeto exportado, también obtiene los *metadatos de la exportación* o información que describe el objeto exportado. Cada colección <xref:System.Lazy%602> contiene un objeto `IOperation`, que representa una operación real, y un objeto `IOperationData`, que representa sus metadatos.

Agregue estas sencillas interfaces al módulo o al espacio de nombres `SimpleCalculator`:

```vb
Public Interface IOperation
    Function Operate(left As Integer, right As Integer) As Integer
End Interface

Public Interface IOperationData
    ReadOnly Property Symbol As Char
End Interface
```

```csharp
public interface IOperation
{
     int Operate(int left, int right);
}

public interface IOperationData
{
    Char Symbol { get; }
}
```

 En este caso, los metadatos de cada operación son el símbolo que representa esa operación, como +, -, \*, etc. Para que la operación de suma esté disponible, agregue la siguiente clase al módulo o al espacio de nombres `SimpleCalculator`:

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "+"c)>
Public Class Add
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left + right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '+')]
class Add: IOperation
{
    public int Operate(int left, int right)
    {
        return left + right;
    }
}
```

El atributo <xref:System.ComponentModel.Composition.ExportAttribute> funciona igual que antes. El atributo <xref:System.ComponentModel.Composition.ExportMetadataAttribute> adjunta metadatos, con formato de un par nombre-valor, a esa exportación. Mientras que la clase `Add` implementa `IOperation`, no se define explícitamente una clase que implementa `IOperationData`. En su lugar, MEF crea implícitamente una clase con propiedades basadas en los nombres de los metadatos proporcionados. (Esta es una de las maneras de acceder a los metadatos en MEF).

La composición en MEF es *recursiva*. Compuso el objeto `Program` explícitamente, que importó un `ICalculator` que resultó ser del tipo `MySimpleCalculator`. A su vez, `MySimpleCalculator` importa una colección de objetos `IOperation` y se completará cuando se cree `MySimpleCalculator`, al mismo tiempo que las importaciones de `Program`. Si la clase `Add` declarara una importación más extensa, también tendría que completarse, y así sucesivamente. Toda importación que quede incompleta dará error en la composición. (Es posible, sin embargo, declarar las importaciones para que sean opcionales o asignarles valores predeterminados).

## <a name="calculator-logic"></a>Lógica de calculadora

Con estos componentes bien establecidos, todo lo que queda es la propia lógica de la calculadora. Agregue el código siguiente a la clase `MySimpleCalculator` para implementar el método `Calculate`:

```vb
Public Function Calculate(input As String) As String Implements ICalculator.Calculate
    Dim left, right As Integer
    Dim operation As Char
    ' Finds the operator.
    Dim fn = FindFirstNonDigit(input)
    If fn < 0 Then
        Return "Could not parse command."
    End If
    operation = input(fn)
    Try
        ' Separate out the operands.
        left = Integer.Parse(input.Substring(0, fn))
        right = Integer.Parse(input.Substring(fn + 1))
    Catch ex As Exception
        Return "Could not parse command."
    End Try
    For Each i As Lazy(Of IOperation, IOperationData) In operations
        If i.Metadata.symbol = operation Then
            Return i.Value.Operate(left, right).ToString()
        End If
    Next
    Return "Operation not found!"
End Function
```

```csharp
public String Calculate(string input)
{
    int left;
    int right;
    char operation;
    // Finds the operator.
    int fn = FindFirstNonDigit(input);
    if (fn < 0) return "Could not parse command.";

    try
    {
        // Separate out the operands.
        left = int.Parse(input.Substring(0, fn));
        right = int.Parse(input.Substring(fn + 1));
    }
    catch
    {
        return "Could not parse command.";
    }

    operation = input[fn];

    foreach (Lazy<IOperation, IOperationData> i in operations)
    {
        if (i.Metadata.Symbol.Equals(operation)) return i.Value.Operate(left, right).ToString();
    }
    return "Operation Not Found!";
}
```

Los pasos iniciales analizan la cadena de entrada en los operandos izquierdo y derecho, y un carácter de operador. En el bucle de `foreach`, se examina cada miembro de la colección `operations`. Estos objetos son de tipo <xref:System.Lazy%602>; se puede acceder a los valores de sus metadatos y al objeto exportado con las propiedades <xref:System.Lazy%602.Metadata%2A> y <xref:System.Lazy%601.Value%2A>, respectivamente. En este caso, si la propiedad `Symbol` del objeto `IOperationData` se detecta como una coincidencia, la calculadora llama al método `Operate` del objeto `IOperation` y devuelve el resultado.

Para completar la calculadora, también necesita un método del asistente que devuelve la posición del primer carácter de una cadena que no sea un dígito. Agregue el método del asistente siguiente a la clase `MySimpleCalculator`:

```vb
Private Function FindFirstNonDigit(s As String) As Integer
    For i = 0 To s.Length - 1
        If Not Char.IsDigit(s(i)) Then Return i
    Next
    Return -1
End Function
```

```csharp
private int FindFirstNonDigit(string s)
{
    for (int i = 0; i < s.Length; i++)
    {
        if (!Char.IsDigit(s[i])) return i;
    }
    return -1;
}
```

A partir de este momento, podrá compilar y ejecutar el proyecto. En Visual Basic, asegúrese de que ha agregado la palabra clave `Public` a `Module1`. En la ventana de consola, escriba una operación de suma, como "5+3", y la calculadora devolverá los resultados. Cualquier otro operador dará como resultado el mensaje "Operación no encontrada".

## <a name="extending-simplecalculator-using-a-new-class"></a>Extensión de SimpleCalculator mediante una clase nueva

Ahora que la calculadora funciona, agregar una nueva operación es fácil. Agregue la siguiente clase al módulo o al espacio de nombres `SimpleCalculator`:

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "-"c)>
Public Class Subtract
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left - right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '-')]
class Subtract : IOperation
{
    public int Operate(int left, int right)
    {
        return left - right;
    }
}
```

Compile y ejecute el proyecto. Escriba una operación de resta, como "5-3". La calculadora admite ahora la resta además de la suma.

## <a name="extending-simplecalculator-using-a-new-assembly"></a>Extensión de SimpleCalculator con un ensamblado nuevo

Agregar clases al código fuente es bastante sencillo, pero MEF permite buscar elementos fuera del propio origen de una aplicación. Para demostrar esto, necesitará modificar SimpleCalculator para que busque los elementos en un directorio y en su propio ensamblado agregando <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.

Agregue un directorio denominado `Extensions` al proyecto SimpleCalculator. Asegúrese de agregarlo en el nivel del proyecto y no en el nivel de la solución. Después agregue a la solución un proyecto de biblioteca de clases denominado `ExtendedOperations`. El nuevo proyecto se compilará en un ensamblado independiente.

Abra el diseñador de propiedades de proyectos para el proyecto ExtendedOperations y haga clic en la pestaña **Compilar** o **Compilación**. Cambie **Ruta de acceso de los resultados de la compilación** o **Ruta de acceso de salida** para que apunte al directorio Extensions del directorio del proyecto SimpleCalculator ( *..\SimpleCalculator\Extensions\\* ).

 En *Module1.vb* o *Program.cs*, agregue la línea siguiente al constructor de `Program`:

```vb
catalog.Catalogs.Add(New DirectoryCatalog("C:\SimpleCalculator\SimpleCalculator\Extensions"))
```

```csharp
catalog.Catalogs.Add(new DirectoryCatalog("C:\\SimpleCalculator\\SimpleCalculator\\Extensions"));
```

Reemplace la ruta de acceso del ejemplo por la ruta de acceso del directorio Extensions. (Esta ruta de acceso absoluta es para fines de depuración solamente. En una aplicación de producción, usaría una ruta de acceso relativa). <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> ahora agregará los elementos encontrados en cualquier ensamblado del directorio Extensions al contenedor de composición.

En el proyecto ExtendedOperations, agregue referencias a SimpleCalculator y System.ComponentModel.Composition. En el archivo de clase ExtendedOperations, agregue una instrucción `Imports` o `using` para System.ComponentModel.Composition. En Visual Basic, agregue también una instrucción `Imports` para SimpleCalculator. Después, agregue la clase siguiente al archivo de clase ExtendedOperations:

```vb
<Export(GetType(SimpleCalculator.IOperation))>
<ExportMetadata("Symbol", "%"c)>
Public Class Modulo
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left Mod right
    End Function
End Class
```

```csharp
[Export(typeof(SimpleCalculator.IOperation))]
[ExportMetadata("Symbol", '%')]
public class Mod : SimpleCalculator.IOperation
{
    public int Operate(int left, int right)
    {
        return left % right;
    }
}
```

Tenga en cuenta que para que el contrato coincida, el atributo <xref:System.ComponentModel.Composition.ExportAttribute> debe tener el mismo tipo que <xref:System.ComponentModel.Composition.ImportAttribute>.

Compile y ejecute el proyecto. Pruebe el nuevo operador Mod (%).

## <a name="conclusion"></a>Conclusión

En este tema se han tratado los conceptos básicos de MEF.

- Elementos, catálogos y el contenedor de composición

     Los elementos y el contenedor de composición son los pilares fundamentales de una aplicación MEF. Un elemento es cualquier objeto que importa o exporta un valor, hasta sí mismo incluido. Un catálogo proporciona una colección de elementos de un origen determinado. El contenedor de composición utiliza los elementos proporcionados por un catálogo para realizar la composición, el enlace de las importaciones a las exportaciones.

- Importaciones y exportaciones

     Las importaciones y las exportaciones son la manera en la que los componentes se comunican. Con una importación, el componente especifica la necesidad de un valor u objeto determinado, y con una exportación se especifica la disponibilidad de un valor. Cada importación coincide con una lista de exportaciones por medio de su contrato.

## <a name="next-steps"></a>Pasos siguientes

Para descargar el código completo de este ejemplo, vea [Ejemplo SimpleCalculator (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/simple-calculator-vb/).

 Para más información y ejemplos de código, vea [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef). Para obtener una lista de los tipos de MEF, vea el espacio de nombres <xref:System.ComponentModel.Composition?displayProperty=nameWithType>.
