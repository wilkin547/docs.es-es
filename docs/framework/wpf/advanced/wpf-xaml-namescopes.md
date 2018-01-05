---
title: "Ámbitos de nombres XAML de WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namescopes [WPF]
- styles [WPF], namescopes in
- templates [WPF], namescopes in
- APIs [WPF], name-related
- name-related APIs
- XAML [WPF], namescopes
- classes [WPF], FrameworkContentElement
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4caaa9453cb3cec76a8606afb5601919eba607a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-xaml-namescopes"></a>Ámbitos de nombres XAML de WPF
Los ámbitos de nombres XAML son un concepto que identifica objetos que se definen en XAML. Los nombres de un ámbito de nombres XAML se pueden usar para establecer relaciones entre los nombres de objetos definidos por XAML y sus equivalentes de instancia en un árbol de objetos. Normalmente, los ámbitos de nombres XAML del código administrado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se crean al cargar las distintas raíces de página XAML de una aplicación XAML. Ámbitos de nombres XAML como objetos de programación se definen mediante la <xref:System.Windows.Markup.INameScope> de interfaz y también se implementan mediante la clase práctica <xref:System.Windows.NameScope>.  
  
  
  
<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## <a name="namescopes-in-loaded-xaml-applications"></a>Ámbitos de nombres en las aplicaciones XAML cargadas  
 En un contexto de programación o de informática más amplio, los conceptos de programación suelen incluir el principio de un identificador o nombre único que se puede usar para obtener acceso a un objeto. Para los sistemas que usan identificadores o nombres, el ámbito de nombres define los límites en los que buscará un proceso o técnica si se solicita un objeto con ese nombre, o bien los límites en los que se aplica la unicidad de la identificación de nombres. En los ámbitos de nombres XAML se aplican los siguientes principios generales. En WPF, los ámbitos de nombres XAML se crean en el elemento raíz de una página XAML cuando esta se carga. Todos los nombres especificados dentro de la página XAML a partir de la raíz de la página se agregan a un ámbito de nombres XAML pertinente.  
  
 En XAML de WPF, los elementos que son elementos raíz comunes (como <xref:System.Windows.Controls.Page>, y <xref:System.Windows.Window>) siempre controlan un ámbito de nombres XAML. Si un elemento como <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> es el elemento raíz de la página en el marcado, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador agrega un <xref:System.Windows.Controls.Page> raíz implícitamente para que la <xref:System.Windows.Controls.Page> puede proporcionar un ámbito de nombres XAML de trabajo.  
  
