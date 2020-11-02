---
title: Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CaseInsensitiveComparer class, using
- CollectionsUtil.CreateCaseInsensitiveHashtable method
- culture-insensitive string operations, collections
- collections [.NET], culture-insensitive string operations
- CaseInsensitiveHashCodeProvider class, using
- ArrayList.Sort method
- SortedList class, culture-insensitive string operations
- culture parameter
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
ms.openlocfilehash: 0a55a41b7cd2a2d245d0fb7722dddee794777422
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063968"
---
# <a name="performing-culture-insensitive-string-operations-in-collections"></a>Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones

En el espacio de nombres <xref:System.Collections> hay clases y miembros que proporcionan, de manera predeterminada, el comportamiento que tiene en cuenta la referencia cultural. Los constructores sin parámetros de las clases <xref:System.Collections.CaseInsensitiveComparer> y <xref:System.Collections.CaseInsensitiveHashCodeProvider> inicializan una instancia nueva con la propiedad <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>. Todas las sobrecargas del método <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> crean una instancia de la clase <xref:System.Collections.Hashtable> mediante la propiedad `Thread.CurrentCulture` de forma predeterminada. Las sobrecargas del método <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> realizan ordenaciones que tienen en cuenta las referencias culturales de manera predeterminada con `Thread.CurrentCulture`. <xref:System.Collections.SortedList> puede afectar la ordenación y la búsqueda en `Thread.CurrentCulture` cuando las cadenas se usan como las claves. Siga las recomendaciones de uso que se proporcionan en esta sección para obtener resultados que no tienen en cuenta la referencia cultural de estas clases y métodos en el espacio de nombres `Collections`.

> [!NOTE]
> Pasar <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> a un método de comparación realiza una comparación que no tiene en cuenta la referencia cultural. Si embargo, no provoca una comparación no lingüística, por ejemplo, para las rutas de acceso de archivo, las claves del Registro y las variables de entorno. Tampoco admite las decisiones de seguridad basadas en el resultado de la comparación. Para una comparación no lingüística o la compatibilidad con las decisiones de seguridad basadas en los resultados, la aplicación debe usar un método de comparación que acepte un valor <xref:System.StringComparison>. A continuación, la aplicación debe pasar <xref:System.StringComparison>.

## <a name="using-the-caseinsensitivecomparer-and-caseinsensitivehashcodeprovider-classes"></a>Uso de las clases CaseInsensitiveComparer y CaseInsensitiveHashCodeProvider

Los constructores sin parámetros para `CaseInsensitiveHashCodeProvider` y `CaseInsensitiveComparer` inicializan una instancia nueva de la clase con `Thread.CurrentCulture`, lo que genera un comportamiento que tiene en cuenta las referencias culturales. En el ejemplo de código siguiente se muestra el constructor de `Hashtable` que tiene en cuenta las referencias culturales porque usa los constructores sin parámetros para `CaseInsensitiveHashCodeProvider` y `CaseInsensitiveComparer`.

```vb
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)
```

```csharp
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);
```

Si desea crear `Hashtable` que no tiene en cuenta las referencias culturales con las clases `CaseInsensitiveComparer` y `CaseInsensitiveHashCodeProvider`, inicialice instancias nuevas de estas clases con los constructores que aceptan un parámetro `culture`. Para el parámetro `culture`, especifique <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. El ejemplo de código siguiente muestra el constructor para un `Hashtable` que no tiene en cuenta las referencias culturales.

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

## <a name="using-the-collectionsutilcreatecaseinsensitivehashtable-method"></a>Uso del método CollectionsUtil.CreateCaseInsensitiveHashTable

