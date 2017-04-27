---
title: "Herencia de valores de propiedad | Microsoft Docs"
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
  - "herencia, valores de propiedades"
  - "propiedades, herencia de valores"
  - "herencia de valores"
ms.assetid: d7c338f9-f2bf-48ed-832c-7be58ac390e4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Herencia de valores de propiedad
La herencia de valores de propiedad es una característica del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  La herencia de valores de propiedad permite que los elementos secundarios de un árbol de elementos obtengan el valor de una propiedad concreta de sus elementos primarios, y lo hereden tal y como esté establecido en cualquier punto del elemento primario más próximo.  El elemento primario también podría haber obtenido su valor a través de la herencia de valores de propiedad, del tal forma que el sistema se repite potencialmente hasta la raíz de la página.  La herencia de valores de propiedad no es el comportamiento predeterminado del sistema de propiedades; una propiedad se debe establecer con un valor de metadatos concreto para que ésta inicie la herencia de valores de propiedad en los elementos secundarios.  
  
   
  
<a name="Property_Value_Inheritance_is_Containment_Inheritance"></a>   
## La herencia de valores de propiedad es la herencia de contención  
 El término "herencia" utilizado aquí no representa exactamente el mismo concepto que la herencia en el contexto de los tipos y de la programación orientada a objetos en general, donde las clases derivadas heredan las definiciones de miembros de sus clases base.  Ese significado de herencia también está activo en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: las propiedades definidas en diversas clases base se exponen como atributos para las clases [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] derivadas cuando se utilizan como elementos y se exponen como miembros para el código.  La herencia de valores de propiedad se refiere, en particular, al modo en que valores de las propiedades se pueden heredar de un elemento a otro basándose en las relaciones entre elementos primarios y secundarios dentro de un árbol de elementos.  Ese árbol de elementos queda visible directamente cuando se anidan los elementos dentro de otros elementos al definir aplicaciones en marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Los árboles de objetos también se pueden crear mediante programación agregando objetos a colecciones designadas de otros objetos, en cuyo caso la herencia de valores de propiedad funcionará de igual forma en el árbol terminado en tiempo de ejecución.  
  
<a name="Practical_Applications_of_Property_Value_Inheritance"></a>   
## Aplicaciones prácticas de la herencia de valores de propiedad  
 Las [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluyen varias propiedades que tienen habilitada la herencia de valores de propiedad.  El escenario típico para ellas es aquél en que es apropiado que una propiedad se establezca una sola vez por página, pero donde esa propiedad también es un miembro de una de las clases de elementos base y, en consecuencia, también existirá en la mayoría de los elementos secundarios.  Por ejemplo, la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> controla en qué dirección se debe presentar y organizar en la página el contenido dinámico.  Normalmente, es conveniente administrar el concepto de flujo de texto de manera coherente en todos los elementos secundarios.  Si la dirección de flujo se restablece por cualquier motivo en algún nivel del árbol de elementos, por acción del usuario o del entorno, lo normal es que haya que restablecerla en todo él.  Cuando la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> se establece para heredar, únicamente es preciso establecer o restablecer el valor una vez en el nivel del árbol de elementos que abarca las necesidades de presentación de cada página de la aplicación.  Incluso el valor predeterminado inicial heredará de esta manera.  A pesar de ello, el modelo de herencia de valores de propiedad permite restablecer el valor en elementos individuales para los pocos casos en que se desea expresamente mezclar las direcciones de flujo.  
  
<a name="Making_a_Custom_Property_Inheritable"></a>   
## Hacer heredable una propiedad personalizada  
 Cambiando los metadatos de una propiedad personalizada, puede hacer que también sus propias propiedades personalizadas sean heredables.  No obstante, tenga en cuenta que hay algunas consideraciones de rendimiento al designar una propiedad como heredable.  En los casos en que esa propiedad no tiene un valor local establecido, o un valor obtenido a través de estilos, plantillas o enlaces de datos, una propiedad heredable proporciona sus valores de propiedad asignados a todos los elementos secundarios del árbol lógico.  
  
 Para que una propiedad participe en la herencia de valores, cree una propiedad asociada personalizada, como se describe en [Registrar una propiedad asociada](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md).  Registre la propiedad con metadatos \(<xref:System.Windows.FrameworkPropertyMetadata>\) y especifique la opción "Inherits" en la configuración de opciones de los metadatos.  Asegúrese también de que la propiedad tenga un valor predeterminado establecido, porque ahora ese valor heredará.  Aunque registró la propiedad como asociada, también puede ser conveniente crear un "contenedor" de propiedad para el acceso set\/get para el tipo de propietario, como lo haría para una [propiedad de dependencia](GTMT) no asociada.  A continuación, la propiedad heredable se puede establecer mediante el contenedor de propiedad directo del tipo de propietario o de los tipos derivados, o bien mediante la sintaxis de propiedades asociadas de cualquier <xref:System.Windows.DependencyObject>.  
  
 Las propiedades asociadas son conceptualmente similares a las propiedades globales; puede comprobar para el valor en cualquier <xref:System.Windows.DependencyObject> y obtener un resultado válido.  El escenario típico para las propiedades asociadas consiste en establecer los valores de propiedad en elementos secundarios. Este escenario es más efectivo si se trata de una propiedad asociada que siempre está presente implícitamente como tal en cada elemento \(<xref:System.Windows.DependencyObject>\) del árbol.  
  
> [!NOTE]
>  Aunque puede que parezca que la herencia de valores de propiedad funciona para las propiedades de dependencia no asociadas, no se ha definido el comportamiento de la herencia de una propiedad no asociada a través de algunos límites de elementos del árbol en tiempo de ejecución.  Utilice siempre <xref:System.Windows.DependencyProperty.RegisterAttached%2A> para registrar las propiedades en las que especifique <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> en los metadatos.  
  
<a name="InheritanceContext"></a>   
## Heredar valores de propiedad a través de los límites del árbol  
 La herencia de propiedades funciona atravesando un árbol de elementos.  Este árbol suele ser paralelo al árbol lógico.  Sin embargo, cada vez que se incluye un objeto de [nivel básico de WPF](GTMT) en el marcado que define un árbol de elementos, como un <xref:System.Windows.Media.Brush>, se crea un árbol lógico discontinuo.  Un verdadero árbol lógico no se extiende conceptualmente a través de <xref:System.Windows.Media.Brush>, porque el árbol lógico es un concepto de [nivel de marco de trabajo de WPF](GTMT).  Puede observar esta situación reflejada en los resultados cuando utilice los métodos de <xref:System.Windows.LogicalTreeHelper>.  Sin embargo, la herencia de valores de propiedad puede cerrar esta brecha del árbol lógico y pasar a través de ella los valores heredados, siempre que la propiedad heredable se haya registrado como propiedad asociada y no se encuentre ningún límite de bloqueo deliberado de la herencia \(como un control <xref:System.Windows.Controls.Frame>\).  
  
## Vea también  
 [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)   
 [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)