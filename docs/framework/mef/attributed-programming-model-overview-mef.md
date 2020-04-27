---
title: Información general del modelo de programación con atributos (MEF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MEF, attributed programming model
- attributed programming model [MEF]
ms.assetid: 49b787ff-2741-4836-ad51-c3017dc592d4
ms.openlocfilehash: c6b1093d2e821a55cc5513b077a270748a780b71
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347626"
---
# <a name="attributed-programming-model-overview-mef"></a>Información general del modelo de programación con atributos (MEF)

En Managed Extensibility Framework (MEF), un *modelo de programación* es una manera específica de definir el conjunto de objetos conceptuales en los que opera MEF. Estos objetos conceptuales incluyen partes, importaciones y exportaciones. MEF utiliza estos objetos, pero no especifica cómo se deben representar. Por consiguiente, es posible una gran variedad de modelos de programación, incluidos modelos personalizados.

El modelo de programación predeterminado utilizado en MEF es el *modelo de programación con atributos*. En el modelo de programación con atributos se definen las partes, las importaciones, las exportaciones y otros objetos con atributos que decoran las clases de .NET Framework normales. En este tema se explica cómo utilizar los atributos que proporciona el modelo de programación con atributos para crear una aplicación MEF.

<a name="import_and_export_basics"></a>

## <a name="import-and-export-basics"></a>Conceptos básicos sobre importaciones y exportaciones

Una *exportación* es un valor que una parte proporciona a otras partes del contenedor y una *importación* es un requisito que una parte especifica al contenedor, y que se debe satisfacer con las exportaciones disponibles. En el modelo de programación con atributos, las importaciones y exportaciones se declaran decorando clases o miembros con atributos `Import` e `Export` . El atributo `Export` puede decorar una clase, campo, propiedad o método, mientras que el atributo `Import` puede decorar un campo, propiedad o parámetro de constructor.

Para que una importación pueda coincidir con una exportación, ambas deben tener el mismo *contrato*. El contrato está compuesto de una cadena, llamada *nombre del contrato*, y el tipo del objeto exportado o importado, denominado *tipo del contrato*. Solo si el nombre del contrato y el tipo del contrato coinciden se considera que una exportación satisface una importación determinada.

Cualquiera de los parámetros del contrato (o ambos) puede ser implícito o explícito. El siguiente código muestra una clase que declara una importación básica.

```vb
Public Class MyClass1
    <Import()>
    Public Property MyAddin As IMyAddin
End Class
```

```csharp
public class MyClass
{
    [Import]
    public IMyAddin MyAddin { get; set; }
}
```

En esta importación, el atributo `Import` no tiene un tipo de contrato ni un parámetro de nombre de contrato adjunto. Por consiguiente, ambos se deducirán de la propiedad decorada. En este caso, el tipo de contrato será `IMyAddin`y el nombre del contrato será una cadena única creada a partir del tipo de contrato. (Es decir, el nombre del contrato sólo coincidirá con aquellas exportaciones cuyos nombres también se deduzcan del tipo `IMyAddin`.)

A continuación se muestra una exportación que coincide con la importación anterior.

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

En esta exportación, el tipo de contrato es `IMyAddin` porque se especifica como un parámetro del atributo `Export` . El tipo exportado debe ser igual que el tipo de contrato, derivar del tipo de contrato o implementar el tipo del contrato si se trata de una interfaz. En este ejemplo, el tipo `MyLogger` implementa la interfaz `IMyAddin`. El nombre del contrato se deduce del tipo de contrato, lo que significa que esta exportación coincidirá con la importación anterior.

> [!NOTE]
> Las exportaciones y las importaciones se deben declarar en clases o miembros públicos. Se admiten otras declaraciones, pero exportar o importar un miembro privado, protegido o interno rompe el modelo de aislamiento para la parte y, por lo tanto, no se recomienda.

El tipo de contrato debe coincidir exactamente para que se considere que hay una coincidencia en la exportación y la importación. Observe la exportación siguiente.

```vb
<Export()> 'WILL NOT match the previous import!
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export] //WILL NOT match the previous import!
public class MyLogger : IMyAddin { }
```

En esta exportación, el tipo de contrato es `MyLogger` en lugar de `IMyAddin`. Aunque `MyLogger` implementa `IMyAddin`y, por consiguiente, se pudo convertir en un objeto `IMyAddin` , esta exportación no coincidirá con la importación anterior porque los tipos de contrato no coinciden.

En general, no es necesario especificar el nombre del contrato, y la mayoría de los contratos se deberían definir según el tipo de contrato y los metadatos. Sin embargo, en algunas circunstancias, es importante especificar el nombre del contrato directamente. El caso más habitual es cuando una clase exporta varios valores que comparten un tipo común, como los primitivos. El nombre del contrato se puede especificar como el primer parámetro del atributo `Import` o `Export` . El siguiente código muestra una importación y una exportación con un nombre de contrato especificado de `MajorRevision`.

```vb
Public Class MyExportClass

    'This one will match
    <Export("MajorRevision")>
    Public ReadOnly Property MajorRevision As Integer
        Get
            Return 4
        End Get
    End Property

    <Export("MinorRevision")>
    Public ReadOnly Property MinorRevision As Integer
        Get
            Return 16
        End Get
    End Property
End Class
```

```csharp
public class MyClass
{
    [Import("MajorRevision")]
    public int MajorRevision { get; set; }
}

public class MyExportClass
{
    [Export("MajorRevision")] //This one will match.
    public int MajorRevision = 4;

    [Export("MinorRevision")]
    public int MinorRevision = 16;
}
```

Si no se especifica el tipo de contrato, se deducirá del tipo de la importación o exportación. Sin embargo, aun cuando explícitamente se especifica el nombre del contrato, el tipo de contrato debe coincidir también exactamente para que se considere que la importación y la exportación coinciden. Por ejemplo, si el campo `MajorRevision` fuera una cadena, los tipos de contrato deducidos no coincidirían y la exportación no coincidiría con la importación, a pesar de tener el mismo nombre de contrato.

### <a name="importing-and-exporting-a-method"></a>Importar y exportar métodos

El atributo `Export` también puede decorar un método, de la misma manera que una clase, propiedad o función. Las exportaciones de métodos deben especificar un tipo o un nombre de contrato, porque el tipo no se puede deducir. El tipo especificado puede ser un delegado personalizado o un tipo genérico, como `Func`. La siguiente clase exporta un método denominado `DoSomething`.

```vb
Public Class MyAddin

    'Explicitly specifying a generic type
    <Export(GetType(Func(Of Integer, String)))>
    Public Function DoSomething(ByVal TheParam As Integer) As String
        Return Nothing 'Function body goes here
    End Function

End Class
```

```csharp
public class MyAddin
{
    //Explicitly specifying a generic type.
    [Export(typeof(Func<int, string>))]
    public string DoSomething(int TheParam);
}
```

En esta clase, el método `DoSomething` toma un parámetro `int` único y devuelve `string`. Para coincidir con esta exportación, la parte de la importación debe declarar un miembro adecuado. La clase siguiente importa el método `DoSomething` .

```vb
Public Class MyClass1

    'Contract name must match!
    <Import()>
    Public Property MajorRevision As Func(Of Integer, String)
End Class
```

```csharp
public class MyClass
{
    [Import] //Contract name must match!
    public Func<int, string> DoSomething { get; set; }
}
```

Para obtener más información sobre cómo utilizar el objeto `Func<T, T>` , vea <xref:System.Func%602>.

<a name="types_of_imports"></a>

## <a name="types-of-imports"></a>Tipos de importaciones

MEF admite varios tipos de importación: dinámica, diferida, de requisito previo y opcional.

### <a name="dynamic-imports"></a>Importaciones dinámicas

En algunos casos, la clase que importa puede querer coincidir con exportaciones de cualquier tipo que tengan un nombre de contrato determinado. En este escenario, la clase puede declarar una *importación dinámica*. La siguiente importación coincide con cualquier exportación que tenga el nombre de contrato "TheString".

```vb
Public Class MyClass1

    <Import("TheString")>
    Public Property MyAddin

End Class
```

```csharp
public class MyClass
{
    [Import("TheString")]
    public dynamic MyAddin { get; set; }
}
```

Cuando el tipo de contrato se deduce de la palabra clave `dynamic` , coincidirá con cualquier tipo de contrato. En este caso, una importación debería especificar **siempre** un nombre de contrato con el que coincidir. (Si no se especifica ningún nombre de contrato, se considerará que la importación no coincide con ninguna exportación). Estas dos exportaciones coincidirían con la importación anterior.

```vb
<Export("TheString", GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class

<Export("TheString")>
Public Class MyToolbar

End Class
```

```csharp
[Export("TheString", typeof(IMyAddin))]
public class MyLogger : IMyAddin { }

[Export("TheString")]
public class MyToolbar { }
```

Obviamente, la clase de importación se debe preparar para tratar con un objeto de tipo arbitrario.

### <a name="lazy-imports"></a>Importaciones diferidas

En algunos casos, la clase de importación puede requerir una referencia indirecta al objeto importado, para que no se creen instancias del objeto inmediatamente. En este escenario, la clase puede declarar una *importación diferida* utilizando un tipo de contrato `Lazy<T>`. La siguiente propiedad de importación declara una importación diferida.

```vb
Public Class MyClass1

    <Import()>
    Public Property MyAddin As Lazy(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [Import]
    public Lazy<IMyAddin> MyAddin { get; set; }
}
```

Desde el punto de vista del motor de composición, un tipo de contrato `Lazy<T>` se considera idéntico al tipo de contrato `T`. Por consiguiente, la importación anterior coincidiría con la siguiente exportación.

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

El nombre de contrato y el tipo de contrato se pueden especificar en el atributo `Import` para una importación diferida, tal y como se describe anteriormente en la sección "Conceptos básicos sobre importaciones y exportaciones".

### <a name="prerequisite-imports"></a>Importaciones de requisito previo

El motor de composición, en respuesta a una solicitud directa o a la necesidad de completar una importación coincidente, crea normalmente las partes de MEF exportadas. De forma predeterminada, al crear una parte, el motor de composición utiliza el constructor sin parámetros. Para que el motor use un constructor diferente, márquelo con el atributo `ImportingConstructor` .

Cada parte solo puede tener un constructor para uso por parte del motor de composición. No proporcionar ningún constructor sin parámetros y ningún atributo `ImportingConstructor`, o proporcionar más de un atributo `ImportingConstructor`, generará un error.

Para completar los parámetros de un constructor marcados con el atributo `ImportingConstructor` , todos esos parámetros se declaran automáticamente como importaciones. Ésta es una manera conveniente de declarar importaciones que se utilizan durante la inicialización de las partes. La siguiente clase utiliza `ImportingConstructor` para declarar una importación.

```vb
Public Class MyClass1

    Private _theAddin As IMyAddin

    'Parameterless constructor will NOT be used
    'because the ImportingConstructor
    'attribute is present.
    Public Sub New()

    End Sub

    'This constructor will be used.
    'An import with contract type IMyAddin
    'is declared automatically.
    <ImportingConstructor()>
    Public Sub New(ByVal MyAddin As IMyAddin)
        _theAddin = MyAddin
    End Sub

End Class
```

```csharp
public class MyClass
{
    private IMyAddin _theAddin;

    //Parameterless constructor will NOT be
    //used because the ImportingConstructor
    //attribute is present.
    public MyClass() { }

    //This constructor will be used.
    //An import with contract type IMyAddin is
    //declared automatically.
    [ImportingConstructor]
    public MyClass(IMyAddin MyAddin)
    {
        _theAddin = MyAddin;
    }
}
```

De forma predeterminada, el atributo `ImportingConstructor` usa tipos de contrato y nombres de contrato deducidos para todas las importaciones de parámetros. Es posible reemplazar esto decorando los parámetros con atributos `Import` , que pueden definir después explícitamente el tipo y el nombre del contrato. El siguiente código muestra un constructor que utiliza esta sintaxis para importar una clase derivada en lugar de una clase principal.

```vb
<ImportingConstructor()>
Public Sub New(<Import(GetType(IMySubAddin))> ByVal MyAddin As IMyAddin)

End Sub
```

```csharp
[ImportingConstructor]
public MyClass([Import(typeof(IMySubAddin))]IMyAddin MyAddin)
{
    _theAddin = MyAddin;
}
```

En concreto, debería tener precaución con los parámetros de colección. Por ejemplo, si especifica `ImportingConstructor` en un constructor con un parámetro de tipo `IEnumerable<int>`, la importación coincidirá con una exportación única de tipo `IEnumerable<int>`, en lugar de con un conjunto de exportaciones de tipo `int`. Para coincidir con un conjunto de exportaciones de tipo `int`, tiene que decorar el parámetro con el atributo `ImportMany` .

Los parámetros declarados como importaciones por el atributo `ImportingConstructor` también se marcan como *importaciones de requisito previo*. Normalmente MEF permite que las exportaciones e importaciones formen un *ciclo*. Por ejemplo, un ciclo es donde el objeto A importa un objeto B, que a su vez importa el objeto A. En circunstancias normales, un ciclo no es un problema y el contenedor de composición construye ambos objetos normalmente.

Cuando el constructor de una parte requiere un valor importado, ese objeto no puede participar en un ciclo. Si el objeto A requiere para poder construirse que antes se construya ese objeto B, y el objeto B importa el objeto A, el ciclo no se podrá resolver y se producirá un error de composición. Las importaciones declaradas en parámetros de constructor son, por consiguiente, importaciones de requisito previo, las cuales deben completarse para que las exportaciones del objeto que las requiere se puedan utilizar.

### <a name="optional-imports"></a>Importaciones opcionales

El atributo `Import` especifica un requisito para que la parte funcione. Si no se puede satisfacer una importación, se producirá un error en la composición de esa parte, que no estará disponible.

Puede especificar que una importación sea *opcional* utilizando la propiedad `AllowDefault` . En este caso, la composición tendrá éxito aun cuando la importación no coincida con las exportaciones disponibles, y la propiedad de importación estará establecida en el valor predeterminado para su tipo de propiedad (`null` para las propiedades de objeto, `false` para valores booleanos o cero para las propiedades numéricas). La siguiente clase utiliza una importación opcional.

```vb
Public Class MyClass1

    <Import(AllowDefault:=True)>
    Public Property thePlugin As Plugin

    'If no matching export is available,
    'thePlugin will be set to null.
End Class
```

```csharp
public class MyClass
{
    [Import(AllowDefault = true)]
    public Plugin thePlugin { get; set; }

    //If no matching export is available,
    //thePlugin will be set to null.
}
```

### <a name="importing-multiple-objects"></a>Importar varios objetos

Se creará el atributo `Import` correctamente solo cuando coincida con una y solo una exportación. En otros casos se generará un error de composición. Para importar más de una exportación que coincida con el mismo contrato, utilice el atributo `ImportMany` . Las importaciones marcadas con este atributo son siempre opcionales. Por ejemplo, no se producirá un error en la composición si no hay ninguna exportación coincidente presente. La siguiente clase importa cualquier número de exportaciones de tipo `IMyAddin`.

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<IMyAddin> MyAddin { get; set; }
}
```

Se puede tener acceso a la matriz importada con métodos y sintaxis `IEnumerable<T>` normales. También es posible utilizar una matriz normal (`IMyAddin[]`) en su lugar.

Este modelo puede ser muy importante si se usa en combinación con la sintaxis `Lazy<T>` . Por ejemplo, utilizando `ImportMany`, `IEnumerable<T>`y `Lazy<T>`, puede importar las referencias indirectas a cualquier número de objetos y crear instancias de los que resultan necesarios únicamente. La siguiente clase muestra este modelo.

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of Lazy(Of IMyAddin))

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<Lazy<IMyAddin>> MyAddin { get; set; }
}
```

