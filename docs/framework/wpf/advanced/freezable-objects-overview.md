---
title: "Informaci&#243;n general sobre objetos Freezable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "clases, Inmovilizable"
  - "Freezable (objetos), description"
  - "movilizar objetos Freezable"
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Informaci&#243;n general sobre objetos Freezable
En este tema se describe cómo utilizar y crear con eficacia objetos <xref:System.Windows.Freezable>, que proporcionan características especiales que pueden ayudar a mejorar el rendimiento de la aplicación.  Algunos ejemplos de objetos Freezable son los pinceles, los lápices, las transformaciones, las geometrías y las animaciones.  
  
 Este tema contiene las siguientes secciones:  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="whatisafreezable"></a>   
## ¿Qué es un objeto Freezable?  
 Un objeto <xref:System.Windows.Freezable> es un tipo especial de objeto que tiene dos estados: no inmovilizado e inmovilizado.  Cuando no está inmovilizado, un objeto <xref:System.Windows.Freezable> parece comportarse como cualquier otro objeto.  Cuando está inmovilizado, un objeto <xref:System.Windows.Freezable> ya no se puede modificar.  
  
 Un objeto <xref:System.Windows.Freezable> proporciona un evento <xref:System.Windows.Freezable.Changed> para notificar a los observadores todas las modificaciones del objeto.  Inmovilizar un objeto <xref:System.Windows.Freezable>, puede mejorar su rendimiento, porque ya no es preciso dedicar recursos a las notificaciones de cambio.  Un objeto <xref:System.Windows.Freezable> inmovilizado también se puede compartir entre subprocesos, lo que no sucede si el objeto <xref:System.Windows.Freezable> no está inmovilizado.  
  
 Aunque la clase <xref:System.Windows.Freezable> tiene muchas aplicaciones, la mayoría de los objetos <xref:System.Windows.Freezable> de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] están relacionados con el subsistema de gráficos.  
  
 La clase <xref:System.Windows.Freezable> facilita el uso de algunos objetos del sistema de gráficos y puede ayudar a mejorar el rendimiento de la aplicación.  Algunos ejemplos de tipos que heredan de <xref:System.Windows.Freezable> son las clases <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform> y <xref:System.Windows.Media.Geometry>.  Dado que contienen recursos no administrados, el sistema debe supervisar estos objetos por si se producen modificaciones y, a continuación, actualizar sus recursos no administrados correspondientes cuando se produce un cambio en el objeto original.  Aunque no se modifique realmente un objeto del sistema de gráficos, el sistema debe dedicar parte de sus recursos a supervisarlo, por si acaso cambia.  
  
 Por ejemplo, supongamos que se crea un pincel <xref:System.Windows.Media.SolidColorBrush> y se utiliza para pintar el fondo de un botón.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 Al representar el botón, el subsistema de gráficos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza la información que se proporciona para pintar un grupo de píxeles y crear el aspecto de un botón.  Aunque se ha utilizado un pincel de color sólido para describir cómo se debe pintar el botón, en realidad este pincel de color sólido no es el que se encarga de pintar.  El sistema de gráficos genera objetos rápidos de bajo nivel para el botón y el pincel, y son esos objetos los que realmente aparecen en la pantalla.  
  
 Si modifica el pincel, será preciso volver a generar estos objetos de bajo nivel.  La clase Freezable es lo que proporciona a un pincel la capacidad de buscar sus objetos generados de bajo nivel correspondientes y actualizarlos cuando cambian.  Cuando esta capacidad está habilitada, se dice que el pincel "no está inmovilizado".  
  
 El método <xref:System.Windows.Freezable.Freeze%2A> de un objeto Freezable permite deshabilitar esta capacidad de actualización automática.  Puede utilizar este método para "inmovilizar" el pincel, es decir, para que no se pueda modificar.  
  
> [!NOTE]
>  No todos los objetos Freezable se pueden inmovilizar.  Para evitar que se inicie una excepción <xref:System.InvalidOperationException>, compruebe el valor de la propiedad <xref:System.Windows.Freezable.CanFreeze%2A> del objeto Freezable, a fin de determinar si se puede inmovilizar antes de intentar inmovilizarlo.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Cuando ya no es necesario modificar un objeto Freezable, inmovilizarlo aporta ventajas de rendimiento.  Si en el ejemplo anterior inmoviliza el pincel, el sistema de gráficos ya no tendrá que supervisarlo por si cambia.  Además, el sistema de gráficos puede realizar otras optimizaciones, porque sabe que el pincel no cambiará.  
  
