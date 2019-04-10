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
ms.openlocfilehash: 8df19e69ff3be06704878ea290a3f4a2997127eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224271"
---
# <a name="freezable-objects-overview"></a>Información general sobre objetos Freezable
En este tema se describe cómo usar de forma eficaz y crear <xref:System.Windows.Freezable> objetos, que proporcionan características especiales que pueden ayudar a mejorar el rendimiento de la aplicación. Pinceles, lápices, transformaciones, geometrías y las animaciones son ejemplos de objetos freezable.  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a>¿Qué es un objeto inmovilizable?  
 Un <xref:System.Windows.Freezable> es un tipo especial de objeto que tiene dos estados: no inmovilizado e inmovilizado. Cuando no está inmovilizado, un <xref:System.Windows.Freezable> parece que se comportan como cualquier otro objeto. Cuando está inmovilizado, un <xref:System.Windows.Freezable> ya no se puede modificar.  
  
 Un <xref:System.Windows.Freezable> proporciona un <xref:System.Windows.Freezable.Changed> eventos para notificar a los observadores de ninguna modificación en el objeto. Inmovilizar un <xref:System.Windows.Freezable> puede mejorar su rendimiento, porque ya no necesita dedicar recursos a las notificaciones de cambio. Inmovilizado <xref:System.Windows.Freezable> también se pueden compartir entre subprocesos, mientras un inmovilizadas <xref:System.Windows.Freezable> no.  
  
 Aunque el <xref:System.Windows.Freezable> clase tiene muchas aplicaciones más <xref:System.Windows.Freezable> objetos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] están relacionados con el subsistema de gráficos.  
  
 La <xref:System.Windows.Freezable> clase hace que sea más fácil de usar ciertos objetos de sistema de gráficos y puede ayudar a mejorar el rendimiento de la aplicación. Ejemplos de tipos que heredan de <xref:System.Windows.Freezable> incluyen el <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, y <xref:System.Windows.Media.Geometry> clases. Porque contienen los recursos no administrados, el sistema debe supervisar estos objetos para realizar modificaciones y, a continuación, actualice sus recursos no administrados correspondientes cuando hay un cambio en el objeto original. Incluso si realmente no modifica un objeto del sistema de gráficos, el sistema debe dedicar algunos de sus recursos de supervisión del objeto, en caso de que lo cambie.  
  
 Por ejemplo, suponga que crea un <xref:System.Windows.Media.SolidColorBrush> brush y usarlo para pintar el fondo de un botón.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 Cuando se representa el botón, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] subsistema de gráficos utiliza la información proporcionada para pintar un grupo de píxeles que se crean la apariencia de un botón. Aunque utilizar un pincel de color sólido para describir cómo se debe pintar el botón, el pincel de color sólido no hace realmente la pintura. El sistema de gráficos genera objetos rápidos y bajo nivel para el botón y el pincel y es esos objetos que realmente aparecen en la pantalla.  
  
 Si tuviera que modificar el pincel, esos objetos de bajo nivel tendría que volver a generar. La clase freezable es lo que permite un pincel para encontrar sus correspondientes objetos generados de bajo nivel y se actualizan cuando cambia. Cuando se habilita esta capacidad, el pincel se dice que "inmovilizado".  
  
 Un objeto inmovilizable <xref:System.Windows.Freezable.Freeze%2A> método le permite deshabilitar esta capacidad de actualización automática. Puede usar este método para hacer que el pincel se convierten en "inmovilizado", o en no modificable.  
  
> [!NOTE]
>  No todos los objetos Freezable se pueden inmovilizar. Para evitar que se produzca una <xref:System.InvalidOperationException>, compruebe el valor del objeto Freezable <xref:System.Windows.Freezable.CanFreeze%2A> propiedad para determinar si se puede inmovilizar antes de intentar inmovilizarlo.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Cuando ya no necesite modificar un elemento freezable, inmovilizarlo ofrece ventajas de rendimiento. Si fuera a inmovilizar el pincel en este ejemplo, el sistema de gráficos ya no necesitaría supervisar los cambios. El sistema de gráficos también puede realizar otras optimizaciones, porque sabe que el pincel no cambiará.  
  
