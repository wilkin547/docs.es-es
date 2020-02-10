---
title: Información general sobre objetos Freezable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: b1887afd19407898d8de1d92252e29778899fb89
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095195"
---
# <a name="freezable-objects-overview"></a>Información general sobre objetos Freezable

En este tema se describe cómo usar y crear de forma eficaz objetos <xref:System.Windows.Freezable>, que proporcionan características especiales que pueden ayudar a mejorar el rendimiento de la aplicación. Los ejemplos de objetos Freezable incluyen pinceles, lápices, transformaciones, geometrías y animaciones.

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a>¿Qué es un elemento Freezable?

Un <xref:System.Windows.Freezable> es un tipo especial de objeto que tiene dos Estados: inmovilizado e inmovilizado. Cuando se inmoviliza, un <xref:System.Windows.Freezable> parece comportarse como cualquier otro objeto. Cuando se inmoviliza, ya no se puede modificar un <xref:System.Windows.Freezable>.

Un <xref:System.Windows.Freezable> proporciona un evento <xref:System.Windows.Freezable.Changed> para notificar a los observadores de cualquier modificación del objeto. La inmovilización de un <xref:System.Windows.Freezable> puede mejorar su rendimiento, ya que ya no es necesario dedicar recursos a las notificaciones de cambio. Un <xref:System.Windows.Freezable> inmovilizado también puede compartirse entre subprocesos, mientras que un <xref:System.Windows.Freezable> inmovilizado no puede.

Aunque la clase <xref:System.Windows.Freezable> tiene muchas aplicaciones, la mayoría de los objetos <xref:System.Windows.Freezable> de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] están relacionados con el subsistema de gráficos.

La clase <xref:System.Windows.Freezable> facilita el uso de determinados objetos del sistema de gráficos y puede ayudar a mejorar el rendimiento de la aplicación. Algunos ejemplos de tipos que heredan de <xref:System.Windows.Freezable> incluyen las clases <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>y <xref:System.Windows.Media.Geometry>. Dado que contienen recursos no administrados, el sistema debe supervisar estos objetos para modificarlos y, a continuación, actualizar sus recursos no administrados correspondientes cuando se produce un cambio en el objeto original. Incluso si no modifica realmente un objeto del sistema de gráficos, el sistema debe seguir gastando algunos de sus recursos supervisando el objeto, en caso de que lo cambie.

Por ejemplo, supongamos que crea un pincel de <xref:System.Windows.Media.SolidColorBrush> y lo usa para pintar el fondo de un botón.

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

Cuando se representa el botón, el subsistema de gráficos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa la información proporcionada para pintar un grupo de píxeles para crear el aspecto de un botón. Aunque se ha usado un pincel de color sólido para describir cómo se debe pintar el botón, el pincel de color sólido no realiza realmente el dibujo. El sistema de gráficos genera objetos de bajo nivel rápidos para el botón y el pincel, y son los objetos que realmente aparecen en la pantalla.

Si tuviera que modificar el pincel, se tendrían que volver a generar los objetos de bajo nivel. La clase Freezable es lo que proporciona a un pincel la capacidad de buscar sus objetos generados de bajo nivel correspondientes y actualizarlos cuando cambia. Cuando esta capacidad está habilitada, se dice que el pincel está "inmovilizado".

Un método <xref:System.Windows.Freezable.Freeze%2A> de Freezable permite deshabilitar esta capacidad de auto-actualización. Puede usar este método para convertir el pincel en "inmovilizado" o no modificable.

> [!NOTE]
> No todos los objetos Freezable se pueden inmovilizar. Para evitar que se inicie una <xref:System.InvalidOperationException>, compruebe el valor de la propiedad <xref:System.Windows.Freezable.CanFreeze%2A> del objeto Freezable para determinar si se puede inmovilizar antes de intentar inmovilizarlo.

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

Cuando ya no necesite modificar un Freezable, inmovilizarlo proporciona ventajas de rendimiento. Si fuera a inmovilizar el pincel en este ejemplo, el sistema de gráficos ya no necesitaría supervisarlo en busca de cambios. El sistema de gráficos también puede crear otras optimizaciones, porque sabe que el pincel no cambiará.