<a name="avoiding_discovery"></a>

## <a name="avoiding-discovery"></a>Evitar la detección

En algunos casos, puede desear evitar que una parte sea detectada como parte de un catálogo. Por ejemplo, la parte puede ser una clase base pensada para que se herede de ella, pero no para usarla. Hay dos maneras de lograrlo. Primero, puede utilizar la palabra clave `abstract` en la clase de la parte. Las clases abstractas nunca proporcionan exportaciones, aunque pueden proporcionar exportaciones heredadas a las clases que derivan de ellas.

Si la clase no se puede hacer abstracta, puede decorarla con el atributo `PartNotDiscoverable` . Una parte decorada con este atributo no estará incluida en ningún catálogo. En el siguiente ejemplo se muestran estos modelos. El catálogo detectará`DataOne` . Puesto que `DataTwo` es abstracta, no se detectará. Puesto que `DataThree` utilizó el atributo `PartNotDiscoverable` , no se detectará.

```vb
<Export()>
Public Class DataOne
    'This part will be discovered
    'as normal by the catalog.
End Class

<Export()>
Public MustInherit Class DataTwo
    'This part will not be discovered
    'by the catalog.
End Class

<PartNotDiscoverable()>
<Export()>
Public Class DataThree
    'This part will also not be discovered
    'by the catalog.
End Class
```