> [!NOTE]
>  Para mayor comodidad, los objetos freezable permanecen inmovilizados a menos que explícitamente inmovilícelos.  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a>Uso de elementos inmovilizables  
 Utilizar un inmovilizadas freezable es como cualquier otro tipo de objeto. En el ejemplo siguiente, el color de un <xref:System.Windows.Media.SolidColorBrush> se cambia de amarillo a rojo después de se usa para pintar el fondo de un botón. El sistema de gráficos funciona en segundo plano para cambiar automáticamente el botón de amarillo a rojo la próxima vez que se actualiza la pantalla.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a>Inmovilizar un objeto inmovilizable  
 Para realizar un <xref:System.Windows.Freezable> en no modificable, se llama a su <xref:System.Windows.Freezable.Freeze%2A> método. Al inmovilizar un objeto que contiene objetos freezable, esos objetos también se inmovilizan. Por ejemplo, si inmoviliza un <xref:System.Windows.Media.PathGeometry>, las figuras y los segmentos que contiene también se inmovilizan.  
  
 Un elemento Freezable **no** se puede inmovilizar si se cumple alguna de las siguientes acciones:  
  
-   Ha animado o propiedades enlazado a datos.  
  
-   Tiene propiedades establecidas por un recurso dinámico. (Consulte la [recursos XAML](xaml-resources.md) para obtener más información acerca de los recursos dinámicos.)  
  
-   Contiene <xref:System.Windows.Freezable> subobjetos que no se puede inmovilizar.  
  
 Si estas condiciones son false y no pretende modificar el <xref:System.Windows.Freezable>, a continuación, se debe inmovilizar para obtener las ventajas de rendimiento se ha descrito anteriormente.  
  
 Una vez que se llama a un objeto inmovilizable <xref:System.Windows.Freezable.Freeze%2A> método, ya no se puede modificar. Al intentar modificar inmovilizado objeto hace que un <xref:System.InvalidOperationException> que se produzca. El código siguiente produce una excepción, ya que se intenta modificar el pincel después de se ha inmovilizado.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Para evitar que se produzca esta excepción, puede usar el <xref:System.Windows.Freezable.IsFrozen%2A> método para determinar si un <xref:System.Windows.Freezable> está inmovilizada.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 En el ejemplo de código anterior, se ha realizado una copia modificable de un objeto inmovilizado mediante el <xref:System.Windows.Freezable.Clone%2A> método. La siguiente sección explica la clonación con más detalle.  
  
 **Tenga en cuenta** porque inmovilizado no pueden animarse freezable, el sistema de animación se creará automáticamente clones modificables de inmovilizado <xref:System.Windows.Freezable> objetos al intentar animar con un <xref:System.Windows.Media.Animation.Storyboard>. Para eliminar la sobrecarga de rendimiento causada mediante la clonación, dejar un objeto movilizar si piensa animarlo. Para obtener más información acerca de cómo animar con guiones gráficos, vea el [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).  
  
