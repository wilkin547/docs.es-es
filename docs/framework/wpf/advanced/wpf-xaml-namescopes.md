---
title: "&#193;mbitos de nombres XAML de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "API, relacionadas con nombres"
  - "clases, FrameworkContentElement"
  - "clases, FrameworkElement"
  - "clases, RegisterName"
  - "FrameworkContentElement (clase)"
  - "FrameworkElement (clase)"
  - "API relacionadas con nombres"
  - "ámbitos de nombres"
  - "RegisterName (clase)"
  - "estilos, ámbitos de nombres en"
  - "plantillas, ámbitos de nombres en"
  - "XAML, ámbitos de nombres"
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# &#193;mbitos de nombres XAML de WPF
Los ámbitos de nombres XAML son un concepto que identifica los objetos definidos en XAML.  Los nombres de un ámbito de nombres XAML se pueden utilizar para establecer relaciones entre los nombres de objetos definidos por XAML y sus equivalentes de instancia en un árbol de objetos.  Normalmente, los ámbitos de nombres XAML en código administrado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se crean al cargar los elementos raíz de la página XAML individual de una aplicación XAML.  La interfaz <xref:System.Windows.Markup.INameScope> define los ámbitos de nombres XAML como objetos de programación. También los implementa la clase práctica <xref:System.Windows.NameScope>.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## Ámbitos de nombres en aplicaciones de XAML cargado  
 En un contexto de programación o informático más amplio, los conceptos de programación suelen incluir el principio de un identificador o nombre único que se puede utilizar para tener acceso a un objeto.  Para los sistemas que utilizan identificadores o nombres, el ámbito de nombres define los límites dentro de los cuales un proceso o técnica buscará si se solicita un objeto con ese nombre, o los límites donde se aplica la singularidad de identificación de nombres.  Estos principios generales son verdaderos para los ámbitos de nombres XAML.  En WPF, los ámbitos de nombres XAML se crean en el elemento raíz de una página XAML al cargarla.  Cada nombre especificado dentro de la página XAML empezando en la raíz de la página se agrega a un ámbito de nombres XAML pertinente.  
  
 En XAML de WPF, los elementos que son elementos raíz comunes \(como <xref:System.Windows.Controls.Page> y <xref:System.Windows.Window>\) siempre controlan un ámbito de nombres XAML.  Si un elemento, como <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, es el elemento raíz de la página en el marcado, un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] agrega implícitamente una raíz de <xref:System.Windows.Controls.Page> para que <xref:System.Windows.Controls.Page> pueda proporcionar un ámbito de nombres XAML de trabajo.  
  
> [!NOTE]
>  Las acciones de compilación de WPF crean un ámbito de nombres XAML para una producción XAML incluso si no se definen atributos `Name` o `x:Name` en algún elemento del marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Si intenta utilizar dos veces el mismo nombre en un ámbito de nombres XAML, se inicia una excepción.  Para el XAML de WPF que tiene código subyacente y forma parte de una aplicación compilada, la excepción la inician las acciones de compilación de WPF en tiempo de compilación, al crear la clase generada para la página durante la compilación inicial del marcado.  Para el XAML que no se compila por marcado mediante ninguna acción de compilación, las excepciones relacionadas con los problemas del ámbito de nombres XAML se podrían iniciar cuando se cargue el XAML.  Los diseñadores XAML también podrían prever los problemas del ámbito de nombres XAML en tiempo de diseño.  
  