```csharp
[Export]
public class DataOne
{
    //This part will be discovered
    //as normal by the catalog.
}

[Export]
public abstract class DataTwo
{
    //This part will not be discovered
    //by the catalog.
}

[PartNotDiscoverable]
[Export]
public class DataThree
{
    //This part will also not be discovered
    //by the catalog.
}
```

<a name="metadata_and_metadata_views"></a>

## <a name="metadata-and-metadata-views"></a>Metadatos y vistas de metadatos

Las exportaciones pueden proporcionar información adicional sobre ellas, lo que se conoce como *metadatos*. Los metadatos se pueden utilizar para llevar propiedades del objeto exportado a la parte de importación. La parte de importación puede utilizar estos datos para decidir qué exportaciones usar o recopilar información sobre una exportación sin tener que construirla. Por esta razón, una importación debe ser diferida para utilizar los metadatos.

Para utilizar los metadatos, se declara normalmente una interfaz conocida como *vista de metadatos*, que declara qué metadatos estarán disponibles. La interfaz de vista de los metadatos solo debe tener propiedades y esas propiedades deben tener descriptores de acceso `get` . La siguiente interfaz es ejemplo de una vista de metadatos.

```vb
Public Interface IPluginMetadata

    ReadOnly Property Name As String

    <DefaultValue(1)>
    ReadOnly Property Version As Integer

End Interface
```