### <a name="freezing-from-markup"></a>Inmovilización de marcado  
 Para inmovilizar un <xref:System.Windows.Freezable> objeto declarado en el marcado, usa el `PresentationOptions:Freeze` atributo. En el ejemplo siguiente, un <xref:System.Windows.Media.SolidColorBrush> se declara como un recurso de página y se inmoviliza. A continuación, sirve para establecer el fondo de un botón.  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Para usar el `Freeze` atributo, debe asignar al espacio de nombres de las opciones de presentación: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` es el prefijo recomendado para asignar este espacio de nombres:  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Dado que no todos los lectores XAML reconocen este atributo, se recomienda utilizar la [mc: Ignorable (atributo)](mc-ignorable-attribute.md) para marcar el `Presentation:Freeze` atributo como se puede pasar por alto:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Para obtener más información, consulte el [mc: Ignorable (atributo)](mc-ignorable-attribute.md) página.  
  
### <a name="unfreezing-a-freezable"></a>"Liberar" un objeto inmovilizable  
 Una vez inmovilizado, un <xref:System.Windows.Freezable> nunca se pueden modificar o movilizar; sin embargo, puede crear un clon inmovilizado usando el <xref:System.Windows.Freezable.Clone%2A> o <xref:System.Windows.Freezable.CloneCurrentValue%2A> método.  
  
 En el ejemplo siguiente, se establece el fondo del botón con un pincel y, a continuación, se inmoviliza ese pincel. Se realiza una copia no inmovilizada del pincel mediante el <xref:System.Windows.Freezable.Clone%2A> método. El clon se modifica y se utiliza para cambiar el fondo del botón de amarillo a rojo.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Independientemente del método clone que use, las animaciones nunca se copian en el nuevo <xref:System.Windows.Freezable>.  
  
 El <xref:System.Windows.Freezable.Clone%2A> y <xref:System.Windows.Freezable.CloneCurrentValue%2A> métodos generan copias en profundidad del objeto freezable. Si el objeto freezable contiene otros objetos freezable inmovilizados, también se clonan y son modificables. Por ejemplo, si clona inmovilizado <xref:System.Windows.Media.PathGeometry> para que sea modificable, las figuras y los segmentos que contiene se también copian y se pueden modificar.  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a>Crear su propia clase Freezable  
 Una clase que derive de <xref:System.Windows.Freezable> incluye las siguientes características.  
  
-   Estados especiales: solo lectura (inmovilizado) y un estado de escritura.  
  
-   Seguridad para subprocesos: inmovilizado <xref:System.Windows.Freezable> se pueden compartir entre subprocesos.  
  
-   Notificación de cambios detallada: A diferencia de otras <xref:System.Windows.DependencyObject>s, objetos Freezable proporcionan notificaciones de cambio cuando cambian los valores de la subpropiedad.  
  
-   Clonación fácil: la clase Freezable ya ha implementado varios métodos que generan clones perfectos.  
  
 Un <xref:System.Windows.Freezable> es un tipo de <xref:System.Windows.DependencyObject>y por lo tanto, usa el sistema de propiedades de dependencia. Las propiedades de clase no tienen que ser propiedades de dependencia, pero utilizando las propiedades de dependencia se reducirá la cantidad de código que tiene que escribir, porque la <xref:System.Windows.Freezable> clase se diseñó teniendo en cuenta las propiedades de dependencia. Para obtener más información sobre el sistema de propiedades de dependencia, consulte el [información general sobre las propiedades de dependencia](dependency-properties-overview.md).  
  
 Cada <xref:System.Windows.Freezable> subclase debe invalidar el <xref:System.Windows.Freezable.CreateInstanceCore%2A> método. Si su clase usa las propiedades de dependencia para todos sus datos, habrá terminado.  
  
 Si la clase contiene a miembros de datos de propiedad no son de dependencia, también debe invalidar los métodos siguientes:  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 También debe observar las reglas siguientes para obtener acceso y escribir en los miembros de datos que no son propiedades de dependencia:  
  
-   Al principio de cualquier [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] que lee los miembros de datos de propiedad no son de dependencia, llame a la <xref:System.Windows.Freezable.ReadPreamble%2A> método.  
  
-   Al principio de cualquier API que escribe los miembros de datos de propiedad no son de dependencia, llame a la <xref:System.Windows.Freezable.WritePreamble%2A> método. (Una vez que haya llamado a <xref:System.Windows.Freezable.WritePreamble%2A> en un [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], no es necesario realizar una llamada adicional a <xref:System.Windows.Freezable.ReadPreamble%2A> si también leer miembros de datos de la propiedad de dependencia no.)  
  
-   Llame a la <xref:System.Windows.Freezable.WritePostscript%2A> método antes de salir de los métodos que se escriben a los miembros de datos de propiedad no son de dependencia.  
  
 Si la clase contiene miembros de datos de la propiedad de dependencia que son <xref:System.Windows.DependencyObject> objetos, también debe llamar a la <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> método cada vez que cambie uno de sus valores, incluso si está configurando el miembro a `null`.  
  
> [!NOTE]
>  Es muy importante iniciar cada <xref:System.Windows.Freezable> método que se reemplaza con una llamada a la implementación base.  
  
 Para obtener un ejemplo de un personalizado <xref:System.Windows.Freezable> de clases, vea el [ejemplo de animación personalizada](https://go.microsoft.com/fwlink/?LinkID=159981).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Freezable>
- [Ejemplo de animación personalizada](https://go.microsoft.com/fwlink/?LinkID=159981)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