### Agregar objetos a los árboles de objetos en tiempo de ejecución  
 El momento en que se analiza el XAML representa el momento en el tiempo en que se crea y define un ámbito de nombres XAML de WPF.  Si agrega un objeto a un árbol de objetos en un punto en el tiempo posterior al análisis del XAML que generó ese árbol, un valor `Name` o `x:Name` en el nuevo objeto no actualiza automáticamente la información en un ámbito de nombres XAML.  Para agregar un nombre de un objeto en un ámbito de nombres XAML de WPF después de cargar el XAML, debe llamar a la implementación adecuada de <xref:System.Windows.Markup.INameScope.RegisterName%2A> en el objeto que define el ámbito de nombres XAML, que normalmente es la raíz de la página XAML.  Si el nombre no está registrado, no se puede hacer referencia al objeto agregado por su nombre mediante métodos como <xref:System.Windows.FrameworkElement.FindName%2A> y no se puede utilizar ese nombre para destinos de animación.  
  
 El escenario más común para los programadores de aplicaciones consiste en utilizar <xref:System.Windows.FrameworkElement.RegisterName%2A> para registrar los nombres en el ámbito de nombres XAML en la raíz actual.  <xref:System.Windows.FrameworkElement.RegisterName%2A> forma parte de un importante escenario para guiones gráficos destinados a objetos para animaciones.  Para obtener más información, vea [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Si llama a <xref:System.Windows.FrameworkElement.RegisterName%2A> en un objeto distinto al objeto que define el ámbito de nombres XAML, el nombre aún se registrará en el ámbito de nombres XAML en el que se encuentra el objeto que realiza la llamada, como si se hubiera llamado a <xref:System.Windows.FrameworkElement.RegisterName%2A> en el ámbito de nombres XAML que define el objeto.  
  
### Ámbitos de nombres XAML en código  
 Puede crear y, a continuación, utilizar ámbitos de nombres XAML en código.  Las API y los conceptos relacionados con la creación del ámbito de nombres XAML son los mismos incluso para el uso en código puro, porque el procesador XAML de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza estas API y conceptos al procesar el propio XAML.  Los conceptos y las API existen principalmente para permitir buscar los objetos por su nombre dentro de un árbol de objetos que se suele definir total o parcialmente en XAML.  
  
 Para las aplicaciones que se crean mediante programación y no a partir de XAML cargado, el objeto que define un ámbito de nombres XAML debe implementar <xref:System.Windows.Markup.INameScope>, o ser una clase derivada de <xref:System.Windows.FrameworkElement> o de <xref:System.Windows.FrameworkContentElement>, para admitir la creación de un ámbito de nombres XAML en sus instancias.  
  
 Además, para cualquier elemento que no se cargue y procese mediante un procesador de XAML, el ámbito de nombres XAML del objeto no se crea ni inicializa de manera predeterminada.  Debe crear de manera explícita un nuevo ámbito de nombres XAML para cualquier objeto en el que vaya a registrar nombres seguidamente.  Para crear un ámbito de nombres XAML, se llama al método <xref:System.Windows.NameScope.SetNameScope%2A> estático.  Especifique el objeto que lo poseerá como el parámetro `dependencyObject` y una nueva llamada al constructor <xref:System.Windows.NameScope.%23ctor%2A> como el parámetro `value`.  
  
 Si el objeto proporcionado como parámetro `dependencyObject` para el método <xref:System.Windows.NameScope.SetNameScope%2A> no es una implementación de <xref:System.Windows.Markup.INameScope>, <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, llamar a <xref:System.Windows.FrameworkElement.RegisterName%2A> en cualquier elemento secundario no surtirá ningún efecto.  Si no crea explícitamente el nuevo ámbito de nombres XAML, al llamar a <xref:System.Windows.FrameworkElement.RegisterName%2A> se iniciará una excepción.  
  
 Para obtener un ejemplo del uso de las API de ámbito de nombres XAML en código, vea [Definir un ámbito de nombres](../../../../docs/framework/wpf/graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## Ámbitos de nombres XAML en estilos y plantillas  
 Los estilos y plantillas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporcionan la capacidad de reutilizar y aplicar de nuevo el contenido de una manera sencilla.  Sin embargo, los estilos y las plantillas también pueden incluir elementos con nombres XAML definidos en el nivel de plantilla.  Esta misma plantilla se puede utilizar varias veces en una página.  Por esta razón, los estilos y las plantillas definen sus propios ámbitos de nombres XAML, independientemente de la ubicación en un árbol de objetos donde se aplique el estilo o la plantilla.  
  
 Considere el ejemplo siguiente:  
  
 [!code-xml[XamlOvwSupport#NameScopeTemplates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Aquí, se aplica la misma plantilla a dos botones diferentes.  Si las plantillas no tuvieran ámbitos de nombres XAML discretos, el nombre `TheBorder` utilizado en la plantilla provocaría un conflicto de nombres en el ámbito de nombres XAML.  Cada instancia que se crea de la plantilla tiene su propio ámbito de nombres XAML, por lo que en este ejemplo el ámbito de nombres XAML de cada instancia de la plantilla contendrá exactamente un nombre.  
  
 Los estilos también definen su propio ámbito de nombres XAML, principalmente para permitir la asignación de nombres concretos a los distintos componentes del guión.  Estos nombres habilitan comportamientos concretos destinados a elementos de ese nombre, aunque se vuelva a definir la plantilla como parte de la personalización de un control.  
  
 A causa de los ámbitos de nombres XAML independientes, buscar elementos con nombre en una plantilla resulta más complicado que hacerlo en un elemento con nombre sin plantilla de una página.  En primer lugar, debe determinar cuál es la plantilla aplicada, obteniendo el valor de propiedad <xref:System.Windows.Controls.Control.Template%2A> del control donde se aplica la plantilla.  A continuación, se llama a la versión de plantilla de <xref:System.Windows.FrameworkTemplate.FindName%2A>, y se pasa el control donde se aplicó la plantilla como segundo parámetro.  
  
 Si usted es el autor de un control y genera una convención donde un elemento con nombre determinado de una plantilla aplicada es el destino para un comportamiento definido por el propio control, puede utilizar el método <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> del código de implementación del control.  El método <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> se protege, de tal forma que únicamente su autor tiene acceso a él.  
  
 Si trabaja desde dentro de una plantilla y necesita obtener el espacio de nombres XAML donde se aplica la plantilla, obtenga el valor de <xref:System.Windows.FrameworkElement.TemplatedParent%2A> y, a continuación, llame a <xref:System.Windows.FrameworkElement.FindName%2A> desde allí.  Un ejemplo de trabajo dentro de la plantilla sería escribir la implementación del controlador de eventos donde el evento se provocará desde un elemento de una plantilla aplicada.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## Ámbitos de nombres XAML y API relacionadas con nombres  
 <xref:System.Windows.FrameworkElement> tiene los métodos <xref:System.Windows.FrameworkElement.FindName%2A>, <xref:System.Windows.FrameworkElement.RegisterName%2A> y <xref:System.Windows.FrameworkElement.UnregisterName%2A>.  Si el objeto para el que se llama a estos métodos posee un ámbito de nombres XAML, los métodos llaman a los métodos del ámbito de nombres XAML pertinente.  De lo contrario, se comprueba el elemento primario por si posee un ámbito de nombres XAML, y este proceso continúa de forma recursiva hasta que se encuentra un ámbito de nombres XAML \(debido al comportamiento del procesador de XAML, es seguro que hay un ámbito de nombres XAML en la raíz\).  <xref:System.Windows.FrameworkContentElement> tiene comportamientos análogos, con la excepción de que ningún <xref:System.Windows.FrameworkContentElement> poseerá jamás un ámbito de nombres de XAML.  Los métodos existen en <xref:System.Windows.FrameworkContentElement> para que las llamadas se puedan reenviar, en caso necesario, a un elemento primario <xref:System.Windows.FrameworkElement>.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A> se utiliza para asignar un nuevo ámbito de nombres XAML a un objeto existente.  Puede llamar más de una vez a <xref:System.Windows.NameScope.SetNameScope%2A> a fin de restablecer o borrar el ámbito de nombres XAML, pero no suele hacerse.  <xref:System.Windows.NameScope.GetNameScope%2A> tampoco se suele utilizar mediante código.  
  
### Implementaciones de ámbitos de nombres XAML  
 Las clases siguientes implementan <xref:System.Windows.Markup.INameScope> directamente:  
  
-   <xref:System.Windows.NameScope>  
  
-   <xref:System.Windows.Style>  
  
-   <xref:System.Windows.ResourceDictionary>  
  
-   <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary> no utiliza nombres ni ámbitos de nombres XAML, sino claves, porque es una implementación de diccionario.  La única razón por la que <xref:System.Windows.ResourceDictionary> implementa <xref:System.Windows.Markup.INameScope> es para poder iniciar excepciones en el código de usuario que ayuden a aclarar la distinción entre un ámbito de nombres XAML verdadero y la manera de administrar las claves por parte de <xref:System.Windows.ResourceDictionary>, además de asegurarse de que ningún elemento primario aplique ámbitos de nombres XAML a <xref:System.Windows.ResourceDictionary>.  
  
 <xref:System.Windows.FrameworkTemplate> y <xref:System.Windows.Style> implementan <xref:System.Windows.Markup.INameScope> mediante definiciones de interfaz explícitas.  Las implementaciones explícitas permiten que estos ámbitos de nombres XAML se comporten de un modo convencional cuando se tiene acceso a ellos a través de la interfaz <xref:System.Windows.Markup.INameScope>, que es el modo que los procesos internos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizan para comunicar los ámbitos de nombres XAML.  No obstante, las definiciones de interfaz explícitas no forman parte de la superficie de API convencional de <xref:System.Windows.FrameworkTemplate> y <xref:System.Windows.Style>, porque casi nunca se necesita llamar directamente a los métodos <xref:System.Windows.Markup.INameScope> en <xref:System.Windows.FrameworkTemplate> y <xref:System.Windows.Style> y, en su lugar, se utilizaría otra API, como <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>.  
  
 Las clases siguientes definen su propio ámbito de nombres XAML, utilizando la clase de aplicación auxiliar <xref:System.Windows.NameScope?displayProperty=fullName> y conectándose a su implementación de ámbito de nombres XAML a través de la propiedad adjunta <xref:System.Windows.NameScope.NameScope%2A?displayProperty=fullName>:  
  
-   <xref:System.Windows.FrameworkElement>  
  
-   <xref:System.Windows.FrameworkContentElement>  
  
## Vea también  
 [Espacios de nombres y asignación de espacios de nombres XAML para WPF](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)   
 [x:Name \(Directiva\)](../../../../docs/framework/xaml-services/x-name-directive.md)