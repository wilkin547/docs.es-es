---
title: Información general sobre la navegación estructurada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- structured navigation [WPF]
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
ms.openlocfilehash: 8760c847d9e73fdff9f10f0dfa55a6c674021667
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364177"
---
# <a name="structured-navigation-overview"></a>Información general sobre la navegación estructurada

El contenido que se puede hospedar [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]mediante un <xref:System.Windows.Controls.Frame>, un o <xref:System.Windows.Navigation.NavigationWindow> un se compone de páginas que se pueden identificar por [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] módulo y a través de hipervínculos. La estructura de páginas y las formas en que se puede navegar por ellas, tal como se define mediante hipervínculos, se conoce como topología de navegación. Esta topología se adapta a diversos tipos de aplicaciones, especialmente a aquéllas que navegan por documentos. Con estas aplicaciones, el usuario puede navegar de una página a otra sin necesidad de saber nada sobre la otra.

Sin embargo, otros tipos de aplicaciones tienen páginas que necesitan saber cuándo se ha navegado entre ellas. Por ejemplo, suponga una aplicación de recursos humanos que tiene una página con una lista de todos los empleados de una organización, la página "Lista de empleados". Esta página también podría permitir a los usuarios agregar a un nuevo empleado haciendo clic en un hipervínculo. Al hacer clic en ella, la página navega a una página "Agregar un empleado" para recopilar los datos del nuevo empleado y llevarlos a la página "Lista de empleados" para crear al nuevo empleado y actualizar la lista. Este estilo de navegación es similar a llamar a un método para realizar algún procesamiento y devolver un valor, que se conoce como programación estructurada. Por tanto, este estilo de navegación se conoce como *navegación estructurada*.

La <xref:System.Windows.Controls.Page> clase no implementa la compatibilidad con la navegación estructurada. En su lugar, <xref:System.Windows.Navigation.PageFunction%601> la clase se deriva <xref:System.Windows.Controls.Page> de y lo extiende con las construcciones básicas necesarias para la navegación estructurada. En este tema se muestra cómo establecer la navegación <xref:System.Windows.Navigation.PageFunction%601>estructurada mediante.

<a name="Structured_Navigation"></a>

## <a name="structured-navigation"></a>Navegación estructurada

Cuando una página llama a otra página en una navegación estructurada, se requieren algunos o todos los comportamientos siguientes:

- La página que llama navega a la página llamada y, opcionalmente, pasa los parámetros requeridos por la página llamada.

- La página llamada, cuando un usuario ha terminado de usar la página que llama, vuelve específicamente a la página que llama y, opcionalmente:

  - Devuelve información de estado que describe cómo se completó la página que llama (por ejemplo, si un usuario presionó un botón Aceptar o Cancelar).

  - Devuelve los datos recopilados del usuario (por ejemplo, los datos de un nuevo empleado).

- Cuando se devuelve la página que llama a la página llamada, la página llamada se quita del historial de navegación para aislar cada instancia de una página llamada de otra.

Estos comportamientos se muestran en la ilustración siguiente:

![Captura de pantalla que muestra el flujo entre la página que llama y la página llamada.](./media/structured-navigation-overview/flow-between-calling-page-called-page.png)

Puede implementar estos comportamientos mediante un <xref:System.Windows.Navigation.PageFunction%601> como la página llamada.

<a name="Structured_Navigation_with_PageFunction"></a>

## <a name="structured-navigation-with-pagefunction"></a>Navegación estructurada con PageFunction

En este tema se muestra cómo implementar los mecanismos básicos de navegación estructurada que implican un único <xref:System.Windows.Navigation.PageFunction%601>. En este ejemplo, <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.PageFunction%601> llama a para obtener un <xref:System.String> valor del usuario y devolverlo.

### <a name="creating-a-calling-page"></a>Creación de una página que llama

La página que llama a <xref:System.Windows.Navigation.PageFunction%601> puede ser <xref:System.Windows.Controls.Page> o <xref:System.Windows.Navigation.PageFunction%601>. En este ejemplo, es <xref:System.Windows.Controls.Page>, tal y como se muestra en el código siguiente.