El método `CollectionsUtil.CreateCaseInsensitiveHashTable` es un acceso directo para crear una instancia de la clase `Hashtable` que no toma en cuenta las mayúsculas y minúsculas de las cadenas. Sin embargo, todas las sobrecargas del método `CollectionsUtil.CreateCaseInsensitiveHashTable` tienen en cuenta las referencias culturales porque usan la propiedad `Thread.CurrentCulture`. No puede crear un `Hashtable` que no tiene en cuenta las referencias culturales con este método. Para crear un `Hashtable` que no tiene en cuenta las referencias culturales, use el constructor `Hashtable` que acepta un parámetro `culture`. Para el parámetro `culture`, especifique `CultureInfo.InvariantCulture`. El ejemplo de código siguiente muestra el constructor para un `Hashtable` que no tiene en cuenta las referencias culturales.

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

<a name="cpconperformingculture-insensitivestringoperationsincollectionsanchor1"></a>

## <a name="using-the-sortedlist-class"></a>Uso de la clase SortedList

`SortedList` representa una colección de pares clave-valor ordenados por claves a los que se accede por clave y por índice. Cuando usa `SortedList` donde las cadenas son las claves, la propiedad `Thread.CurrentCulture` puede afectar la ordenación y la búsqueda. Para obtener el comportamiento que no tiene en cuenta las referencias culturales desde `SortedList`, cree `SortedList` con uno de los constructores que acepta un parámetro `comparer`. El parámetro `comparer` especifica la implementación <xref:System.Collections.IComparer> para usarla al comparar claves. Para el parámetro, especifique una clase de comparador personalizada que usa`CultureInfo.InvariantCulture` para comparar claves. En el ejemplo siguiente se muestra una clase de comparación que no tiene en cuenta las referencias culturales y que puede especificar como el parámetro `comparer` para un constructor `SortedList`.

```vb
Imports System.Collections
Imports System.Globalization

Friend Class InvariantComparer
    Implements IComparer
    Private m_compareInfo As CompareInfo
    Friend Shared [Default] As New InvariantComparer()

    Friend Sub New()
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo
    End Sub

    Public Function Compare(a As Object, b As Object) As Integer _
            Implements IComparer.Compare
        Dim sa As String = CType(a, String)
        Dim sb As String = CType(b, String)
        If Not (sa Is Nothing) And Not (sb Is Nothing) Then
            Return m_compareInfo.Compare(sa, sb)
        Else
            Return Comparer.Default.Compare(a, b)
        End If
    End Function
End Class
```

```csharp
using System;
using System.Collections;
using System.Globalization;

internal class InvariantComparer : IComparer
{
    private CompareInfo m_compareInfo;
    internal static readonly InvariantComparer Default = new
        InvariantComparer();

    internal InvariantComparer()
    {
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo;
    }

    public int Compare(Object a, Object b)
    {
        String sa = a as String;
        String sb = b as String;
        if (sa != null && sb != null)
            return m_compareInfo.Compare(sa, sb);
        else
            return Comparer.Default.Compare(a,b);
    }
}
```

En general, si usa `SortedList` en las cadenas sin especificar un comparador invariable personalizado, un cambio en `Thread.CurrentCulture` una vez que se rellena la lista puede invalidarla.

## <a name="using-the-arraylistsort-method"></a>Uso del método ArrayList.Sort

Las sobrecargas del método `ArrayList.Sort` realizan ordenaciones que tienen en cuenta las referencias culturales de manera predeterminada con la propiedad `Thread.CurrentCulture`. Los resultados pueden variar según la referencia cultural debido a criterios de ordenación distintos. Para eliminar el comportamiento que tiene en cuenta las referencias culturales, use las sobrecargas de este método que aceptan una implementación `IComparer`. Para el parámetro `comparer`, especifique una clase de comparador invariable personalizada que use `CultureInfo.InvariantCulture`. En el tema [Uso de la clase SortedList](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1) se proporciona un ejemplo de una clase de comparador invariable personalizada.

## <a name="see-also"></a>Vea también

- <xref:System.Collections.CaseInsensitiveComparer>
- <xref:System.Collections.CaseInsensitiveHashCodeProvider>
- <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>
- <xref:System.Collections.SortedList>
- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IComparer>
- [Realizar operaciones de cadenas que no distinguen entre referencias culturales](performing-culture-insensitive-string-operations.md)
- <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>
