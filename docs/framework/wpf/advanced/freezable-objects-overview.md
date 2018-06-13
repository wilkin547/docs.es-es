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
ms.openlocfilehash: d3b9f6f7af22b2a846f4ee34e8d4d00bb032fd69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548475"
---
# <a name="freezable-objects-overview"></a>Información general sobre objetos Freezable
Este tema describe cómo utilizar y crear de forma eficaz <xref:System.Windows.Freezable> objetos, que proporcionan características especiales que pueden ayudar a mejorar el rendimiento de la aplicación. Pinceles, lápices, las transformaciones, las geometrías y las animaciones son ejemplos de objetos freezable.  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a>¿Qué es un objeto Freezable?  
 A <xref:System.Windows.Freezable> es un tipo especial de objeto que tiene dos estados: no inmovilizado e inmovilizado. Cuando no está inmovilizado, un <xref:System.Windows.Freezable> parece comportarse como cualquier otro objeto. Cuando está inmovilizado, un <xref:System.Windows.Freezable> ya no se puede modificar.  
  
 A <xref:System.Windows.Freezable> proporciona un <xref:System.Windows.Freezable.Changed> eventos para notificar a los observadores ninguna modificación en el objeto. Inmovilizar un <xref:System.Windows.Freezable> puede mejorar su rendimiento, porque ya no es necesario dedicar recursos a las notificaciones de cambio. Inmovilizado <xref:System.Windows.Freezable> también se pueden compartir entre subprocesos, mientras un inmovilizadas <xref:System.Windows.Freezable> no puede.  
  
 Aunque la <xref:System.Windows.Freezable> clase tiene muchas aplicaciones, más <xref:System.Windows.Freezable> objetos en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] están relacionados con el subsistema de gráficos.  
  
 La <xref:System.Windows.Freezable> clase resulta más fácil utilizar ciertos objetos de sistema de gráficos y puede ayudar a mejorar el rendimiento de la aplicación. Algunos ejemplos de tipos que heredan de <xref:System.Windows.Freezable> incluyen el <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, y <xref:System.Windows.Media.Geometry> clases. Dado que contienen recursos no administrados, el sistema debe supervisar estos objetos para que las modificaciones y, a continuación, actualizar sus recursos no administrados correspondientes cuando se produce un cambio en el objeto original. Incluso si no modifica realmente un objeto del sistema de gráficos, el sistema debe dedicar algunos de sus recursos en el objeto de supervisión en caso de que se efectúan cambios en ella.  
  
 Por ejemplo, suponga que crea un <xref:System.Windows.Media.SolidColorBrush> de pincel y utilizarlo para pintar el fondo de un botón.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 Cuando se representa el botón, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] subsistema de gráficos utiliza la información proporcionada para pintar un grupo de píxeles para crear la apariencia de un botón. Aunque se ha utilizado un pincel de color sólido para describir cómo se debe pintar el botón, el pincel de color sólido no lleva a cabo la actualización. El sistema de gráficos genera objetos rápidos y bajo nivel para el botón y el pincel, y son los objetos a los que realmente aparecen en la pantalla.  
  
 Si fuera a modificar el pincel, esos objetos de bajo nivel que se vuelven a generar. La clase freezable es lo que da un pincel la capacidad para buscar sus objetos generados de bajo nivel correspondientes y actualizarlos cuando el estado cambia. Cuando esta capacidad está habilitada, se dice que el pincel "no está inmovilizado".  
  
 Un objeto inmovilizable <xref:System.Windows.Freezable.Freeze%2A> método le permite deshabilitar esta capacidad de actualización automática. Puede usar este método para realizar el pincel se convierten en "inmovilizado" o no modificable.  
  
> [!NOTE]
>  No todos los objetos Freezable se pueden inmovilizar. Para evitar que se produzca una <xref:System.InvalidOperationException>, compruebe el valor del objeto Freezable <xref:System.Windows.Freezable.CanFreeze%2A> propiedad para determinar si se puede inmovilizar antes de intentar la inmoviliza.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Cuando ya no necesite modificar un objeto freezable, inmovilizarlo proporciona ventajas de rendimiento. Si deseara inmoviliza el pincel en este ejemplo, el sistema de gráficos ya no se necesitaría supervisar cambios. El sistema de gráficos también puede realizar otras optimizaciones, ya que sabe que no cambiará el pincel.  
  