```csharp
public interface IPluginMetadata
{
    string Name { get; }

    [DefaultValue(1)]
    int Version { get; }
}
```

También es posible utilizar una colección genérica, `IDictionary<string, object>`, como vista de metadatos, pero esto anula las ventajas de la comprobación de tipos y se debe evitar.

Normalmente, todas las propiedades nombradas en la vista de metadatos son obligatorias y las exportaciones que no las proporcionen no se considerarán una coincidencia. El atributo `DefaultValue` especifica que una propiedad es opcional. Si la propiedad no está incluida, se le asignará el valor predeterminado especificado como un parámetro de `DefaultValue`. A continuación se incluyen dos clases diferentes decoradas con metadatos. Ambas clases coincidirían con la vista de metadatos anterior.

```vb
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class MyLogger
    Implements IPlugin

End Class

'Version is not required because of the DefaultValue
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Disk Writer")>
Public Class DWriter
    Implements IPlugin

End Class
```

```csharp
[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
}

[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Disk Writer")]
    //Version is not required because of the DefaultValue
public class DWriter : IPlugin
{
}
```

Los metadatos se expresan detrás del atributo `Export` mediante el atributo `ExportMetadata` . Cada componente de los metadatos consta de un par de nombre/valor. La parte del nombre de los metadatos debe coincidir con el nombre de la propiedad adecuada en la vista de metadatos y el valor se asignará a esa propiedad.

