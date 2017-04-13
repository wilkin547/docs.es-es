---
title: "Recursos y c&#243;digo | Microsoft Docs"
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
  - "claves, utilizar objetos como"
  - "código de procedimientos, acceso a los recursos desde"
  - "código de procedimientos, crear recursos mediante"
  - "recursos, acceso desde código de procedimientos"
  - "recursos, crear con código de procedimientos"
ms.assetid: c1cfcddb-e39c-41c8-a7f3-60984914dfae
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Recursos y c&#243;digo
Esta información general se concentra en cómo se puede obtener acceso a los recursos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] o cómo crearlos mediante código en lugar de mediante la sintaxis [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Para obtener más información sobre el uso de recursos en general y sobre los recursos desde la perspectiva de la sintaxis [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="accessing"></a>   
## Acceso a los recursos mediante código  
 Las claves que identifican los recursos si se definen mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] también se utilizan para recuperar recursos concretos cuando se solicita el recurso en el código.  La manera más simple de recuperar un recurso desde el código es llamar al método <xref:System.Windows.FrameworkElement.FindResource%2A> o <xref:System.Windows.FrameworkElement.TryFindResource%2A> desde los objetos de nivel de marco de trabajo de la aplicación.  La diferencia de comportamiento entre estos métodos reside en lo que ocurre si no se encuentra la clave solicitada.  <xref:System.Windows.FrameworkElement.FindResource%2A> produce una excepción; <xref:System.Windows.FrameworkElement.TryFindResource%2A> no producirá una excepción pero devolverá `null`.  Cada método toma la clave de recurso como parámetro de entrada y devuelve un objeto con establecimiento flexible de tipos.  Normalmente, una clave de recurso es una cadena, pero ocasionalmente se utilizan otros tipos de datos; consulte la sección [Utilizar objetos como claves](#objectaskey) para obtener detalles al respecto.  Lo habitual es convertir el objeto devuelto al tipo requerido por la propiedad que se está estableciendo al solicitar el recurso.  La lógica de búsqueda para la resolución del recurso de código es igual que en el caso de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de referencia de recurso dinámico.  La búsqueda de recursos comienza desde el elemento que realiza la llamada, y continúa a los elementos primarios sucesivos del [árbol lógico](GTMT).  La búsqueda continúa avanzando por los recursos de la aplicación, los temas y los recursos del sistema si es necesario.  Una solicitud mediante código de un recurso tendrá en cuenta correctamente los cambios en tiempo de ejecución que puedan hacerse en los diccionarios de recursos después de cargarlos desde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], así como los cambios que se hagan en los recursos del sistema en tiempo real.  
  
 A continuación, se muestra un breve ejemplo de código que busca un recurso por su clave y utiliza el valor devuelto para establecer una propiedad, que se implementa como controlador del evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Un método alternativo para asignar una referencia de recurso es <xref:System.Windows.FrameworkElement.SetResourceReference%2A>.  Este método toma dos parámetros: la clave del recurso y el identificador correspondiente a una propiedad de dependencia determinada que está presente en la instancia de elemento a la que debería estar asignado el valor de recurso.  Funcionalmente, este método es igual, y tiene la ventaja de no requerir ninguna conversión de los valores devueltos.  
  
 Otra manera más de tener acceso a los recursos mediante programación es obtener acceso al contenido de la propiedad <xref:System.Windows.FrameworkElement.Resources%2A> como diccionario.  Tener acceso al diccionario contenido por esta propiedad también constituye la manera de agregar nuevos recursos a las colecciones existentes, comprobar si la colección ya ha aceptado un nombre de clave determinado y realizar otras operaciones de diccionario o colección.  Si está escribiendo una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante código en su totalidad, también puede crear la colección completa en código, asignarle claves y, a continuación, asignar la colección acabada a la propiedad <xref:System.Windows.FrameworkElement.Resources%2A> de un elemento establecido.  Esto se describe en la sección siguiente.  
  
 Puede indizar dentro de cualquier colección <xref:System.Windows.FrameworkElement.Resources%2A> determinada utilizando una clave concreta como índice, pero debe tener en cuenta que al tener acceso al recurso de esta manera no se siguen las reglas de tiempo de ejecución normales para la resolución de recursos.  Únicamente se tiene acceso a esa colección en particular.  La búsqueda de recursos no recorrerá el ámbito hasta la raíz ni la aplicación si no se encuentra ningún objeto válido en la clave solicitada.  Sin embargo, este enfoque puede presentar ventajas de rendimiento en algunos casos precisamente por esta restricción del ámbito de búsqueda de la clave.  Consulte la clase <xref:System.Windows.ResourceDictionary> para obtener más detalles sobre cómo trabajar directamente con el diccionario de recursos.  
  
<a name="creating"></a>   
## Crear recursos mediante código  
 Si desea crear una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] completa mediante código, quizás también desee crear los recursos de esa aplicación mediante código.  Para ello, cree una nueva instancia de <xref:System.Windows.ResourceDictionary> y, a continuación, agregue todos los recursos al diccionario mediante llamadas sucesivas a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName>.  Después, utilice el objeto <xref:System.Windows.ResourceDictionary> así creado para establecer la propiedad <xref:System.Windows.FrameworkElement.Resources%2A> en un elemento que esté presente en el ámbito de una página, o la propiedad <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>.  También puede mantener <xref:System.Windows.ResourceDictionary> como objeto independiente sin agregarlo a un elemento.  Sin embargo, si lo hace, deberá tener acceso a los recursos contenidos en él por su clave de elemento, como si se tratase de un diccionario genérico.  Si un <xref:System.Windows.ResourceDictionary> no está asociado a la propiedad `Resources` de un elemento o existirá como parte del árbol del elemento y no tendrá ningún ámbito en la secuencia de búsqueda utilizada por <xref:System.Windows.FrameworkElement.FindResource%2A> y otros métodos relacionados.  
  
<a name="objectaskey"></a>   
## Utilizar objetos como claves  
 La mayoría de los usos de recursos establecen la clave de recurso en una cadena.  Sin embargo, en varias características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] deliberadamente no se utiliza un tipo de cadena para especificar las claves, sino un objeto.  La capacidad de que la clave de un recurso sea un objeto se utiliza en la compatibilidad de estilos y temas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Las claves de los estilos de los temas que se convierten en el estilo predeterminado de un control que, salvo éste, no tiene ningún otro estilo, se determinan mediante el objeto <xref:System.Type> del control al que se deben aplicar.  El hecho de que la clave sea un tipo proporciona un mecanismo de búsqueda confiable que funciona en las instancias predeterminadas de cada tipo de control. Además, el tipo se puede detectar por reflexión y utilizar para las clases de estilos derivadas aunque, por lo demás, el tipo derivado no tenga ningún estilo predeterminado.  Puede especificar una clave <xref:System.Type> para un recurso definido en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizando [x:Type \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-type-markup-extension.md).  Existen extensiones similares para otros usos de clave que no son de cadena y que admiten las características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como [Extensión de marcado ComponentResourceKey](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).  
  
## Vea también  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)