> [!NOTE]
> Para mayor comodidad, los objetos Freezable permanecen inmovilizados a menos que se inmovilizan explícitamente.

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a>Usar elementos inmovilizables

El uso de un objeto Freezable inmovilizado es como usar cualquier otro tipo de objeto. En el ejemplo siguiente, el color de un <xref:System.Windows.Media.SolidColorBrush> se cambia de amarillo a rojo después de utilizarse para pintar el fondo de un botón. El sistema de gráficos funciona en segundo plano para cambiar automáticamente el botón de amarillo a rojo la próxima vez que se actualice la pantalla.

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a>Inmovilizar un Freezable

Para que un <xref:System.Windows.Freezable> sea no modificable, llame a su método <xref:System.Windows.Freezable.Freeze%2A>. Al inmovilizar un objeto que contiene objetos Freezable, esos objetos también se inmovilizan. Por ejemplo, si inmoviliza un <xref:System.Windows.Media.PathGeometry>, las figuras y los segmentos que contiene también se bloquearán.

**No se puede** inmovilizar un Freezable si se cumple alguna de las siguientes condiciones:

- Tiene propiedades animadas o enlazadas a datos.

- Tiene las propiedades establecidas por un recurso dinámico. (Vea los [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) para obtener más información acerca de los recursos dinámicos).

- Contiene <xref:System.Windows.Freezable> subobjetos que no se pueden inmovilizar.

Si estas condiciones son falsas y no pretende modificar el <xref:System.Windows.Freezable>, debe inmovilizarla para obtener las ventajas de rendimiento descritas anteriormente.

Una vez que se llama al método <xref:System.Windows.Freezable.Freeze%2A> de un Freezable, ya no se puede modificar. Si se intenta modificar un objeto inmovilizado, se produce una <xref:System.InvalidOperationException>. En el código siguiente se produce una excepción, ya que se intenta modificar el pincel una vez que se ha inmovilizado.

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

Para evitar que se produzca esta excepción, puede utilizar el método <xref:System.Windows.Freezable.IsFrozen%2A> para determinar si un <xref:System.Windows.Freezable> está inmovilizado.

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

En el ejemplo de código anterior, se realizó una copia modificable de un objeto inmovilizado mediante el método <xref:System.Windows.Freezable.Clone%2A>. En la sección siguiente se describe con más detalle la clonación.

> [!NOTE]
> Dado que no se puede animar un objeto Freezable inmovilizado, el sistema de animación creará automáticamente clones modificables de objetos <xref:System.Windows.Freezable> inmovilizados al intentar animarlos con un <xref:System.Windows.Media.Animation.Storyboard>. Para eliminar la sobrecarga de rendimiento causada por la clonación, deje un objeto inmovilizado si tiene previsto animarlo. Para obtener más información sobre cómo animar con guiones gráficos, vea la [información general sobre los guiones gráficos](../graphics-multimedia/storyboards-overview.md).

### <a name="freezing-from-markup"></a>Inmovilizar desde el marcado

Para inmovilizar un objeto <xref:System.Windows.Freezable> declarado en el marcado, se usa el atributo `PresentationOptions:Freeze`. En el ejemplo siguiente, un <xref:System.Windows.Media.SolidColorBrush> se declara como un recurso de página y se inmoviliza. A continuación, se usa para establecer el fondo de un botón.

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