Es el importador el que especifica qué vista de metadatos se usará, en caso de que se use alguna. Una importación con metadatos se declara como una importación diferida, con la interfaz de metadatos como el segundo parámetro de tipo para `Lazy<T,T>`. La siguiente clase importa la parte anterior con metadatos.

```vb
Public Class Addin

    <Import()>
    Public Property plugin As Lazy(Of IPlugin, IPluginMetadata)
End Class
```

```csharp
public class Addin
{
    [Import]
    public Lazy<IPlugin, IPluginMetadata> plugin;
}
```

En muchos casos, deseará combinar los metadatos con el atributo `ImportMany` , con el fin de analizar las importaciones disponibles y elegir y crear instancias de una sola, o filtrará una colección para que coincida con determinada condición. La siguiente clase únicamente crea instancias de los objetos `IPlugin` que tienen el valor `Name` "Logger".

```vb
Public Class User

    <ImportMany()>
    Public Property plugins As IEnumerable(Of Lazy(Of IPlugin, IPluginMetadata))

    Public Function InstantiateLogger() As IPlugin

        Dim logger As IPlugin
        logger = Nothing

        For Each Plugin As Lazy(Of IPlugin, IPluginMetadata) In plugins
            If Plugin.Metadata.Name = "Logger" Then
                logger = Plugin.Value
            End If
        Next
        Return logger
    End Function

End Class
```

```csharp
public class User
{
    [ImportMany]
    public IEnumerable<Lazy<IPlugin, IPluginMetadata>> plugins;

    public IPlugin InstantiateLogger()
    {
        IPlugin logger = null;

        foreach (Lazy<IPlugin, IPluginMetadata> plugin in plugins)
        {
            if (plugin.Metadata.Name == "Logger")
                logger = plugin.Value;
        }
        return logger;
    }
}
```

<a name="import_and_export_inheritance"></a>

## <a name="import-and-export-inheritance"></a>Herencia de las importaciones y exportaciones

Si una clase hereda de una parte, esa clase también se puede convertir en una parte. Las importaciones siempre son heredadas por las subclases. Por consiguiente, una subclase de una parte siempre será una parte, con las mismas importaciones que su clase primaria.

Las exportaciones declaradas con el atributo `Export` no son heredadas por las subclases. Sin embargo, una parte se puede exportar utilizando el atributo `InheritedExport` . Las subclases de la parte heredarán y proporcionarán la misma exportación, incluido el nombre y el tipo del contrato. A diferencia de un atributo `Export` , `InheritedExport` solo se puede aplicar en el nivel de clase, no en el nivel de miembro. Por consiguiente, las exportaciones de nivel de miembro nunca pueden heredarse.

Las siguientes cuatro clases muestran los principios de la herencia de la importación y la exportación. `NumTwo` hereda de `NumOne`, de modo que `NumTwo` importará `IMyData`. Las exportaciones normales no se heredan, de modo que `NumTwo` no exportará nada. `NumFour` hereda de `NumThree`. Dado que `NumThree` utilizó `InheritedExport`, `NumFour` tiene una exportación con tipo de contrato `NumThree`. Las exportaciones de nivel de miembro nunca se heredan, de modo que `IMyData` no se exporta.

```vb
<Export()>
Public Class NumOne
    <Import()>
    Public Property MyData As IMyData
End Class

Public Class NumTwo
    Inherits NumOne

    'Imports are always inherited, so NumTwo will
    'Import IMyData

    'Ordinary exports are not inherited, so
    'NumTwo will NOT export anything.  As a result it
    'will not be discovered by the catalog!

End Class

<InheritedExport()>
Public Class NumThree

    <Export()>
    Public Property MyData As IMyData

    'This part provides two exports, one of
    'contract type NumThree, and one of
    'contract type IMyData.

End Class

Public Class NumFour
    Inherits NumThree

    'Because NumThree used InheritedExport,
    'this part has one export with contract
    'type NumThree.

    'Member-level exports are never inherited,
    'so IMyData is not exported.

End Class
```