> [!NOTE]
>  Para mayor comodidad, los objetos freezable permanecen inmovilizados a menos que se inmovilizan de manera explícita.  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a>Utilizar Freezables  
 Mediante un inmovilizadas freezable es similar al uso de cualquier otro tipo de objeto. En el ejemplo siguiente, el color de un <xref:System.Windows.Media.SolidColorBrush> cambia de amarillo a rojo después de que se usa para pintar el fondo de un botón. El sistema de gráficos funciona en segundo plano para cambiar automáticamente el botón de amarillo a rojo la próxima vez que se actualiza la pantalla.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a>Inmovilizar un objeto Freezable  
 Para realizar una <xref:System.Windows.Freezable> sea no modificable, se llama a su <xref:System.Windows.Freezable.Freeze%2A> método. Al inmovilizar un objeto que contiene objetos freezable, esos objetos también se inmovilizan. Por ejemplo, si inmoviliza un <xref:System.Windows.Media.PathGeometry>, las figuras y los segmentos que contiene también se inmovilizan.  
  
 Un elemento Freezable **no** inmovilizar si se cumple alguna de las siguientes acciones:  
  
-   Ha animado o propiedades enlazado a datos.  
  
-   Tiene propiedades establecidas por un recurso dinámico. (Consulte la [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) para obtener más información acerca de recursos dinámicos.)  
  
