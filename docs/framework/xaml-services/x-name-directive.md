---
title: "x:Name Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:Name"
  - "xName"
  - "Name"
helpviewer_keywords: 
  - "x:Name attribute [XAML Services]"
  - "XAML [XAML Services], x:Name attribute"
  - "Name attribute in XAML [XAML Services]"
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 27
---
# x:Name Directive
Identifica de manera única elementos definidos por XAML en un ámbito de nombres XAML.  Los ámbitos de nombres XAML y sus modelos de unicidad se pueden aplicar a los objetos con instancias, cuando los marcos de trabajo proporcionan las API o implementan comportamientos de acceso al gráfico de objetos creado por XAML en tiempo de ejecución.  
  
## Uso de atributos XAML  
  
```  
<object x:Name="XAMLNameValue".../>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`XAMLNameValue`|Cadena que cumple a las restricciones de [Gramática de XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
  
## Comentarios  
 Después de aplicar `x:Name` al modelo de programación de respaldo de un marco, el nombre es equivalente a la variable que contiene una referencia de objeto o una instancia devuelta por un constructor.  
  
 El valor de uso de una directiva `x:Name` debe ser único dentro de un ámbito de nombres de XAML.  De forma predeterminada, cuando lo usa la API de servicios XAML de .NET Framework, el ámbito de nombres XAML primario se define en el elemento raíz XAML de una producción XAML única y abarca los elementos incluidos en la producción XAML.  Los marcos pueden definir los ámbitos de nombres XAML discretos adicionales que pueden ocurrir dentro de una única producción XAML para resolver escenarios concretos.  Por ejemplo, en WPF, los ámbitos de nombres XAML nuevos están definidos y creados por una plantilla también definida en la producción XAML.  Para obtener más información acerca de los ámbitos de nombres XAML \(escritos para WPF pero pertinente para muchos conceptos del ámbito de nombres XAML\), vea [Ámbitos de nombres XAML de WPF](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 En general, `x:Name` no se debería aplicar en situaciones que también usan `x:Key`.  Implementaciones XAML concretas mediante los marcos de trabajo existentes han introducido conceptos de substitución entre `x:Key` y `x:Name`, pero no es una práctica recomendada.  Los servicios XAML de .NET Framework no son compatibles con estos conceptos de sustitución al administrar información de nombre\/clave como <xref:System.Windows.Markup.INameScope> o <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 Los marcos de aplicación específicos se definen en las reglas para permitir `x:Name`, así como en el cumplimiento de la singularidad del nombre.  Sin embargo, para que se puedan usar con los servicios XAML de .NET Framework, las definiciones del marco de trabajo de la exclusividad del ámbito de nombres XAML deben ser coherentes con la definición de la información de <xref:System.Windows.Markup.INameScope> de esta documentación, y deben utilizar las mismas reglas con respecto a dónde se aplica la información.  Por ejemplo, la implementación [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] divide los distintos elementos de marcado en intervalos <xref:System.Windows.NameScope> independientes, tales como diccionarios de recursos, el árbol lógico creado por el XAML de nivel de página, las plantillas y otro contenido diferido y, a continuación, exige la exclusividad de un nombre XAML dentro de cada uno de esos ámbitos de nombres XAML.  
  
 Para los tipos personalizados que usan los sistemas de escritura de objetos XAML de los servicios XAML de .NET Framework, se puede establecer o cambiar una propiedad que asigna a `x:Name` en un tipo.  Defina este comportamiento haciendo referencia al nombre de la propiedad que se debe asignar con <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> en el código de la definición de tipo.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> es un atributo en el nivel de tipos.  
  
 Al utilizar los servicios XAML de .NET Services, la lógica de respaldo para la compatibilidad del ámbito de nombres XAML se puede definir en un marco neutro mediante la implementación de la interfaz <xref:System.Windows.Markup.INameScope>.  
  
## Notas de uso de WPF  
 Bajo la configuración de compilación estándar correspondiente a una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que utiliza XAML, clases parciales y código subyacente, el `x:Name` especificado pasa a ser el nombre de un campo que se crea en el código subyacente al procesar el [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] mediante una tarea de compilación de marcado; este campo contiene una referencia al objeto. De manera predeterminada, el campo creado es interno.  Puede cambiar el acceso al campo especificando el [atributo x:FieldModifier](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md).  En WPF y Silverlight, la secuencia consiste en que la compilación del marcado define y nombra el campo en una clase parcial, pero el valor está inicialmente vacío.  A continuación, se llama a un método generado denominado `InitializeComponent` desde el constructor de clase.  `InitializeComponent` se compone de llamadas a `FindName` en las que se usan cada uno de los valores `x:Name` que existen en la parte definida por XAML de la clase parcial como cadenas de entrada.  A continuación, los valores devueltos se asignan a la referencia de campo con el mismo nombre para rellenar los valores de campo con objetos creados a partir del análisis de XAML.  La ejecución de `InitializeComponent` permite hacer referencia al gráfico de objetos en tiempo de ejecución usando el nombre del campo `x:Name` \/ directamente, en lugar de tener que llamar a `FindName` de forma explícita cada vez que se requiera una referencia a un objeto definido en XAML.  
  
 Para una aplicación WPF que usa destinos de [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] e incluye archivos XAML con una acción de compilación `Page`, se crea una propiedad de referencia independiente durante la compilación que agrega la palabra clave `WithEvents` a todos los elementos que tienen un atributo `x:Name`, a fin de admitir la sintaxis de `Handles` para los delegados de controladores de eventos.  Esta propiedad siempre es pública.  Para obtener más información, consulte [Control de eventos en Visual Basic y WPF](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 Un procesador XAML de WPF usa `x:Name` para registrar un nombre en un ámbito de nombres XAML durante la carga, incluso en aquellos casos en que las acciones de compilación no compilan por marcado la página \(por ejemplo, XAML separado de un diccionario de recursos\).  Una de las causas de este comportamiento se debe a que `x:Name` se necesita potencialmente para el enlace de <xref:System.Windows.Data.Binding.ElementName%2A>.  Para obtener información detallada, vea [Información general sobre el enlace de datos](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Tal y como se mencionó anteriormente, `x:Name` \(o `Name`\) no se deberían aplicar en situaciones que también utilizan `x:Key`.  El objeto [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> presenta un comportamiento especial que consiste en definirse a sí mismo como un ámbito de nombres XAML, pero devuelve Sin implementar o valores NULL para las API <xref:System.Windows.Markup.INameScope> como una manera de imponer este comportamiento.  Si el analizador XAML de WPF encuentra `Name` o `x:Name` en un elemento <xref:System.Windows.ResourceDictionary> definido por XAML, el nombre no se agrega a ningún ámbito de nombres XAML.  Al intentar encontrar ese nombre desde cualquier ámbito de nombres XAML y los métodos `FindName` no se devolverán resultados válidos.  
  
### x:Name y Name  
 Muchos escenarios de aplicación de WPF pueden evitar cualquier uso del atributo `x:Name`, porque la propiedad de dependencia `Name`, como se especifica dentro del espacio de nombres XAML predeterminado para varias de las clases base importantes como <xref:System.Windows.FrameworkElement> y <xref:System.Windows.FrameworkContentElement>, cumple este mismo propósito.  Todavía existen algunos escenarios de XAML y WPF comunes donde es importante tener acceso mediante código a un elemento que no tiene una propiedad `Name` en el nivel de marco.  Por ejemplo, algunas clases de compatibilidad de animaciones y guiones gráficos no admiten una propiedad `Name`, pero con frecuencia debe hacerse referencia a estas en el código para controlar la animación.  Debe especificar `x:Name` como atributo en las escalas de tiempo y transformaciones que se crean en XAML, si piensa hacer referencia a ellas desde el código más adelante.  
  
 Si <xref:System.Windows.FrameworkElement.Name%2A> está disponible como una propiedad de la clase, <xref:System.Windows.FrameworkElement.Name%2A> y `x:Name` se pueden usar de forma intercambiable como atributos, pero se producirá una excepción de análisis si ambas se especifican en el mismo elemento.  Si XAML es compilado de marcado, la excepción se producirá en la compilación de marcado, de lo contrario se produce en la carga.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> se puede establecer mediante la sintaxis de atributo XAML y también mediante código usando <xref:System.Windows.DependencyObject.SetValue%2A>; no obstante, tenga en cuenta que, en la mayoría de las circunstancias, al establecer la propiedad <xref:System.Windows.FrameworkElement.Name%2A> en código no se crea la referencia de campo representativa dentro del ámbito de nombres XAML, donde XAML ya se ha cargado.  En lugar de intentar establecer <xref:System.Windows.FrameworkElement.Name%2A> mediante código, utilice los métodos <xref:System.Windows.NameScope> del código, con respecto al ámbito de nombres correspondiente.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> también se puede establecer mediante la sintaxis de elementos de propiedad con texto interno, pero eso es raro.  En cambio, `x:Name` no se puede establecer en la sintaxis de elemento de propiedad de XAML, ni mediante código utilizando <xref:System.Windows.DependencyObject.SetValue%2A> ; solo se puede establecer utilizando la sintaxis de atributo en objetos porque es una directiva.  
  
## Notas de uso de Silverlight  
 `x:Name` para Silverlight se documenta por separado.  Para obtener más información, vea [Características de lenguaje \(x:\) de espacios de nombres XAML \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## Vea también  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=fullName>   
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=fullName>   
 [Árboles en WPF](../../../docs/framework/wpf/advanced/trees-in-wpf.md)