> [!NOTE]
>  Para mayor comodidad, los objetos Freezable permanecen no inmovilizados hasta que se inmovilizan de manera explícita.  
  
<a name="frozenfreezables"></a>   
## Utilizar Freezables  
 Utilizar un objeto Freezable no inmovilizado es igual que utilizar cualquier otro tipo de objeto.  En el ejemplo siguiente, se cambia el color de <xref:System.Windows.Media.SolidColorBrush> del amarillo al rojo después de utilizarlo para pintar el fondo de un botón.  El sistema de gráficos actúa en segundo plano para cambiar automáticamente el botón del amarillo al rojo la próxima vez que se actualiza la pantalla.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### Inmovilizar un objeto Freezable  
 Para impedir que un objeto <xref:System.Windows.Freezable>, se pueda modificar, llame a su método <xref:System.Windows.Freezable.Freeze%2A>.  Al inmovilizar un objeto que contiene objetos Freezable, éstos últimos se inmovilizan también.  Por ejemplo, si inmoviliza una <xref:System.Windows.Media.PathGeometry>, las figuras y los segmentos que contiene también se inmovilizan.  
  
 **No se puede** inmovilizar un objeto Freezable en ninguna de las situaciones siguientes:  
  
-   Tiene propiedades animadas o enlazadas a datos.  
  
-   Tiene propiedades establecidas por un recurso dinámico.  \(Para obtener más información acerca de recursos dinámicos, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).\)  
  
-   Contiene subobjetos <xref:System.Windows.Freezable> que no se pueden inmovilizar.  
  
 Si estas condiciones no se cumplen y tampoco tiene previsto modificar un objeto <xref:System.Windows.Freezable>, entonces es conveniente inmovilizarlo para obtener las ventajas de rendimiento descritas anteriormente.  
  
 Cuando se llama al método <xref:System.Windows.Freezable.Freeze%2A> de un objeto Freezable, éste ya no se puede modificar.  Si intenta modificar un objeto inmovilizado, se inicia una excepción <xref:System.InvalidOperationException>.  Al ejecutar el código siguiente se inicia una excepción, porque se intenta modificar el pincel después de inmovilizarlo.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Para evitar que se inicie esta excepción, puede utilizar el método <xref:System.Windows.Freezable.IsFrozen%2A> para determinar si un objeto <xref:System.Windows.Freezable> está inmovilizado.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 En el ejemplo de código anterior, se ha realizado una copia modificable de un objeto inmovilizado mediante el método <xref:System.Windows.Freezable.Clone%2A>.  En la sección siguiente se explica la clonación con más detalle.  
  
 **Nota**: puesto que los objetos Freezable inmovilizados no se pueden animar, el sistema de animación crea automáticamente clones modificables de los objetos <xref:System.Windows.Freezable> inmovilizados si intenta animarlos con <xref:System.Windows.Media.Animation.Storyboard>.  Para eliminar la sobrecarga de rendimiento causada por la clonación, no inmovilice los objetos si tiene previsto animarlos.  Para obtener más información sobre animación con guiones gráficos, consulte [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### Inmovilizar mediante marcado  
 Para inmovilizar un objeto <xref:System.Windows.Freezable> declarado en el marcado, se utiliza el atributo `PresentationOptions:Freeze`.  En el ejemplo siguiente, se declara <xref:System.Windows.Media.SolidColorBrush> como recurso de página y se inmoviliza.  A continuación, se utiliza para establecer el fondo de un botón.  
  
 [!code-xml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Para utilizar el atributo `Freeze`, debe efectuar la asignación al espacio de nombres de opciones de presentación: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.  `PresentationOptions` es el prefijo recomendado para asignar este espacio de nombres:  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Dado que no todos los lectores de XAML reconocen este atributo, se recomienda utilizar [Atributo mc:Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) para marcar el atributo `Presentation:Freeze` como omitible:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Para obtener más información, consulte la página [Atributo mc:Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).  
  
### "Liberar" un objeto Freezable  
 Una vez inmovilizado, un objeto <xref:System.Windows.Freezable> nunca se puede modificar ni liberar; sin embargo, sí puede crear un clon no inmovilizado mediante el método <xref:System.Windows.Freezable.Clone%2A> o <xref:System.Windows.Freezable.CloneCurrentValue%2A>.  
  
 En el ejemplo siguiente, se establece el fondo de un botón con un pincel y, a continuación, se inmoviliza el pincel.  Se realiza una copia no inmovilizada del pincel mediante el método <xref:System.Windows.Freezable.Clone%2A>.  El clon se modifica y se utiliza para cambiar el fondo del botón del amarillo al rojo.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Sea cual sea el método de clonación que utilice, las animaciones nunca se copian en el nuevo objeto <xref:System.Windows.Freezable>.  
  
 Los métodos <xref:System.Windows.Freezable.Clone%2A> y <xref:System.Windows.Freezable.CloneCurrentValue%2A> generan copias en profundidad del objeto Freezable.  Si el objeto Freezable contiene otros objetos Freezable inmovilizados, éstos también se clonan y son modificables.  Por ejemplo, si clona un <xref:System.Windows.Media.PathGeometry> inmovilizado para poder modificarlo, las figuras y los segmentos que contiene también se copian y se pueden modificar.  
  
<a name="createyourownfreezableclass"></a>   
## Crear su propia clase Freezable  
 Una clase que se deriva de <xref:System.Windows.Freezable> incluye las siguientes características.  
  
-   Estados especiales: estado de sólo lectura \(inmovilizado\) y estado modificable.  
  
-   Seguridad de subprocesos: un objeto <xref:System.Windows.Freezable> inmovilizado se puede compartir entre subprocesos.  
  
-   Notificación de los cambios detallados: a diferencia de otros objetos <xref:System.Windows.DependencyObject>, los objetos Freezable proporcionan notificaciones de cambios cuando cambian los valores de subpropiedad.  
  
-   Clonación fácil: la clase Freezable ya ha implementado varios métodos que generan clones perfectos.  
  
 Un objeto <xref:System.Windows.Freezable> es un tipo de <xref:System.Windows.DependencyObject> y, por consiguiente, utiliza el sistema de propiedades de dependencia.  No es necesario que las propiedades de clase sean propiedades de dependencia, pero al utilizar propiedades de dependencia se reduce la cantidad de código que hay que escribir, porque la clase <xref:System.Windows.Freezable> se ha diseñado teniendo en cuenta las propiedades de dependencia.  Para obtener más información sobre el sistema de propiedades de dependencia, consulte [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Cada subclase de <xref:System.Windows.Freezable> debe invalidar el método <xref:System.Windows.Freezable.CreateInstanceCore%2A>.  Si la clase utiliza propiedades de dependencia para todos los datos, con esto basta.  
  
 Si la clase contiene miembros de datos de propiedades que no son de dependencia, también debe invalidar los métodos siguientes:  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 También debe observar las reglas siguientes para obtener acceso a los miembros de datos que no son propiedades de dependencia y escribir en ellos:  
  
-   Al principio de cualquier [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] que lee miembros de datos de propiedades que no son de dependencia, llame al método <xref:System.Windows.Freezable.ReadPreamble%2A>.  
  
-   Al principio de cualquier API que escribe miembros de datos de propiedades que no son de dependencia, llame al método <xref:System.Windows.Freezable.WritePreamble%2A>.  \(Después de llamar al método <xref:System.Windows.Freezable.WritePreamble%2A> de una [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], ya no necesita realizar una llamada adicional a <xref:System.Windows.Freezable.ReadPreamble%2A> si también va a leer miembros de datos de propiedades que no son de dependencia.\)  
  
-   Llame al método <xref:System.Windows.Freezable.WritePostscript%2A> antes de salir de los métodos que escriben en los miembros de datos de propiedades que no son de dependencia.  
  
 Si la clase contiene miembros de datos de propiedades que no son de dependencia y que son objetos <xref:System.Windows.DependencyObject>, también debe llamar al método <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> cada vez que cambie uno de sus valores, aunque establezca el miembro en `null`.  
  
> [!NOTE]
>  Es muy importante que comience cada método de <xref:System.Windows.Freezable> que invalide con una llamada a la implementación base.  
  
 Para obtener un ejemplo de una clase <xref:System.Windows.Freezable> personalizada, vea [Custom Animation Sample](http://go.microsoft.com/fwlink/?LinkID=159981).  
  
## Vea también  
 <xref:System.Windows.Freezable>   
 [Ejemplo Custom Animation](http://go.microsoft.com/fwlink/?LinkID=159981)   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)