> [!NOTE]
>  Las acciones de compilación de WPF crean un ámbito de nombres XAML para la producción de XAML, aunque no haya ningún atributo `Name` o `x:Name` definido en ningún elemento del marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Si intenta usar el mismo nombre dos veces en cualquier ámbito de nombres XAML, se producirá una excepción. Para el XAML de WPF que tiene código subyacente y forma parte de una aplicación compilada, la excepción se produce en tiempo de compilación mediante acciones de compilación de WPF, al crear la clase generada para la página durante la compilación inicial del marcado. Para el XAML que no está compilado por el marcado mediante ninguna acción de compilación, las excepciones relacionadas con algún error de ámbito de nombres XAML podrían producirse al cargar el XAML. Los diseñadores de XAML también pueden prever los errores de ámbito de nombres XAML en tiempo de diseño.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Agregar objetos a los árboles de objetos en tiempo de ejecución  
 El momento en que se analiza el XAML representa el momento en el que se crea y se define un ámbito de nombres XAML de WPF. Si agrega un objeto a un árbol de objetos después de haber analizado el XAML que generó el árbol, los valores `Name` o `x:Name` del objeto nuevo no actualizarán automáticamente la información de un ámbito de nombres XAML. Para agregar un nombre de un objeto en un ámbito de nombres XAML de WPF después de carga XAML, debe llamar a la implementación adecuada de <xref:System.Windows.Markup.INameScope.RegisterName%2A> en el objeto que define el ámbito de nombres XAML, que suele ser la raíz de la página XAML. Si el nombre no está registrado, el objeto agregado no puede hacer referencia por su nombre a través de métodos como <xref:System.Windows.FrameworkElement.FindName%2A>, y no se puede utilizar ese nombre para destinos de animación.  
  
 El escenario más común para los desarrolladores de aplicaciones es la que va a usar <xref:System.Windows.FrameworkElement.RegisterName%2A> para registrar los nombres en el ámbito de nombres XAML en la raíz de la página actual. <xref:System.Windows.FrameworkElement.RegisterName%2A>forma parte de un escenario importante para guiones gráficos que objetos de destino para las animaciones. Para obtener más información, consulte [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Si se llama a <xref:System.Windows.FrameworkElement.RegisterName%2A> en un objeto que no sea el objeto que define el ámbito de nombres XAML, el nombre se siguen registrado en el ámbito de nombres XAML que se mantiene el objeto que realiza la llamada dentro de, como si se hubiera llamado <xref:System.Windows.FrameworkElement.RegisterName%2A> en el ámbito de nombres XAML que define el objeto.  
  
### <a name="xaml-namescopes-in-code"></a>Ámbitos de nombres XAML en el código  
 Puede crear y usar ámbitos de nombres XAML en el código. Las API y los conceptos implicados en la creación de ámbitos de nombres XAML son los mismos, incluso para un uso de código puro, ya que el procesador XAML de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa estas API y estos conceptos cuando procesa el XAML. Los conceptos y las API existen principalmente para poder buscar objetos por nombre dentro de un árbol de objetos que se suele definir parcial o completamente en XAML.  
  
 Para las aplicaciones que se crean mediante programación y no desde XAML cargado, el objeto que define un ámbito de nombres XAML debe implementar <xref:System.Windows.Markup.INameScope>, o ser un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> clase derivada, para admitir la creación de un ámbito de nombres XAML en su instancias.  
  
 Además, para cualquier elemento que no se haya cargado y procesado con un procesador XAML, el ámbito de nombres XAML del objeto no se crea ni se inicializa de forma predeterminada. Debe crear explícitamente un ámbito de nombres XAML para cualquier objeto en el que después vaya a registrar nombres. Para crear un ámbito de nombres XAML, se llama el método estático <xref:System.Windows.NameScope.SetNameScope%2A> método. Especificar el objeto que será el propietario como el `dependencyObject` parámetro y un nuevo <xref:System.Windows.NameScope.%23ctor%2A> llamada de constructor como el `value` parámetro.  
  
 Si el objeto proporcionado como `dependencyObject` para <xref:System.Windows.NameScope.SetNameScope%2A> no es un <xref:System.Windows.Markup.INameScope> implementación, <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, al llamar a <xref:System.Windows.FrameworkElement.RegisterName%2A> en todos los elementos no tiene ningún efecto. Si no puede crear el nuevo ámbito de nombres XAML explícitamente, a continuación, llama a <xref:System.Windows.FrameworkElement.RegisterName%2A> , se producirá una excepción.  
  
 Para ver un ejemplo de cómo usar las API de ámbito de nombres XAML en el código, consulte [Definir un ámbito de nombres](../../../../docs/framework/wpf/graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## <a name="xaml-namescopes-in-styles-and-templates"></a>Ámbitos de nombres XAML en estilos y plantillas  
 Los estilos y las plantillas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrecen la posibilidad de reutilizar y volver a aplicar el contenido de una manera sencilla, aunque también pueden incluir elementos con nombres XAML definidos en el nivel de la plantilla. Esa misma plantilla se puede usar varias veces en una página. Por este motivo, tanto los estilos como las plantillas definen sus propios ámbitos de nombres XAML, independientemente de la ubicación en un árbol de objetos en la que se aplique el estilo o plantilla.  
  
 Considere el ejemplo siguiente:  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 En este caso, se aplica la misma plantilla a dos botones diferentes. Si las plantillas no tuvieran ámbitos de nombres XAML discretos, el nombre `TheBorder` usado en la plantilla provocaría un conflicto de nombres en el ámbito de nombres XAML. Todas las instancias de la plantilla tienen su propio ámbito de nombres XAML, por lo que, en este ejemplo, el ámbito de nombres XAML de todas las plantillas de instancia contendrían exactamente un nombre.  
  
 Los estilos también definen su propio ámbito de nombres XAML, sobre todo para que las partes de los guiones gráficos puedan tener asignados nombres concretos. Estos nombres permiten que haya comportamientos específicos de controles destinados a elementos con ese nombre, incluso si la plantilla se ha vuelto a definir como parte de la personalización de controles.  
  
 Debido a los ámbitos de nombres XAML independientes, resulta más difícil buscar elementos con nombre en una plantilla que buscar un elemento con nombre y sin plantilla en una página. Primero debe determinar la plantilla aplicada, obteniendo el <xref:System.Windows.Controls.Control.Template%2A> valor de la propiedad del control donde se aplica la plantilla. A continuación, se llama a la versión de la plantilla de <xref:System.Windows.FrameworkTemplate.FindName%2A>, pasando el control donde se aplicó la plantilla como segundo parámetro.  
  
 Si es el autor de un control y genera una convención donde un determinado elemento de una plantilla aplicada cuyo nombre sea el destino para un comportamiento definido por el propio control, puede usar el <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> método desde el código de implementación del control. El <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> método está protegido, por lo que solo el autor del control tiene acceso a él.  
  
 Si está trabajando desde dentro de una plantilla y la necesidad de obtener el ámbito de nombres XAML donde se aplica la plantilla, obtener el valor de <xref:System.Windows.FrameworkElement.TemplatedParent%2A>y, a continuación, llame a <xref:System.Windows.FrameworkElement.FindName%2A> no existe. Un ejemplo de trabajo dentro de la plantilla sería escribir la implementación del controlador de eventos donde se generará el evento desde un elemento de una plantilla aplicada.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## <a name="xaml-namescopes-and-name-related-apis"></a>Ámbitos de nombres XAML y API relacionadas con nombres  
 <xref:System.Windows.FrameworkElement>tiene <xref:System.Windows.FrameworkElement.FindName%2A>, <xref:System.Windows.FrameworkElement.RegisterName%2A> y <xref:System.Windows.FrameworkElement.UnregisterName%2A> métodos. Si el objeto en el que llama a estos métodos tiene un ámbito de nombres XAML, los métodos llaman a los métodos del ámbito de nombres XAML relevante. De lo contrario, se comprueba el elemento primario para ver si tiene un ámbito de nombres XAML. Este proceso continúa de forma recursiva hasta que se encuentra un ámbito de nombres XAML (debido al comportamiento del procesador XAML, se garantiza que haya un ámbito de nombres XAML en la raíz). <xref:System.Windows.FrameworkContentElement>tiene comportamientos análogos, con la excepción de que ningún <xref:System.Windows.FrameworkContentElement> nunca será el propietario de un ámbito de nombres XAML. Los métodos existen en <xref:System.Windows.FrameworkContentElement> para que se pueden reenviar las llamadas futuro a un <xref:System.Windows.FrameworkElement> elemento primario.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>se utiliza para asignar un nuevo ámbito de nombres XAML a un objeto existente. Puede llamar a <xref:System.Windows.NameScope.SetNameScope%2A> más de una vez con el fin de restablecer o borrar el XAML ámbito de nombres, pero que no es un uso común. Además, <xref:System.Windows.NameScope.GetNameScope%2A> no se utiliza normalmente desde el código.  
  
### <a name="xaml-namescope-implementations"></a>Implementaciones de ámbito de nombres XAML  
 Las clases siguientes implementan <xref:System.Windows.Markup.INameScope> directamente:  
  
-   <xref:System.Windows.NameScope>  
  
-   <xref:System.Windows.Style>  
  
-   <xref:System.Windows.ResourceDictionary>  
  
-   <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>No utilice nombres de XAML o ámbitos de nombres; las claves usa en su lugar, porque es una implementación de diccionario. La única razón <xref:System.Windows.ResourceDictionary> implementa <xref:System.Windows.Markup.INameScope> es, por lo que puede producir excepciones al código de usuario que le ayudan a aclarar la distinción entre un ámbito de nombres XAML true y cómo un <xref:System.Windows.ResourceDictionary> controla teclas y también para garantizar que los ámbitos de nombres XAML no se aplican a un <xref:System.Windows.ResourceDictionary> por los elementos primarios.  
  
 <xref:System.Windows.FrameworkTemplate>y <xref:System.Windows.Style> implementar <xref:System.Windows.Markup.INameScope> a través de definiciones de interfaz explícita. Las implementaciones explícitas permiten que estos ámbitos de nombres XAML se comporten convencional cuando se tiene acceso a través de la <xref:System.Windows.Markup.INameScope> interfaz, que indica cómo se comunican los ámbitos de nombres XAML por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] procesos internos. Pero las definiciones de interfaz explícitas no forman parte de la superficie de API convencional de <xref:System.Windows.FrameworkTemplate> y <xref:System.Windows.Style>, ya que rara vez es necesario llamar a la <xref:System.Windows.Markup.INameScope> métodos en <xref:System.Windows.FrameworkTemplate> y <xref:System.Windows.Style> directamente y en su lugar, utilizaría otra API como <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>.  
  
 Las clases siguientes definen su propio ámbito de nombres XAML, mediante el uso de la <xref:System.Windows.NameScope?displayProperty=nameWithType> clase auxiliar y conectarse a su implementación de ámbito de nombres XAML a través de la <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> propiedad asociada:  
  
-   <xref:System.Windows.FrameworkElement>  
  
-   <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>Vea también  
 [Espacios de nombres y asignación de espacios de nombres XAML para WPF](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)  
 [x:Name (Directiva)](../../../../docs/framework/xaml-services/x-name-directive.md)
