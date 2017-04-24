---
title: "Realizar pruebas de posicionamiento en la capa visual | Microsoft Docs"
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
  - "funcionalidad de prueba de posicionamiento"
  - "capa visual, funcionalidad de prueba de posicionamiento"
ms.assetid: b1a64b61-14be-4d75-b89a-5c67bebb2c7b
caps.latest.revision: 42
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 41
---
# Realizar pruebas de posicionamiento en la capa visual
En este tema se proporciona información general sobre la funcionalidad de prueba de posicionamiento que proporciona la capa visual.  La compatibilidad con la prueba de posicionamiento permite determinar si el valor de una geometría o de un punto pertenece al contenido representado de un objeto <xref:System.Windows.Media.Visual>, lo que permite implementar comportamientos de interfaz de usuario tal como un rectángulo de selección para seleccionar varios objetos.  
  
   
  
<a name="hit_testing_scenarios"></a>   
## Escenarios de pruebas de posicionamiento  
 La clase <xref:System.Windows.UIElement> proporciona el método <xref:System.Windows.UIElement.InputHitTest%2A>, que permite realizar pruebas de posicionamiento frente a un elemento utilizando un valor de coordenadas determinado.  En muchos casos, el método <xref:System.Windows.UIElement.InputHitTest%2A> proporciona la funcionalidad deseada para implementar las pruebas de posicionamiento de elementos.  Sin embargo, hay varios escenarios en los que puede necesitar implementar pruebas de posicionamiento en la capa visual.  
  
-   Pruebas de posicionamiento frente a objetos que no sean <xref:System.Windows.UIElement>: esto se aplica si se está realizando pruebas de posicionamiento para objetos que no sean <xref:System.Windows.UIElement>, tales como objetos <xref:System.Windows.Media.DrawingVisual> u objetos gráficos.  
  
-   Pruebas de posicionamiento usando una geometría: esto se aplica si necesita realizar una prueba de posicionamiento usando un objeto de geometría en lugar del valor de coordenadas de un punto.  
  
-   Pruebas de posicionamiento frente a varios objetos: esto se aplica cuando se necesita realizar pruebas de posicionamiento frente a varios objetos, tales como objetos superpuestos.  Puede obtener resultados para todos los elementos visuales que corten una geometría o un punto, no solamente para el primero.  
  
-   Omitir la directiva de prueba de posicionamiento de <xref:System.Windows.UIElement>: esto se aplica cuando se necesita omitir la directiva de prueba de posicionamiento de <xref:System.Windows.UIElement>, la que tiene en cuenta factores tales como si un elemento está deshabilitado o no visible.  
  
> [!NOTE]
>  Para obtener un ejemplo de código completo que muestra la prueba de posicionamiento en la capa visual, vea [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994) y [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="hit_testing_support"></a>   
## Compatibilidad con la prueba de posicionamiento  
 El propósito de los métodos <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> de la clase <xref:System.Windows.Media.VisualTreeHelper> es determinar si una geometría o un valor de coordenadas de punto está dentro del contenido representado de un objeto determinado, tal como un control o un elemento gráfico.  Por ejemplo, podría utilizar la prueba de posicionamiento para determinar si un clic del mouse dentro del rectángulo delimitador de un objeto pertenece a la geometría de un círculo.  También puede decidir invalidar la implementación predeterminada de la prueba de posicionamiento, para realizar cálculos propios en las pruebas de posicionamiento.  
  
 La ilustración siguiente muestra la relación entre la región de un objeto no rectangular y su rectángulo delimitador.  
  
 ![Diagrama de región de prueba de posicionamiento válida](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-hittest-1.png "wcpsdk\_mmgraphics\_visuals\_hittest\_1")  
Diagrama de la región válida para la prueba de posicionamiento  
  
<a name="hit_testing_and_z-order"></a>   
## Prueba de posicionamiento y orden z  
 La capa visual de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] admite la prueba de posicionamiento frente a todos los objetos situados bajo un punto o una geometría, no solamente para el objeto de nivel superior.  Los resultados se devuelven en un [orden z](GTMT).  Sin embargo, el objeto visual que se pasa como parámetro al método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> determina qué parte del [árbol visual](GTMT) se someterá a la prueba de posicionamiento.  Puede realizar la prueba de posicionamiento frente al árbol visual completo o frente a cualquier parte de él.  
  
 En la ilustración siguiente, el objeto de círculo está encima del objeto cuadrado y del triangular.  Si solamente le interesa la prueba de posicionamiento del objeto visual cuyo valor de [orden z](GTMT) es el superior, puede configurar la enumeración de prueba de posicionamiento visual para que devuelva <xref:System.Windows.Media.HitTestResultBehavior> de <xref:System.Windows.Media.HitTestResultCallback> para detener la exploración transversal de la prueba de posicionamiento después del primer elemento.  
  
 ![Diagrama del orden z de un árbol visual](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-hittest-2.png "wcpsdk\_mmgraphics\_visuals\_hittest\_2")  
Diagrama del orden z de un árbol visual  
  
 Si desea enumerar todos los objetos visuales bajo un punto o geometría concretos, devuelva <xref:System.Windows.Media.HitTestResultBehavior> desde <xref:System.Windows.Media.HitTestResultCallback>.  Esto significa que puede realizar pruebas de posicionamiento para objetos visuales que estén bajo otros objetos, aunque estén completamente ocultos.  Vea el ejemplo de código en la sección "Utilizar una devolución de llamada de resultados de pruebas de posicionamiento" para obtener más información.  
  
> [!NOTE]
>  Un objeto visual transparente también se puede someter a una prueba de posicionamiento.  
  
<a name="using_default_hit_testing"></a>   
## Usar la prueba de posicionamiento predeterminada  
 Puede identificar si un punto está dentro de la geometría de un objeto visual utilizando el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> para especificar un objeto visual y un valor de coordenadas de punto para la prueba.  El parámetro de objeto visual identifica el punto inicial en el árbol visual para la búsqueda de la prueba de posicionamiento.  Si un objeto visual se encuentra en el árbol visual cuya geometría contiene las coordenadas, se establece en la propiedad <xref:System.Windows.Media.HitTestResult.VisualHit%2A> de un objeto <xref:System.Windows.Media.HitTestResult>.  A continuación, se devuelve <xref:System.Windows.Media.HitTestResult> desde el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  Si el punto no está contenido en el subárbol visual que se está sometiendo a la prueba de posicionamiento, <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> devuelve `null`.  
  
> [!NOTE]
>  La prueba de posicionamiento predeterminada devuelve el objeto de nivel superior en el [orden z](GTMT).  Para identificar todos los objetos visuales, incluso aquéllos que puedan estar ocultos, en parte o completamente, utilice una devolución de llamada de resultado de prueba de posicionamiento.  
  
 El valor de coordenadas que pase como parámetro de punto para el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> debe ser relativo al espacio de coordenadas del objeto visual para el que se esté realizando la prueba de posicionamiento.  Por ejemplo, si ha anidado objetos visuales definidos en \(100, 100\) en el espacio de coordenadas del elemento primario, la prueba de posicionamiento de un elemento secundario visual en \(0, 0\) es equivalente a la prueba de posicionamiento en \(100, 100\) en el espacio de coordenadas del elemento primario.  
  
 El código siguiente muestra cómo configurar controladores de eventos del mouse para un objeto <xref:System.Windows.UIElement> que se utiliza para capturar eventos utilizados para la prueba de posicionamiento.  
  
 [!code-csharp[HitTestingOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[HitTestingOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#100)]  
  
### Cómo afecta el árbol visual a la prueba de posicionamiento  
 El punto inicial en el árbol visual determina qué objetos se devuelven durante la enumeración de objetos de la prueba de posicionamiento.  Si tiene varios objetos que desea someter a la prueba de posicionamiento, el objeto visual utilizado como punto inicial en el árbol visual debe ser el antecesor común de todos los objetos de interés.  Por ejemplo, si estuviera interesado en la prueba de posicionamiento tanto del elemento de botón como del elemento visual de dibujo del diagrama siguiente, tendría que establecer el punto inicial del árbol visual en el antecesor común de ambos.  En este caso, el elemento de lienzo es el antecesor común del elemento de botón y del elemento visual de dibujo.  
  
 ![Diagrama de una jerarquía de árbol visual](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-overview-01.png "wcpsdk\_mmgraphics\_visuals\_overview\_01")  
Diagrama de jerarquía del árbol visuial  
  
> [!NOTE]
>  La propiedad <xref:System.Windows.UIElement.IsHitTestVisible%2A> obtiene o establece un valor que declara si un objeto derivado de <xref:System.Windows.UIElement> se puede devolver como un resultado de prueba de posicionamiento de alguna parte de su contenido representado.  Esto permite modificar selectivamente el árbol visual para determinar qué objetos visuales están implicados en una prueba de posicionamiento.  
  
<a name="using_a_hit_test_result_callback"></a>   
## Utilizar una devolución de llamada de resultados de prueba de posicionamiento  
 Puede enumerar todos los objetos visuales de un árbol visual cuya geometría contenga un valor de coordenadas especificado.  Esto permite identificar todos los objetos visuales, incluso aquéllos que puedan estar ocultos, en parte o completamente, por otros objetos visuales.  Enumerar los objetos visuales de un árbol visual, utilice el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> con una función de devolución de llamada de la prueba de posicionamiento.  El sistema llama a la función de devolución de llamada de la prueba de posicionamiento cuando el valor de coordenadas especificado esté contenido en un objeto visual.  
  
 Durante la enumeración de resultados de pruebas de posicionamiento no se debe realizar ninguna operación que modifique el árbol visual.  Agregar o quitar un objeto del árbol visual mientras se está recorriendo puede producir un comportamiento imprevisible.  Puede modificar sin ningún riesgo el árbol visual una vez que vuelva el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  Quizá desee proporcionar una estructura de datos, tal como un objeto <xref:System.Collections.ArrayList>, para almacenar los valores durante la enumeración de resultados de pruebas de posicionamiento.  
  
 [!code-csharp[HitTestingOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[HitTestingOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#101)]  
  
 El método de devolución de llamada de la prueba de posicionamiento define las acciones que se realizan cuando se identifica una prueba de posicionamiento en un objeto visual determinado del árbol visual.  Después de realizar las acciones, se devuelve un valor de <xref:System.Windows.Media.HitTestResultBehavior> que determina si debe continuar la enumeración de los demás objetos visuales.  
  
 [!code-csharp[HitTestingOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[HitTestingOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#102)]  
  
> [!NOTE]
>  El orden de enumeración de los objetos visuales de la posición es el [orden z](GTMT).  El objeto visual de [orden z](GTMT) de nivel superior es el primer objeto enumerado.  Los demás objetos visuales enumerados están en [orden z](GTMT) decreciente.  Este orden de enumeración corresponde al orden de representación de elementos visuales.  
  
 Puede detener la enumeración de objetos visuales en cualquier momento de la función de devolución de llamada de la prueba de posicionamiento devolviendo <xref:System.Windows.Media.HitTestResultBehavior>.  
  
 [!code-csharp[HitTestingOverview#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#103)]
 [!code-vb[HitTestingOverview#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#103)]  
  
<a name="using_a_hit_test_filter_callback"></a>   
## Utilizar una devolución de llamada de filtro de prueba de posicionamiento  
 Puede utilizar un filtro opcional de la prueba de posicionamiento para restringir los objetos que se pasan en los resultados de pruebas de posicionamiento.  Esto permite omitir, en los resultados de pruebas de posicionamiento, las partes del árbol visual que no se desee procesar.  Para implementar un filtro de prueba de posicionamiento, defina una función de devolución de llamada de filtro de prueba de posicionamiento y páselo como un valor de parámetro al llamar al método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  
  
 [!code-csharp[HitTestingOverview#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#104)]
 [!code-vb[HitTestingOverview#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#104)]  
  
 Si no desea proporcionar la función opcional de devolución de llamada de filtro de prueba de posicionamiento, pase un valor `null` como parámetro para el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  
  
 [!code-csharp[HitTestingOverview#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#105)]
 [!code-vb[HitTestingOverview#105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#105)]  
  
 ![Restringir un árbol visual usando un filtro de prueba de posicionamiento](../../../../docs/framework/wpf/graphics-multimedia/media/filteredvisualtree-01.png "FilteredVisualTree\_01")  
Eliminar objetos de un árbol visual  
  
 La función de devolución de llamada de filtro de prueba de posicionamiento permite enumerar todos los objetos visuales cuyo contenido representado contenga las coordenadas que especifique.  No obstante, es posible que desee omitir determinadas bifurcaciones del árbol visual, porque no le interese procesarlas en la función de devolución de llamada de los resultados de pruebas de posicionamiento.  El valor devuelto de la función de devolución de llamada del filtro de la prueba de posicionamiento determina el tipo de acción que deben realizar los objetos visuales.  Por ejemplo, si devuelve el valor <xref:System.Windows.Media.HitTestFilterBehavior>, podrá quitar el objeto visual actual y sus derivados de la enumeración de los resultados de pruebas de posicionamiento.  Esto significa que la función de devolución de llamada de los resultados de pruebas de posicionamiento no verá estos objetos en su enumeración.  Cuando se elimina objetos del árbol visual, se reduce el número de procesos durante el paso de enumeración de resultados de pruebas de posicionamiento.  En el ejemplo de código siguiente, el filtro omite las etiquetas y sus descendientes y realiza pruebas de posicionamiento con todos los demás objetos.  
  
 [!code-csharp[HitTestingOverview#106](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#106)]
 [!code-vb[HitTestingOverview#106](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#106)]  
  
> [!NOTE]
>  Se llamará a la devolución de llamada de filtro de la prueba de posicionamiento en aquellos casos en los que no se llame a la devolución de llamada de resultados de pruebas de posicionamiento.  
  
<a name="overriding_default_hit_testing"></a>   
## Invalidar la prueba de posicionamiento predeterminada  
 Puede invalidar la compatibilidad con la prueba de posicionamiento predeterminada de un objeto visual invalidando el método <xref:System.Windows.Media.Visual.HitTestCore%2A>.  Esto significa que, al invocar el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>, se llamaría a la implementación de invalidación de <xref:System.Windows.Media.Visual.HitTestCore%2A>.  Se llama al método de invalidación cuando una prueba de posicionamiento está dentro del rectángulo delimitador del objeto visual, aunque las coordenadas estén fuera del contenido representado de dicho objeto.  
  
 [!code-csharp[HitTestingOverview#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#107)]
 [!code-vb[HitTestingOverview#107](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#107)]  
  
 Quizá haya ocasiones en las que desee realizar la prueba de posicionamiento tanto respecto al rectángulo delimitador como respecto al contenido representado de un objeto visual.  Utilizando el valor del parámetro `PointHitTestParameters` valor del método <xref:System.Windows.Media.Visual.HitTestCore%2A> de reemplazo como parámetro para <xref:System.Windows.Media.Visual.HitTestCore%2A> del método base, puede realizar acciones basadas en un posicionamiento en el rectángulo delimitador de un objeto visual y, a continuación, realizar una segunda prueba de posicionamiento respecto al contenido representado del objeto visual.  
  
 [!code-csharp[HitTestingOverview#108](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#108)]
 [!code-vb[HitTestingOverview#108](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#108)]  
  
## Vea también  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>   
 <xref:System.Windows.Media.HitTestResult>   
 <xref:System.Windows.Media.HitTestResultCallback>   
 <xref:System.Windows.Media.HitTestFilterCallback>   
 <xref:System.Windows.UIElement.IsHitTestVisible%2A>   
 [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994)   
 [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995)   
 [Geometría de una prueba de posicionamiento en un objeto Visual](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)   
 [Realizar pruebas de posicionamiento mediante un contenedor host Win32](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-a-win32-host-container.md)