---
title: Información general sobre la navegación estructurada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- structured navigation [WPF]
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
ms.openlocfilehash: 5e8c27d017ed4bf8a7dcc2dda18877c9ed8dba69
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636346"
---
# <a name="structured-navigation-overview"></a>Información general sobre la navegación estructurada

El contenido que se puede hospedar en una aplicación de explorador XAML (XBAP), un <xref:System.Windows.Controls.Frame>o un <xref:System.Windows.Navigation.NavigationWindow> se compone de páginas que se pueden identificar por los identificadores uniformes de recursos (URI) del paquete y a los que se ha navegado por hipervínculos. La estructura de páginas y las formas en que se puede navegar por ellas, tal como se define mediante hipervínculos, se conoce como topología de navegación. Esta topología se adapta a diversos tipos de aplicaciones, especialmente a aquéllas que navegan por documentos. Con estas aplicaciones, el usuario puede navegar de una página a otra sin necesidad de saber nada sobre la otra.

Sin embargo, otros tipos de aplicaciones tienen páginas que necesitan saber cuándo se ha navegado entre ellas. Por ejemplo, suponga una aplicación de recursos humanos que tiene una página con una lista de todos los empleados de una organización, la página "Lista de empleados". Esta página también podría permitir a los usuarios agregar a un nuevo empleado haciendo clic en un hipervínculo. Al hacer clic en ella, la página navega a una página "Agregar un empleado" para recopilar los datos del nuevo empleado y llevarlos a la página "Lista de empleados" para crear al nuevo empleado y actualizar la lista. Este estilo de navegación es similar a llamar a un método para realizar algún procesamiento y devolver un valor, que se conoce como programación estructurada. Por tanto, este estilo de navegación se conoce como *navegación estructurada*.

La clase <xref:System.Windows.Controls.Page> no implementa la compatibilidad con la navegación estructurada. En su lugar, la clase <xref:System.Windows.Navigation.PageFunction%601> deriva de <xref:System.Windows.Controls.Page> y la extiende con las construcciones básicas necesarias para la navegación estructurada. En este tema se muestra cómo establecer la navegación estructurada mediante <xref:System.Windows.Navigation.PageFunction%601>.

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

Puede implementar estos comportamientos mediante el uso de un <xref:System.Windows.Navigation.PageFunction%601> como la página llamada.

<a name="Structured_Navigation_with_PageFunction"></a>

## <a name="structured-navigation-with-pagefunction"></a>Navegación estructurada con PageFunction

En este tema se muestra cómo implementar los mecanismos básicos de navegación estructurada que implican un único <xref:System.Windows.Navigation.PageFunction%601>. En este ejemplo, un <xref:System.Windows.Controls.Page> llama a un <xref:System.Windows.Navigation.PageFunction%601> para obtener un valor de <xref:System.String> del usuario y devolverlo.

### <a name="creating-a-calling-page"></a>Creación de una página que llama

La página que llama a un <xref:System.Windows.Navigation.PageFunction%601> puede ser una <xref:System.Windows.Controls.Page> o una <xref:System.Windows.Navigation.PageFunction%601>. En este ejemplo, es un <xref:System.Windows.Controls.Page>, como se muestra en el código siguiente.

[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]

[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]

### <a name="creating-a-page-function-to-call"></a>Creación de una función de página para realizar la llamada

Dado que la página que llama puede usar la página llamada para recopilar y devolver datos del usuario, <xref:System.Windows.Navigation.PageFunction%601> se implementa como una clase genérica cuyo argumento de tipo especifica el tipo del valor que devolverá la página llamada. En el código siguiente se muestra la implementación inicial de la página llamada mediante una <xref:System.Windows.Navigation.PageFunction%601>, que devuelve un <xref:System.String>.

[!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]

[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]

La declaración de una <xref:System.Windows.Navigation.PageFunction%601> es similar a la declaración de un <xref:System.Windows.Controls.Page> con la adición de los argumentos de tipo. Como puede ver en el ejemplo de código, se especifican los argumentos de tipo en el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], con el atributo `x:TypeArguments`, y en el código subyacente, con la sintaxis del argumento de tipo genérico estándar.

No tiene que usar solo .NET Framework clases como argumentos de tipo. Se podría llamar a <xref:System.Windows.Navigation.PageFunction%601> para recopilar datos específicos del dominio que se abstraen como un tipo personalizado. En el código siguiente se muestra cómo usar un tipo personalizado como un argumento de tipo para un <xref:System.Windows.Navigation.PageFunction%601>.

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

Los argumentos de tipo para el <xref:System.Windows.Navigation.PageFunction%601> proporcionan la base para la comunicación entre una página de llamada y la página llamada, que se describen en las secciones siguientes.

Como verá, el tipo que se identifica con la declaración de una <xref:System.Windows.Navigation.PageFunction%601> desempeña un papel importante en la devolución de datos de una <xref:System.Windows.Navigation.PageFunction%601> a la página que llama.

### <a name="calling-a-pagefunction-and-passing-parameters"></a>Llamada a una clase PageFunction y transmisión de parámetros

Para llamar a una página, la página que llama debe crear una instancia de la página llamada y navegar hasta ella con el método <xref:System.Windows.Navigation.NavigationService.Navigate%2A>. Esto permite que la página que llama pase los datos iniciales a la página llamada, como valores predeterminados para los datos recopilados por la página llamada.

En el código siguiente se muestra la página llamada con un constructor sin parámetros para aceptar parámetros de la página que llama.

[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]

En el código siguiente se muestra la página de llamada que controla el evento <xref:System.Windows.Documents.Hyperlink.Click> del <xref:System.Windows.Documents.Hyperlink> para crear una instancia de la página llamada y pasarle un valor de cadena inicial.

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

  2. Almacene los parámetros en <xref:System.Windows.Application.Properties%2A>.

  3. Navegue hasta el <xref:System.Windows.Navigation.PageFunction%601>llamado.

- Desde el <xref:System.Windows.Navigation.PageFunction%601>llamado:

  - Recupere y use los parámetros almacenados en <xref:System.Windows.Application.Properties%2A>.

Pero, como verá en breve, aún necesitará utilizar código para crear una instancia y navegar a la página llamada para recopilar los datos devueltos por la página llamada. Por esta razón, el <xref:System.Windows.Navigation.PageFunction%601> debe mantenerse activo; de lo contrario, la próxima vez que navegue al <xref:System.Windows.Navigation.PageFunction%601>, WPF crea una instancia del <xref:System.Windows.Navigation.PageFunction%601> mediante el constructor sin parámetros.

Sin embargo, antes de la página llamada pueda volver, debe devolver los datos para que los pueda recuperar la página que llama.

### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a>Devolución de los resultados y los datos de la tarea de una tarea a una página que llama

Una vez que el usuario ha terminado de utilizar la página llamada, en este ejemplo indicado al presionar los botones Aceptar o Cancelar, la página llamada debe volver. Puesto que la página que llama utilizó la página llamada para recopilar datos del usuario, la página que llama requiere dos tipos de información:

1. Si el usuario canceló la página llamada (presionando el botón Aceptar o el botón Cancelar en este ejemplo). Esto permite que la página que llama determine si se procesan los datos que recopiló del usuario.

2. Los datos proporcionados por el usuario.

Para devolver información, <xref:System.Windows.Navigation.PageFunction%601> implementa el método <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>. El siguiente código muestra cómo llamarlo.

[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]

En este ejemplo, si un usuario presiona el botón Cancelar, se devuelve un valor de `null` a la página que llama. En cambio, si se presiona el botón Aceptar, se devuelve el valor de cadena proporcionado por el usuario. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> es un método de `protected virtual` al que se llama para devolver los datos a la página que llama. Los datos se deben empaquetar en una instancia del tipo de <xref:System.Windows.Navigation.ReturnEventArgs%601> genérico, cuyo argumento de tipo especifica el tipo de valor que devuelve <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A>. De esta manera, cuando se declara un <xref:System.Windows.Navigation.PageFunction%601> con un argumento de tipo determinado, se indica que un <xref:System.Windows.Navigation.PageFunction%601> devolverá una instancia del tipo especificado por el argumento de tipo. En este ejemplo, el argumento de tipo y, por consiguiente, el valor devuelto es de tipo <xref:System.String>.

Cuando se llama a <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>, la página que llama necesita alguna manera de recibir el valor devuelto de la <xref:System.Windows.Navigation.PageFunction%601>. Por esta razón, <xref:System.Windows.Navigation.PageFunction%601> implementa el evento de <xref:System.Windows.Navigation.PageFunction%601.Return> para el control de las páginas de llamada. Cuando se llama a <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>, se genera <xref:System.Windows.Navigation.PageFunction%601.Return>, por lo que la página que llama puede registrarse con <xref:System.Windows.Navigation.PageFunction%601.Return> para recibir la notificación.

[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]

### <a name="removing-task-pages-when-a-task-completes"></a>Eliminación de páginas de tarea cuando se completa una tarea

Cuando vuelve una página llamada y el usuario no la había cancelado, la página que llama procesará los datos proporcionados por el usuario y los devueltos desde la página llamada. La adquisición de datos de esta manera suele ser una actividad aislada; cuando la página llamada vuelve, la página que llama debe crear y navegar a una nueva página que llama para capturar más datos.

Sin embargo, a menos que una página llamada se quite del diario, un usuario podrá volver a una instancia anterior de la página que llama. El hecho de que se conserve un <xref:System.Windows.Navigation.PageFunction%601> en el diario viene determinado por la propiedad <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A>. De forma predeterminada, una función de página se quita automáticamente cuando se llama a <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> porque <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> está establecido en `true`. Para mantener una función de página en el historial de navegación después de llamar a <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>, establezca <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> en `false`.

<a name="Other_Types_of_Structured_Navigation"></a>

## <a name="other-types-of-structured-navigation"></a>Otros tipos de navegación estructurada

En este tema se muestra el uso más básico de una <xref:System.Windows.Navigation.PageFunction%601> para admitir la navegación estructurada de llamada o devolución. Esta base proporciona la capacidad de crear tipos más complejos de navegación estructurada.

Por ejemplo, a veces son necesarias varias páginas en una página que llama para recopilar suficientes datos de un usuario o para realizar una tarea. El uso de varias páginas se conoce como un "asistente".

En otros casos, las aplicaciones pueden tener topologías de navegación complejas que dependen de la navegación estructurada para funcionar eficazmente. Para más información, consulte [Información general sobre topologías de navegación](navigation-topologies-overview.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [Información general sobre topologías de navegación](navigation-topologies-overview.md)