-   Contiene <xref:System.Windows.Freezable> objetos secundarios que no se pueden inmovilizar.  
  
 Si estas condiciones son false, y no va a modificar el <xref:System.Windows.Freezable>, a continuación, se debe inmovilizar para obtener las ventajas de rendimiento se ha descrito anteriormente.  
  
 Una vez que se llama a un objeto inmovilizable <xref:System.Windows.Freezable.Freeze%2A> método, ya no se puede modificar. Al intentar modificar inmovilizado objeto causas un <xref:System.InvalidOperationException> que se produzca. El código siguiente produce una excepción, porque se intenta modificar el pincel después de que se ha inmovilizado.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Para evitar que se produzca esta excepción, puede usar el <xref:System.Windows.Freezable.IsFrozen%2A> método para determinar si un <xref:System.Windows.Freezable> está inmovilizado.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 En el ejemplo de código anterior, se ha realizado una copia modificable de un objeto inmovilizado mediante el <xref:System.Windows.Freezable.Clone%2A> método. La siguiente sección explica la clonación con más detalle.  
  
 **Tenga en cuenta** porque inmovilizado freezable no se pueden animar, el sistema de animación creará automáticamente clones modificables de inmovilizado <xref:System.Windows.Freezable> objetos al intentar animarlos con un <xref:System.Windows.Media.Animation.Storyboard>. Para eliminar la sobrecarga de rendimiento causada por la clonación, deje un objeto movilizar si piensa animarlo. Para obtener más información sobre la animación con guiones gráficos, vea la [información general de guiones gráficos](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="freezing-from-markup"></a>Inmovilización de marcado  
 Para inmovilizar un <xref:System.Windows.Freezable> objeto declarado en el marcado, se utiliza el `PresentationOptions:Freeze` atributo. En el ejemplo siguiente, un <xref:System.Windows.Media.SolidColorBrush> se declara como un recurso de página e inmovilizado. A continuación, sirve para establecer el fondo de un botón.  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Para usar el `Freeze` atributo, debe asignar el espacio de nombres de opciones de presentación: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` es el prefijo recomendado para asignar este espacio de nombres:  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Dado que no todos los lectores XAML reconocen este atributo, se recomienda que utilice la [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) para marcar el `Presentation:Freeze` atributo como puede pasar por alto:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Para obtener más información, consulte el [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) página.  
  
### <a name="unfreezing-a-freezable"></a>"Liberar" un objeto Freezable  
 Una vez inmovilizado, un <xref:System.Windows.Freezable> nunca se pueden modificar o movilizar; sin embargo, puede crear un clon no inmovilizado mediante el <xref:System.Windows.Freezable.Clone%2A> o <xref:System.Windows.Freezable.CloneCurrentValue%2A> método.  
  
 En el ejemplo siguiente, se establece el fondo del botón con un pincel de diseño y, a continuación, se inmoviliza el pincel. Se realiza una copia no inmovilizada del pincel con la <xref:System.Windows.Freezable.Clone%2A> método. El clon se modifica y se utiliza para cambiar el fondo del botón de amarillo a rojo.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Independientemente de qué método de clonación que use, animaciones nunca se copian en el nuevo <xref:System.Windows.Freezable>.  
  
 El <xref:System.Windows.Freezable.Clone%2A> y <xref:System.Windows.Freezable.CloneCurrentValue%2A> métodos generan copias en profundidad del objeto freezable. Si el objeto freezable contiene otros objetos freezable inmovilizados, también se clonan y son modificables. Por ejemplo, si se clona inmovilizado <xref:System.Windows.Media.PathGeometry> para que sea modificable, las figuras y los segmentos que contiene se también copian y se pueden modificar.  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a>Crear su propia clase Freezable  
 Una clase que deriva de <xref:System.Windows.Freezable> incluye las siguientes características.  
  
-   Estados especiales: solo lectura (inmovilizado) y un estado de escritura.  
  
-   Seguridad para subprocesos: inmovilizado <xref:System.Windows.Freezable> se pueden compartir entre subprocesos.  
  
-   Obtener la notificación de cambio: a diferencia de otras <xref:System.Windows.DependencyObject>s, objetos Freezable proporcionan notificaciones de cambio cuando cambian los valores de la subpropiedad.  
  
-   Clonación fácil: la clase Freezable ya ha implementado varios métodos que generan clones profundos.  
  
 A <xref:System.Windows.Freezable> es un tipo de <xref:System.Windows.DependencyObject>y, por tanto, utiliza el sistema de propiedades de dependencia. Las propiedades de clase no tienen propiedades de dependencia, pero con las propiedades de dependencia se reduce la cantidad de código que se debe escribir, porque la <xref:System.Windows.Freezable> clase se diseñó teniendo en cuenta las propiedades de dependencia. Para obtener más información sobre el sistema de propiedad de dependencia, vea el [información general sobre propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Cada <xref:System.Windows.Freezable> subclase debe invalidar el <xref:System.Windows.Freezable.CreateInstanceCore%2A> método. Si la clase utiliza propiedades de dependencia para todos sus datos, habrá terminado.  
  
 Si la clase contiene a miembros de datos de la propiedad de dependencia no, también debe invalidar los métodos siguientes:  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 También debe cumplir las reglas siguientes para obtener acceso y escribir en los miembros de datos que no son propiedades de dependencia:  
  
-   Al principio de cualquier [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] que lee los miembros de datos de la propiedad de dependencia no, llame a la <xref:System.Windows.Freezable.ReadPreamble%2A> método.  
  
-   Al principio de cualquier API que escribe miembros de datos de la propiedad de dependencia no, llame a la <xref:System.Windows.Freezable.WritePreamble%2A> método. (Una vez que se ha llamado a <xref:System.Windows.Freezable.WritePreamble%2A> en un [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], no es necesario realizar una llamada adicional al <xref:System.Windows.Freezable.ReadPreamble%2A> si también leer miembros de datos de la propiedad de dependencia no.)  
  
-   Llame a la <xref:System.Windows.Freezable.WritePostscript%2A> método antes de salir de métodos que escriben en los miembros de datos de propiedad de dependencia no.  
  
 Si la clase contiene miembros de datos de la propiedad de dependencia que son <xref:System.Windows.DependencyObject> objetos, también debe llamar a la <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> método cada vez que cambie uno de sus valores, incluso si está configurando el miembro a `null`.  
  
> [!NOTE]
>  Es muy importante que comience cada uno <xref:System.Windows.Freezable> método invalide con una llamada a la implementación base.  
  
 Para obtener un ejemplo de un personalizado <xref:System.Windows.Freezable> de clases, consulte la [Custom Animation Sample](http://go.microsoft.com/fwlink/?LinkID=159981).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Freezable>  
 [Ejemplo de animación personalizada](http://go.microsoft.com/fwlink/?LinkID=159981)  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
