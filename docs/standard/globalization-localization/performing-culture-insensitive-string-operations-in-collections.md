---
title: "Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ArrayList.Sort (método)"
  - "CaseInsensitiveComparer (clase), utilizar"
  - "CaseInsensitiveHashCodeProvider (clase), utilizar"
  - "colecciones [.NET Framework], operaciones de cadena que no tienen en cuenta la referencia cultural"
  - "CollectionsUtil.CreateCaseInsensitiveHashtable (método)"
  - "parámetro de referencia cultural"
  - "operaciones de cadena que no tienen en cuenta la referencia cultural, colecciones"
  - "SortedList (clase), operaciones de cadena que no tienen en cuenta la referencia cultural"
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones
Hay clases y miembros en el espacio de nombres <xref:System.Collections> que, de forma predeterminada, proporcionan un comportamiento que tiene en cuenta las referencias culturales.  Los constructores predeterminados de las clases <xref:System.Collections.CaseInsensitiveComparer> y <xref:System.Collections.CaseInsensitiveHashCodeProvider> inicializan una nueva instancia mediante la propiedad <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName>.  De forma predeterminada, todas las sobrecargas del método [CollectionsUtil.CreateCaseInsensitiveHashTable](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic) crean una nueva instancia de la clase <xref:System.Collections.Hashtable> mediante la propiedad `Thread.CurrentCulture`.  De forma predeterminada, las sobrecargas del método <xref:System.Collections.ArrayList.Sort%2A?displayProperty=fullName> realizan ordenaciones que tienen en cuenta la referencia cultural mediante la propiedad `Thread.CurrentCulture`.  La propiedad `Thread.CurrentCulture` puede afectar a la ordenación y la búsqueda en un objeto <xref:System.Collections.SortedList> cuando se utilizan cadenas como claves.  Siga las recomendaciones de uso proporcionadas en esta sección para obtener resultados que no tengan en cuenta la referencia cultural de estos métodos y clases en el espacio de nombres `Collections`.  
  
 **Nota** Al pasar <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> a un método de comparación, se realiza una comparación que no tiene en cuenta la referencia cultural.  Sin embargo, no se realiza una comparación no lingüística, por ejemplo, para las rutas de acceso a archivos, las claves del Registro y las variables de entorno.  Tampoco se admiten decisiones de seguridad basadas en el resultado de la comparación.  Para que se realice una comparación no lingüística o se admitan decisiones de seguridad basadas en los resultados, la aplicación debe usar un método de comparación que acepte un valor de <xref:System.StringComparison>.  A continuación, la aplicación debe pasar <xref:System.StringComparison>.  
  
## Utilizar las clases CaseInsensitiveComparer y CaseInsensitiveHashCodeProvider  
 Los constructores predeterminados de `CaseInsensitiveHashCodeProvider` y `CaseInsensitiveComparer` inicializan una nueva instancia de la clase mediante `Thread.CurrentCulture`, lo cual da lugar a un comportamiento que tiene en cuenta la referencia cultural.  En el ejemplo de código siguiente, se muestra el constructor de una clase `Hashtable` que es dependiente de la referencia cultural porque utiliza los constructores predeterminados de `CaseInsensitiveHashCodeProvider` y `CaseInsensitiveComparer`.  
  
```vb  
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)  
  
```  
  
```csharp  
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);  
```  
  
 Si desea crear una nueva clase `Hashtable` que no tenga en cuenta la referencia cultural usando las clases `CaseInsensitiveComparer` y `CaseInsensitiveHashCodeProvider`, inicialice nuevas instancias de estas clases mediante constructores que acepten un parámetro `culture`.  Para el parámetro `culture`, especifique <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  En el siguiente ejemplo de código, se muestra el constructor de una clase `Hashtable` que no tiene en cuenta la referencia cultural.  
  
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
  
## Utilizar el método CollectionsUtil.CreateCaseInsensitiveHashTable  
 El método `CollectionsUtil.CreateCaseInsensitiveHashTable` es un acceso directo útil para crear una nueva instancia de la clase `Hashtable` que omita el uso de mayúsculas y minúsculas en las cadenas.  Sin embargo, todas las sobrecargas del método `CollectionsUtil.CreateCaseInsensitiveHashTable` tienen en cuenta la referencia cultural porque usan la propiedad `Thread.CurrentCulture`.  Con este método, no se puede crear una `Hashtable` que no tenga en cuenta la referencia cultural.  Para crear una `Hashtable` que no tenga en cuenta la referencia cultural, use el constructor de `Hashtable` que acepte un parámetro `culture`.  Para el parámetro `culture`, especifique `CultureInfo.InvariantCulture`.  En el siguiente ejemplo de código, se muestra el constructor de una clase `Hashtable` que no tiene en cuenta la referencia cultural.  
  
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
## Utilizar la clase SortedList  
 Una clase `SortedList` representa una colección de pares clave\-valor que se ordenan según las claves y a los cuales se puede obtener acceso mediante las claves o el índice.  Cuando se usa una clase `SortedList` donde las cadenas son las claves, la ordenación y la búsqueda pueden verse afectadas por la propiedad `Thread.CurrentCulture`.  Para que una clase `SortedList` tenga un comportamiento independiente de la referencia cultural, cree un objeto `SortedList` mediante uno de los constructores que acepten un parámetro `comparer`.  El parámetro `comparer` especifica la implementación de <xref:System.Collections.IComparer> que se va a utilizar para comparar las claves.  Para el parámetro, especifique una clase comparadora personalizada que utilice `CultureInfo.InvariantCulture` para comparar las claves.  En el ejemplo siguiente, se muestra una clase comparadora personalizada e independiente de la referencia cultural que se puede especificar como el parámetro `comparer` de un constructor de `SortedList`.  
  
```vb  
Imports System  
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
  
 En general, si se usa un objeto `SortedList` con cadenas sin especificar un comparador invariable personalizado, cualquier cambio que se realice en `Thread.CurrentCulture` después de que se haya rellenado la lista puede invalidar dicha lista.  
  
## Utilizar el método ArrayList.Sort  
 De forma predeterminada, las sobrecargas del método `ArrayList.Sort` realizan ordenaciones que tienen en cuenta la referencia cultural mediante la propiedad `Thread.CurrentCulture`.  Los resultados pueden cambiar en función de las referencias culturales debido a los diferentes criterios de ordenación.  Para que el comportamiento no tenga en cuenta la referencia cultural, use las sobrecargas de este método que acepten una implementación de `IComparer`.  Para el parámetro `comparer`, especifique una clase comparadora invariable personalizada que use `CultureInfo.InvariantCulture`.  Se proporciona un ejemplo de clase comparadora invariable personalizada en el tema [Utilizar la clase SortedList](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1).  
  
## Vea también  
 <xref:System.Collections.CaseInsensitiveComparer>   
 <xref:System.Collections.CaseInsensitiveHashCodeProvider>   
 <xref:System.Collections.ArrayList.Sort%2A?displayProperty=fullName>   
 <xref:System.Collections.SortedList>   
 <xref:System.Collections.Hashtable>   
 <xref:System.Collections.IComparer>   
 [Realizar operaciones de cadenas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)   
 [CollectionsUtil.CreateCaseInsensitiveHashTable \(Método\)](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic)