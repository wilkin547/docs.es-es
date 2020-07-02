---
title: 'Cómo: Crear y enlazar a una colección ObservableCollection'
description: Obtenga información sobre cómo crear y enlazar a una colección que deriva de la clase ObservableCollection en Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], ObservableCollection class
- notifications [WPF]
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
ms.openlocfilehash: 36e3d2d84aff0ab96c9b2914da28d4c968c32bac
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617874"
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a>Cómo: Crear y enlazar a una colección ObservableCollection
En este ejemplo se muestra cómo crear y enlazar a una colección que se deriva de la <xref:System.Collections.ObjectModel.ObservableCollection%601> clase, que es una clase de colección que proporciona notificaciones cuando se agregan o quitan elementos.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra la implementación de una colección `NameList`:  
  
```csharp  
public class NameList : ObservableCollection<PersonName>  
{  
    public NameList() : base()  
    {  
        Add(new PersonName("Willa", "Cather"));  
        Add(new PersonName("Isak", "Dinesen"));  
        Add(new PersonName("Victor", "Hugo"));  
        Add(new PersonName("Jules", "Verne"));  
    }  
  }  
  
  public class PersonName  
  {  
      private string firstName;  
      private string lastName;  
  
      public PersonName(string first, string last)  
      {  
          this.firstName = first;  
          this.lastName = last;  
      }  
  
      public string FirstName  
      {  
          get { return firstName; }  
          set { firstName = value; }  
      }  
  
      public string LastName  
      {  
          get { return lastName; }  
          set { lastName = value; }  
      }  
  }  
```  
  
```vb  
Public Class NameList  
    Inherits ObservableCollection(Of PersonName)  
  
    ' Methods  
    Public Sub New()  
        MyBase.Add(New PersonName("Willa", "Cather"))  
        MyBase.Add(New PersonName("Isak", "Dinesen"))  
        MyBase.Add(New PersonName("Victor", "Hugo"))  
        MyBase.Add(New PersonName("Jules", "Verne"))  
    End Sub  
  
End Class  
  
Public Class PersonName  
    ' Methods  
    Public Sub New(ByVal first As String, ByVal last As String)  
        Me._firstName = first  
        Me._lastName = last  
    End Sub  
  
    ' Properties  
    Public Property FirstName() As String  
        Get  
            Return Me._firstName  
        End Get  
        Set(ByVal value As String)  
            Me._firstName = value  
        End Set  
    End Property  
  
    Public Property LastName() As String  
        Get  
            Return Me._lastName  
        End Get  
        Set(ByVal value As String)  
            Me._lastName = value  
        End Set  
    End Property  
  
    ' Fields  
    Private _firstName As String  
    Private _lastName As String  
End Class  
```  
  
 Puede hacer que la colección esté disponible para el enlace de la misma forma que lo haría con otros objetos Common Language Runtime (CLR), tal y como se describe en [hacer que los datos estén disponibles para el enlace en XAML](how-to-make-data-available-for-binding-in-xaml.md). Por ejemplo, puede crear una instancia de la colección en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y especificar la colección como un recurso, como se muestra aquí:  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:c="clr-namespace:SDKSample"  
  x:Class="SDKSample.Window1"  
  Width="400"  
  Height="280"  
  Title="MultiBinding Sample">  
  
  <Window.Resources>  
    <c:NameList x:Key="NameListData"/>  
  
...  
  
</Window.Resources>  
```  
  
 A continuación, puede crear un enlace a la colección:  
  
```xaml  
<ListBox Width="200"  
         ItemsSource="{Binding Source={StaticResource NameListData}}"  
         ItemTemplate="{StaticResource NameItemTemplate}"  
         IsSynchronizedWithCurrentItem="True"/>  
```  
  
 La definición de `NameItemTemplate` no se muestra aquí.  
  
> [!NOTE]
> Los objetos de la colección deben cumplir los requisitos descritos en la [Información general sobre orígenes de enlaces](binding-sources-overview.md). En concreto, si usa <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> (por ejemplo, desea [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que actualice cuando las propiedades de origen cambian dinámicamente), debe implementar un mecanismo de notificación de cambio de propiedad adecuado, como la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz.  
  
 Para más información, consulte la sección Enlace a colecciones en [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Ordenar datos en una vista](how-to-sort-data-in-a-view.md)
- [Filtrar datos en una vista](how-to-filter-data-in-a-view.md)
- [Ordenar y agrupar datos mediante una vista en XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