Para usar el atributo `Freeze`, debe asignar al espacio de nombres opciones de presentación: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` es el prefijo recomendado para asignar este espacio de nombres:

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

Dado que no todos los lectores de XAML reconocen este atributo, se recomienda usar el [atributo MC: ignorable](mc-ignorable-attribute.md) para marcar el atributo de `Presentation:Freeze` como ignorable:

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

Para obtener más información, vea la página de [atributo MC: ignorable](mc-ignorable-attribute.md) .

### <a name="unfreezing-a-freezable"></a>"Liberar" un Freezable

Una vez inmovilizada, un <xref:System.Windows.Freezable> nunca se puede modificar ni inmovilizar; sin embargo, puede crear un clon inmovilizado mediante el método <xref:System.Windows.Freezable.Clone%2A> o <xref:System.Windows.Freezable.CloneCurrentValue%2A>.

En el ejemplo siguiente, el fondo del botón se establece con un pincel y, a continuación, se inmoviliza el pincel. Se realiza una copia inmovilizada del pincel con el método <xref:System.Windows.Freezable.Clone%2A>. El clon se modifica y se usa para cambiar el fondo del botón de amarillo a rojo.

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> Independientemente del método de clonación que use, las animaciones nunca se copian en la nueva <xref:System.Windows.Freezable>.

Los métodos <xref:System.Windows.Freezable.Clone%2A> y <xref:System.Windows.Freezable.CloneCurrentValue%2A> generan copias en profundidad del Freezable. Si el objeto Freezable contiene otros objetos Freezable inmovilizados, también se clonan y se convierten en modificables. Por ejemplo, si clona una <xref:System.Windows.Media.PathGeometry> inmovilizada para convertirla en modificable, las figuras y los segmentos que contiene también se copian y se convierten en modificables.

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a>Crear su propia clase Freezable

Una clase que deriva de <xref:System.Windows.Freezable> obtiene las siguientes características.

- Estados especiales: un estado de solo lectura (inmovilizado) y de escritura.

- Seguridad para subprocesos: un <xref:System.Windows.Freezable> inmovilizado puede compartirse entre subprocesos.

- Notificación de cambios detallada: a diferencia de otros <xref:System.Windows.DependencyObject>s, los objetos Freezable proporcionan notificaciones de cambios cuando cambian los valores de las subpropiedades.

- Clonación sencilla: la clase Freezable ya ha implementado varios métodos que producen clones profundos.

Un <xref:System.Windows.Freezable> es un tipo de <xref:System.Windows.DependencyObject>y, por tanto, utiliza el sistema de propiedades de dependencia. No es necesario que las propiedades de la clase sean propiedades de dependencia, pero el uso de propiedades de dependencia reduce la cantidad de código que se debe escribir, ya que la clase <xref:System.Windows.Freezable> se ha diseñado teniendo en cuenta las propiedades de dependencia. Para obtener más información sobre el sistema de propiedades de dependencia, consulte [información general sobre las propiedades de dependencia](dependency-properties-overview.md).

Cada subclase <xref:System.Windows.Freezable> debe invalidar el método <xref:System.Windows.Freezable.CreateInstanceCore%2A>. Si la clase usa propiedades de dependencia para todos sus datos, ha terminado.

Si la clase contiene miembros de datos de propiedades que no son de dependencia, también debe invalidar los métodos siguientes:

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

También debe observar las siguientes reglas para obtener acceso a los miembros de datos que no son propiedades de dependencia y escribir en ellos:

- Al principio de cualquier API que lea miembros de datos de propiedades que no son de dependencia, llame al método <xref:System.Windows.Freezable.ReadPreamble%2A>.

- Al principio de cualquier API que escriba miembros de datos de propiedades que no son de dependencia, llame al método <xref:System.Windows.Freezable.WritePreamble%2A>. (Una vez que haya llamado <xref:System.Windows.Freezable.WritePreamble%2A> en una API, no es necesario que realice una llamada adicional a <xref:System.Windows.Freezable.ReadPreamble%2A> si también lee miembros de datos de propiedades que no son de dependencia).

- Llame al método <xref:System.Windows.Freezable.WritePostscript%2A> antes de salir de los métodos que escriben en los miembros de datos de propiedades que no son de dependencia.

Si la clase contiene miembros de datos que no son de dependencia que se <xref:System.Windows.DependencyObject> objetos, también debe llamar al método <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> cada vez que cambie uno de sus valores, aunque esté estableciendo el miembro en `null`.

> [!NOTE]
> Es muy importante que comience cada <xref:System.Windows.Freezable> método que invalide con una llamada a la implementación base.

Para obtener un ejemplo de una clase de <xref:System.Windows.Freezable> personalizada, vea el [ejemplo de animación personalizada](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Freezable>
- [Ejemplo de animación personalizada](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