```csharp
[Export]
public class NumOne
{
    [Import]
    public IMyData MyData { get; set; }
}

public class NumTwo : NumOne
{
    //Imports are always inherited, so NumTwo will
    //import IMyData.

    //Ordinary exports are not inherited, so
    //NumTwo will NOT export anything. As a result it
    //will not be discovered by the catalog!
}

[InheritedExport]
public class NumThree
{
    [Export]
    Public IMyData MyData { get; set; }

    //This part provides two exports, one of
    //contract type NumThree, and one of
    //contract type IMyData.
}

public class NumFour : NumThree
{
    //Because NumThree used InheritedExport,
    //this part has one export with contract
    //type NumThree.

    //Member-level exports are never inherited,
    //so IMyData is not exported.
}
```

Si hay metadatos asociados al atributo `InheritedExport` , también se heredarán. (Para obtener más información, vea la sección anterior "Metadatos y vistas de metadatos"). La subclase no puede modificar los metadatos heredados. Sin embargo, si se vuelve a declarar el atributo `InheritedExport` con el mismo nombre y tipo de contrato, pero con nuevos metadatos, la subclase puede reemplazar los metadatos heredados por los nuevos metadatos. La clase siguiente muestra este principio. La parte `MegaLogger` hereda de `Logger` e incluye el atributo `InheritedExport` . Puesto que `MegaLogger` vuelve a declarar nuevos metadatos denominados Status, no hereda los metadatos Name y Version de `Logger`.

```vb
<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class Logger
    Implements IPlugin

    'Exports with contract type IPlugin
    'and metadata "Name" and "Version".
End Class

Public Class SuperLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Name" and "Version", exactly the same
    'as the Logger class.

End Class

<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Status", "Green")>
Public Class MegaLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Status" only. Re-declaring
    'the attribute replaces all metadata.

End Class
```

```csharp
[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version".
}

public class SuperLogger : Logger
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version", exactly the same
    //as the Logger class.
}

[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Status", "Green")]
public class MegaLogger : Logger        {
    //Exports with contract type IPlugin and
    //metadata "Status" only. Re-declaring
    //the attribute replaces all metadata.
}
```

Al volver a declarar el atributo `InheritedExport` para reemplazar los metadatos, asegúrese de que los tipos de contrato son los mismos. (En el ejemplo anterior, `IPlugin` es el tipo del contrato). Si difieren, el segundo atributo creará, en lugar de reemplazar, una segunda exportación independiente de la parte. Generalmente, esto significa que tendrá que especificar el tipo de contrato explícitamente al reemplazar un atributo `InheritedExport` , como se muestra en el ejemplo anterior.

Puesto que no se pueden crear instancias de interfaces directamente, por lo general no se pueden decorar con atributos `Export` o `Import` . Sin embargo, una interfaz se puede decorar con un atributo `InheritedExport` en el nivel de interfaz y esa exportación junto con los metadatos asociados las heredarán las clases implementadoras. Sin embargo, la propia interfaz no estará disponible como una parte.

<a name="custom_export_attributes"></a>

## <a name="custom-export-attributes"></a>Atributos de exportación personalizados

Los atributos de exportación básicos, `Export` e `InheritedExport`, se pueden extender para incluir los metadatos como propiedades de atributo. Esta técnica es útil para aplicar metadatos similares a muchas partes o para crear un árbol de herencia de atributos de metadatos.

Un atributo personalizado puede especificar el tipo de contrato, el nombre del contrato o cualquier otro tipo de metadatos. Para definir un atributo personalizado, una clase que hereda de `ExportAttribute` (o `InheritedExportAttribute`) se debe decorar con el atributo `MetadataAttribute` . La siguiente clase define un atributo personalizado.

```vb
<MetadataAttribute()>
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=false)>
Public Class MyAttribute
    Inherits ExportAttribute

    Public Property MyMetadata As String

    Public Sub New(ByVal myMetadata As String)
        MyBase.New(GetType(IMyAddin))

        myMetadata = myMetadata
    End Sub

End Class
```

```csharp
[MetadataAttribute]
[AttributeUsage(AttributeTargets.Class, AllowMultiple=false)]
public class MyAttribute : ExportAttribute
{
    public MyAttribute(string myMetadata)
        : base(typeof(IMyAddin))
    {
        MyMetadata = myMetadata;
    }

    public string MyMetadata { get; private set; }
}
```

Esta clase define un atributo personalizado denominado `MyAttribute` con tipo de contrato `IMyAddin` y algunos metadatos denominados `MyMetadata`. Se considera que todas las propiedades de una clase marcadas con el atributo `MetadataAttribute` son metadatos definidos en el atributo personalizado. Las dos declaraciones siguientes son equivalentes.

```vb
<Export(GetType(IMyAddin))>
<ExportMetadata("MyMetadata", "theData")>
Public Property myAddin As MyAddin
```

```vb
<MyAttribute("theData")>
Public Property myAddin As MyAddin
```

```csharp
[Export(typeof(IMyAddin)),
    ExportMetadata("MyMetadata", "theData")]
public MyAddin myAddin { get; set; }
```