[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]

[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]

### <a name="creating-a-page-function-to-call"></a>Creación de una función de página para realizar la llamada

Dado que la página que llama puede usar la página llamada para recopilar y devolver datos del <xref:System.Windows.Navigation.PageFunction%601> usuario, se implementa como una clase genérica cuyo argumento de tipo especifica el tipo del valor que devolverá la página llamada. En el código siguiente se muestra la implementación inicial de la página llamada, <xref:System.Windows.Navigation.PageFunction%601>utilizando, que <xref:System.String>devuelve.

[!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]

[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]

La declaración de <xref:System.Windows.Navigation.PageFunction%601> es similar a la declaración de un <xref:System.Windows.Controls.Page> con la adición de los argumentos de tipo. Como puede ver en el ejemplo de código, se especifican los argumentos de tipo en el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], con el atributo `x:TypeArguments`, y en el código subyacente, con la sintaxis del argumento de tipo genérico estándar.

No tiene que usar solo .NET Framework clases como argumentos de tipo. <xref:System.Windows.Navigation.PageFunction%601> Se podría llamar a para recopilar datos específicos del dominio que se abstraen como un tipo personalizado. En el código siguiente se muestra cómo usar un tipo personalizado como un argumento de tipo <xref:System.Windows.Navigation.PageFunction%601>para.

[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode1)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode1)]
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode2)]

[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup1)]
[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup2)]

[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind1)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind1)]
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind2)]

Los argumentos de tipo de <xref:System.Windows.Navigation.PageFunction%601> proporcionan la base para la comunicación entre una página de llamada y la página llamada, que se describen en las secciones siguientes.

Como verá, el tipo que se identifica con la declaración de una <xref:System.Windows.Navigation.PageFunction%601> desempeña un papel importante en la devolución de datos <xref:System.Windows.Navigation.PageFunction%601> de a la página que llama.

### <a name="calling-a-pagefunction-and-passing-parameters"></a>Llamada a una clase PageFunction y transmisión de parámetros

Para llamar a una página, la página que llama debe crear una instancia de la página llamada y navegar <xref:System.Windows.Navigation.NavigationService.Navigate%2A> hasta ella mediante el método. Esto permite que la página que llama pase los datos iniciales a la página llamada, como valores predeterminados para los datos recopilados por la página llamada.

En el código siguiente se muestra la página llamada con un constructor sin parámetros para aceptar parámetros de la página que llama.

[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]

En el código siguiente se muestra la página de <xref:System.Windows.Documents.Hyperlink.Click> llamada que controla el evento de para crear una instancia de la página llamada y pasarle un valor de cadena inicial. <xref:System.Windows.Documents.Hyperlink>