```csharp
[MyAttribute("theData")]
public MyAddin myAddin { get; set; }
```

En la primera declaración, el tipo de contrato y los metadatos se definen explícitamente. En la segunda declaración, el tipo de contrato y los metadatos están implícitos en el atributo personalizado. Concretamente, en los casos en los que se debe aplicar una cantidad grande de metadatos idénticos a muchas partes (por ejemplo, información sobre el autor y el copyright), utilizar un atributo personalizado ahorra tiempo y duplicados. Además, se pueden crear árboles de herencia de atributos personalizados para permitir variantes.

Para crear los metadatos opcionales en un atributo personalizado, puede utilizar el atributo `DefaultValue` . Cuando este atributo se aplica a una propiedad de una clase de atributos personalizada, especifica que la propiedad representativa es opcional y no tiene que ser proporcionada por un exportador. Si no se proporciona el valor de la propiedad, se le asignará el valor predeterminado de su tipo de propiedad (normalmente `null`, `false`o 0).

<a name="creation_policies"></a>

## <a name="creation-policies"></a>Directivas de creación

Cuando una parte especifica una importación y se realiza la composición, el contenedor de composición intenta encontrar una exportación coincidente. Si la importación coincide correctamente con una exportación, el miembro de importación se establece en una instancia del objeto exportado. La *directiva de creación*de la parte que exporta controla la procedencia de esta instancia.

Las dos posibles directivas de creación son *compartida* y *no compartida*. Una parte con una directiva de creación compartida se compartirá entre todas las importaciones del contenedor de una parte con ese contrato. Cuando el motor de composición encuentra una coincidencia y tiene que establecer una propiedad de importación, solo creará una instancia de una nueva copia de la parte si aún no existe; si no, proporcionará la copia existente. Esto significa que muchos objetos pueden tener referencias a la misma parte. Estas partes no deberían confiar en un estado interno que se puede cambiar desde muchos lugares. Esta directiva es adecuada para las partes estáticas, las que proporcionan servicios y las que utilizan mucha memoria u otros recursos.

Se creará una parte con una directiva de creación de parte no compartida cada vez que se encuentre una importación correspondiente para una de sus exportaciones. Se crearán instancias de una nueva copia para cada importación del contenedor que coincida con uno de los contratos exportados de la parte. No se compartirá el estado interno de estas copias. Esta directiva es adecuada para las partes en las que cada importación requiere su propio estado interno.

La importación y la exportación pueden especificar la directiva de creación de una parte, entre los valores `Shared`, `NonShared`o `Any`. El valor predeterminado es `Any` para las importaciones y las exportaciones. Una exportación que especifica `Shared` o `NonShared` solo coincidirá con una importación que especifique lo mismo o que especifique `Any`. De igual forma, una exportación que especifica `Shared` o `NonShared` solo coincidirá con una exportación que especifique lo mismo o que especifique `Any`. Las importaciones y exportaciones con directivas de creación incompatibles no se consideran una coincidencia, de la misma manera que una importación y exportación cuyo nombre de contrato o tipo de contrato no coinciden. Si la importación y la exportación especifican `Any`o no especifican una directiva de creación y tienen como valor predeterminado `Any`, la directiva de creación se establecerá de manera predeterminado en compartida.

En el siguiente ejemplo se muestran importaciones y exportaciones que especifican directivas de creación. `PartOne` no especifica una directiva de creación, de modo que el valor predeterminado es `Any`. `PartTwo` no especifica una directiva de creación, de modo que el valor predeterminado es `Any`. Dado que la importación y la exportación tienen como valor predeterminado `Any`, se compartirá `PartOne` . `PartThree` especifica una directiva de creación `Shared` , de modo que `PartTwo` y `PartThree` compartirán la misma copia de `PartOne`. `PartFour` especifica una directiva de creación `NonShared` , de modo que `PartFour` será no compartida en `PartFive`. `PartSix` especifica una directiva de creación `NonShared` . `PartFive` y `PartSix` recibirán copias independientes de `PartFour`. `PartSeven` especifica una directiva de creación `Shared` . Dado que no hay ningún `PartFour` exportado con una directiva de creación de `Shared`, la importación `PartSeven` no coincide con nada y no se completará.

```vb
<Export()>
Public Class PartOne
    'The default creation policy for an export is Any.
End Class

Public Class PartTwo

    <Import()>
    Public Property partOne As PartOne

    'The default creation policy for an import is Any.
    'If both policies are Any, the part will be shared.

End Class

Public Class PartThree

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partOne As PartOne

    'The Shared creation policy is explicitly specified.
    'PartTwo and PartThree will receive references to the
    'SAME copy of PartOne.

End Class

<Export()>
<PartCreationPolicy(CreationPolicy.NonShared)>
Public Class PartFour
    'The NonShared creation policy is explicitly specified.
End Class

Public Class PartFive

    <Import()>
    Public Property partFour As PartFour

    'The default creation policy for an import is Any.
    'Since the export's creation policy was explicitly
    'defined, the creation policy for this property will
    'be non-shared.

End Class

Public Class PartSix

    <Import(RequiredCreationPolicy:=CreationPolicy.NonShared)>
    Public Property partFour As PartFour

    'Both import and export specify matching creation
    'policies.  PartFive and PartSix will each receive
    'SEPARATE copies of PartFour, each with its own
    'internal state.

End Class

Public Class PartSeven

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partFour As PartFour

    'A creation policy mismatch.  Because there is no
    'exported PartFour with a creation policy of Shared,
    'this import does not match anything and will not be
    'filled.

End Class
```