[!code-xaml[StructuredNavigationSample#PassingDataMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]

No es necesario pasar parámetros a la página llamada. En su lugar, podría hacer lo siguiente:

- En la página que llama:

  1. Cree una instancia del <xref:System.Windows.Navigation.PageFunction%601> llamado mediante el constructor sin parámetros.

  2. Almacene los parámetros <xref:System.Windows.Application.Properties%2A>en.

  3. Navegue al llamado <xref:System.Windows.Navigation.PageFunction%601>.

- Del llamado <xref:System.Windows.Navigation.PageFunction%601>:

  - Recupere y use los parámetros almacenados <xref:System.Windows.Application.Properties%2A>en.

Pero, como verá en breve, aún necesitará utilizar código para crear una instancia y navegar a la página llamada para recopilar los datos devueltos por la página llamada. Por esta razón, el <xref:System.Windows.Navigation.PageFunction%601> debe mantenerse activo; de lo contrario, la próxima vez que navegue <xref:System.Windows.Navigation.PageFunction%601>a, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] crea una instancia de <xref:System.Windows.Navigation.PageFunction%601> mediante el constructor sin parámetros.

Sin embargo, antes de la página llamada pueda volver, debe devolver los datos para que los pueda recuperar la página que llama.

### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a>Devolución de los resultados y los datos de la tarea de una tarea a una página que llama

Una vez que el usuario ha terminado de utilizar la página llamada, en este ejemplo indicado al presionar los botones Aceptar o Cancelar, la página llamada debe volver. Puesto que la página que llama utilizó la página llamada para recopilar datos del usuario, la página que llama requiere dos tipos de información:

1. Si el usuario canceló la página llamada (presionando el botón Aceptar o el botón Cancelar en este ejemplo). Esto permite que la página que llama determine si se procesan los datos que recopiló del usuario.

2. Los datos proporcionados por el usuario.

Para devolver información, <xref:System.Windows.Navigation.PageFunction%601> implementa el <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> método. El siguiente código muestra cómo llamarlo.

[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]

En este ejemplo, si un usuario presiona el botón Cancelar, se devuelve un valor de `null` a la página que llama. En cambio, si se presiona el botón Aceptar, se devuelve el valor de cadena proporcionado por el usuario. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>es un `protected virtual` método al que se llama para devolver los datos a la página que llama. Los datos se deben empaquetar en una instancia del tipo genérico <xref:System.Windows.Navigation.ReturnEventArgs%601> , cuyo argumento de tipo especifica el tipo de valor que <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> devuelve. De esta manera, cuando se declara un <xref:System.Windows.Navigation.PageFunction%601> con un argumento de tipo determinado, se indica que un <xref:System.Windows.Navigation.PageFunction%601> devolverá una instancia del tipo especificado por el argumento de tipo. En este ejemplo, el argumento de tipo y, por consiguiente, el valor devuelto es <xref:System.String>de tipo.

Cuando <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> se llama a, la página que llama necesita alguna manera de recibir el valor devuelto <xref:System.Windows.Navigation.PageFunction%601>de. Por esta razón, <xref:System.Windows.Navigation.PageFunction%601> implementa el <xref:System.Windows.Navigation.PageFunction%601.Return> evento para controlar las páginas que se van a llamar. Cuando <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> se llama <xref:System.Windows.Navigation.PageFunction%601.Return> a <xref:System.Windows.Navigation.PageFunction%601.Return> , se produce, por lo que la página que llama puede registrarse en para recibir la notificación.

[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]

### <a name="removing-task-pages-when-a-task-completes"></a>Eliminación de páginas de tarea cuando se completa una tarea

Cuando vuelve una página llamada y el usuario no la había cancelado, la página que llama procesará los datos proporcionados por el usuario y los devueltos desde la página llamada. La adquisición de datos de esta manera suele ser una actividad aislada; cuando la página llamada vuelve, la página que llama debe crear y navegar a una nueva página que llama para capturar más datos.

Sin embargo, a menos que una página llamada se quite del diario, un usuario podrá volver a una instancia anterior de la página que llama. El hecho <xref:System.Windows.Navigation.PageFunction%601> de que un se retenga en el diario <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> viene determinado por la propiedad. De forma predeterminada, una función de página se quita <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> automáticamente cuando se <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> llama a porque `true`está establecido en. Para mantener una función de página en el historial <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> de navegación después de <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> llamar `false`a, establezca en.

<a name="Other_Types_of_Structured_Navigation"></a>

## <a name="other-types-of-structured-navigation"></a>Otros tipos de navegación estructurada

<xref:System.Windows.Navigation.PageFunction%601> En este tema se muestra el uso más básico de para admitir la navegación estructurada de llamada o devolución. Esta base proporciona la capacidad de crear tipos más complejos de navegación estructurada.

Por ejemplo, a veces son necesarias varias páginas en una página que llama para recopilar suficientes datos de un usuario o para realizar una tarea. El uso de varias páginas se conoce como un "asistente".

En otros casos, las aplicaciones pueden tener topologías de navegación complejas que dependen de la navegación estructurada para funcionar eficazmente. Para más información, consulte [Información general sobre topologías de navegación](navigation-topologies-overview.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [Información general sobre topologías de navegación](navigation-topologies-overview.md)