```csharp
[Export]
public class PartOne
{
    //The default creation policy for an export is Any.
}

public class PartTwo
{
    [Import]
    public PartOne partOne { get; set; }

    //The default creation policy for an import is Any.
    //If both policies are Any, the part will be shared.
}

public class PartThree
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartOne partOne { get; set; }

    //The Shared creation policy is explicitly specified.
    //PartTwo and PartThree will receive references to the
    //SAME copy of PartOne.
}

[Export]
[PartCreationPolicy(CreationPolicy.NonShared)]
public class PartFour
{
    //The NonShared creation policy is explicitly specified.
}

public class PartFive
{
    [Import]
    public PartFour partFour { get; set; }

    //The default creation policy for an import is Any.
    //Since the export's creation policy was explicitly
    //defined, the creation policy for this property will
    //be non-shared.
}

public class PartSix
{
    [Import(RequiredCreationPolicy = CreationPolicy.NonShared)]
    public PartFour partFour { get; set; }

    //Both import and export specify matching creation
    //policies.  PartFive and PartSix will each receive
    //SEPARATE copies of PartFour, each with its own
    //internal state.
}

public class PartSeven
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartFour partFour { get; set; }

    //A creation policy mismatch.  Because there is no
    //exported PartFour with a creation policy of Shared,
    //this import does not match anything and will not be
    //filled.
}
```

<a name="life_cycle_and_disposing"></a>

## <a name="life-cycle-and-disposing"></a>Ciclo de vida y eliminación

Dado que las partes se hospedan en el contenedor de composición, su ciclo de vida puede ser más complejo que el de los objetos ordinarios. Las partes pueden implementar dos importantes interfaces relacionadas con el ciclo de vida: `IDisposable` e `IPartImportsSatisfiedNotification`.

Las partes que exigen realizar trabajo al cerrar o que necesitan liberar recursos deberían implementar `IDisposable`como de costumbre para los objetos de .NET Framework. Sin embargo, ya que el contenedor crea y mantiene las referencias a las partes, solo el contenedor que posee una parte debería llamar al método `Dispose` en él. El contenedor implementa `IDisposable`, y como parte de la limpieza en `Dispose` llamará a `Dispose` en todas las partes que posee. Por esta razón, debería eliminar, cuando ya no se necesite, el contenedor de composición y sus partes.

Para los contenedores de composición duraderos, el consumo de memoria de las partes con una directiva de creación de parte no compartida puede convertirse en un problema. Estas partes no compartidas se pueden crear varias veces y no se eliminarán hasta que se elimine el contenedor. Para solucionar esto, el contenedor proporciona el método `ReleaseExport` . Llamando a este método en una exportación no compartida, se quita esa exportación del contenedor de composición y se elimina. Las partes que solo utilizaba la exportación eliminada y demás hacia abajo en el árbol, también se quitan y se eliminan. De esta manera, los recursos se pueden reclamar sin eliminar el contenedor de composición.

`IPartImportsSatisfiedNotification` contiene un método denominado `OnImportsSatisfied`. El contenedor de composición llama a este método en cualquier parte que implemente la interfaz cuando se ha completado la composición y las importaciones de la parte están listas para el uso. El motor de la composición crea las partes para completar las importaciones de otras partes. Antes de que las importaciones de una parte se hayan establecido, no puede realizar ninguna inicialización que confíe o manipule los valores importados en el constructor de la parte, a menos que esos valores se hayan especificado como requisitos previos mediante el atributo `ImportingConstructor` . Éste es normalmente el método preferido, pero en algunos casos, la inyección de constructor tal vez no esté disponible. En esos casos, la inicialización se puede realizar en `OnImportsSatisfied`y la parte debería implementar `IPartImportsSatisfiedNotification`.

## <a name="see-also"></a>Vea también

- [Vídeo de Channel 9: Abrir las aplicaciones con Managed Extensibility Framework](https://channel9.msdn.com/events/TechEd/NorthAmerica/2009/DTL328)
- [Vídeo de Channel 9: Managed Extensibility Framework (MEF) 2.0](https://channel9.msdn.com/posts/NET-45-Oleg-Lvovitch-and-Kevin-Ransom-Managed-Extensibility-Framework-MEF-20)
