---
title: "XAML-Related CLR Attributes for Custom Types and Libraries | Microsoft Docs"
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
  - "CLR attributes for custom types [XAML Services]"
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# XAML-Related CLR Attributes for Custom Types and Libraries
En este tema se describen los atributos de Common Language Runtime \(CLR\) definidos por los Servicios XAML de .NET Framework.  También se describen otros atributos de CLR definidos en .NET Framework que tienen un escenario relacionado con XAML para la aplicación a ensamblados o tipos.  La asignación de atributos a ensamblados, tipos o miembros con estos atributos de CLR proporciona información de sistema de tipos XAML relacionada con los tipos.  La información se proporciona a cualquier consumidor de XAML que utilice los servicios XAML de .NET Framework para procesar el flujo de nodo XAML directamente o a través de los lectores y escritores de XAML dedicados.  
  
## Atributos de CLR relacionados con XAML para los tipos y miembros personalizados  
 El uso de los atributos de CLR implica que está utilizando el CLR general para definir sus tipos; de lo contrario, tales atributos no estarían disponibles.  Si usa CLR para definir el respaldo de tipos, el contexto de esquema XAML predeterminado utilizado por los escritores de XAML de los Servicios XAML de .NET Framework puede leer la atribución de CLR a través de la reflexión contra el respaldo de los ensamblados.  
  
 En las siguientes secciones se describen los atributos relacionados con XAML que puede aplicar a los tipos o miembros personalizados.  Cada atributo de CLR comunica la información que es pertinente a un sistema de tipos XAML.  En la ruta de acceso de carga, la información con atributos ayuda al lector de XAML a formar un flujo de nodo XAML válido o ayuda al escritor de XAML a producir un gráfico de objetos válido.  En la ruta de acceso para guardar, la información con atributos ayuda al lector de XAML a formar un flujo de nodo XAML válido que reconstituye la información del sistema de tipos XAML; o declara sugerencias de serialización o requisitos para el escritor de XAML u otros consumidores de XAML.  
  
### AmbientAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **Se aplica a:** clase, propiedad o miembros de descriptor de acceso `get` que admiten propiedades adjuntables.  
  
 **Argumentos:** ninguno.  
  
 <xref:System.Windows.Markup.AmbientAttribute> indica que la propiedad, o todas las propiedades que toman el tipo con atributos, se deben interpretar bajo el concepto de propiedad de ambiente en XAML.  El concepto ambiente está relacionado con la forma en que los procesadores XAML determinan los propietarios de tipos de los miembros.  Una propiedad de ambiente es una propiedad donde se espera que el valor esté disponible en el contexto del analizador al crear un gráfico de objetos, pero donde la búsqueda típica de miembro de tipo se suspende para el conjunto de nodos XAML inmediato que se está creando.  
  
 El concepto de ambiente se puede aplicar a los miembros adjuntables, que no se representan como propiedades en lo que se refiere a cómo la atribución de CLR define <xref:System.AttributeTargets>.  El uso de la atribución de método solamente se debe aplicar en el caso de un descriptor de acceso `get` que admite el uso adjuntable para XAML.  
  
### ConstructorArgumentAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **Se aplica a:** clase.  
  
 **Argumentos:** una cadena que especifica el nombre de la propiedad que coincide con un argumento de constructor único.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute> especifica que un objeto se puede inicializar utilizando una sintaxis de constructor no predeterminado, y que una propiedad del nombre especificado proporciona información de la construcción.  Esta información sirve principalmente para la serialización XAML.  Para obtener más información, vea <xref:System.Windows.Markup.ConstructorArgumentAttribute>.  
  
### ContentPropertyAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **Se aplica a:** clase.  
  
 **Argumentos:** una cadena que especifica el nombre de un miembro del tipo con atributos.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute> indica que la propiedad denominada por el argumento debe actuar como propiedad de contenido de XAML para ese tipo.  La definición de propiedad de contenido de XAML hereda a todos los tipos derivados que se pueden asignar al tipo de definición.  La definición puede reemplazarse en un tipo derivado concreto aplicando <xref:System.Windows.Markup.ContentPropertyAttribute> en el tipo derivado concreto.  
  
 Para la propiedad que actúa como la propiedad de contenido de XAML, el etiquetado del elemento de propiedad se puede omitir en el uso de XAML.  Normalmente, se designan las propiedades de contenido de XAML que promueven un marcado XAML simplificado para los modelos de contención y contenido.  Dado que solo se puede designar un miembro como propiedad de contenido de XAML, a veces hay que tomar decisiones de diseño sobre cuáles de las diversas propiedades de contenedor de un tipo se deben designar como propiedad de contenido de XAML.  Las otras propiedades de contenedor se deben usar con elementos de propiedad explícitos.  
  
 En el flujo de nodo XAML, las propiedades de contenido de XAML siguen generando nodos `EndMember` y `StartMember`, utilizando el nombre de la propiedad para <xref:System.Xaml.XamlMember>.  Para determinar si un miembro es la propiedad de contenido XAML, examine el valor de <xref:System.Xaml.XamlType> en la posición `StartObject` y obtenga el valor de <xref:System.Xaml.XamlType.ContentProperty%2A>.  
  
### ContentWrapperAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **Se aplica a:** clase, específicamente los tipos de colección.  
  
 **Argumentos:** un objeto <xref:System.Type> que especifica el tipo que se va a usar como tipo contenedor para el contenido externo.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute> especifica uno o varios tipos del tipo de colección asociado que se van a utilizar para encapsular el contenido externo.  El término contenido externo hace referencia a los casos donde las restricciones del sistema de tipos en el tipo de la propiedad de contenido no capturan todos los posibles casos de contenido que admitiría el uso de XAML para el tipo propietario.  Por ejemplo, la compatibilidad de XAML para el contenido de un tipo determinado podría admitir cadenas en un objeto <xref:System.Collections.ObjectModel.Collection%601> genérico fuertemente tipado.  Los contenedores de contenido son útiles para migrar las convenciones de marcado preexistentes en el concepto de XAML de valores asignables para las colecciones, como la migración de los modelos de contenido relacionados con texto.  
  
 Para especificar más de un tipo de contenedor de contenido, aplique el atributo varias veces.  
  
### DependsOnAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **Se aplica a:** propiedad.  
  
 **Argumentos:** una cadena que especifica el nombre de otro miembro del tipo con atributos.  
  
 <xref:System.Windows.Markup.DependsOnAttribute> indica que la propiedad con atributos depende del valor de otra propiedad.  Aplicar este atributo a una definición de propiedad garantiza que las propiedades dependientes se procesan primero en la escritura de objetos XAML.  Los usos de <xref:System.Windows.Markup.DependsOnAttribute> especifican los casos excepcionales de propiedades en los tipos donde se debe seguir un orden concreto de análisis para la creación de objetos válidos.  
  
 Se pueden aplicar varios casos <xref:System.Windows.Markup.DependsOnAttribute> a una definición de propiedad.  
  
### MarkupExtensionReturnTypeAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **Se aplica a:** clase, que se espera que sea un tipo derivado de <xref:System.Windows.Markup.MarkupExtension>.  
  
 **Argumentos:** un objeto <xref:System.Type> que especifica el tipo más preciso que se espera como resultado `ProvideValue` del objeto <xref:System.Windows.Markup.MarkupExtension> con atributos.  
  
 Para obtener más información, vea [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
### NameScopePropertyAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **Se aplica a:** clase.  
  
 **Argumentos:** admite dos formas de atribución:  
  
-   Una cadena que especifica el nombre de una propiedad en el tipo con atributos.  
  
-   Una cadena que especifica el nombre de una propiedad y un objeto <xref:System.Type> para el tipo que define la propiedad con nombre.  Esta forma sirve para especificar un miembro adjuntable como la propiedad de ámbito de nombres XAML.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute> especifica una propiedad que proporciona el valor del ámbito de nombres XAML para la clase con atributos.  Se espera que la propiedad de ámbito de nombres XAML haga referencia a un objeto que implementa <xref:System.Windows.Markup.INameScope> y contiene el ámbito de nombres XAML real, su almacén y su comportamiento.  
  
### RuntimeNamePropertyAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **Se aplica a:** clase.  
  
 **Argumentos:** una cadena que especifica el nombre de la propiedad de nombre en tiempo de ejecución en el tipo con atributos.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> notifica una propiedad del tipo con atributos que se asigna a [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md) de XAML.  La propiedad debe ser del tipo <xref:System.String> y de lectura y escritura.  
  
 La definición hereda a todos los tipos derivados que se pueden asignar al tipo de definición.  Puede reemplazar la definición en un tipo derivado concreto aplicando <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> en el tipo derivado concreto.  
  
### TrimSurroundingWhitespaceAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **Se aplica a:** tipos.  
  
 **Argumentos:** ninguno.  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> se aplica a los tipos específicos que podrían aparecer como elementos secundarios dentro del contenido significativo del espacio en blanco \(contenido almacenado por una colección que tiene un objeto <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>\).  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> es principalmente pertinente en la ruta de acceso para guardar, pero está disponible en el sistema de tipos XAML en la ruta de acceso de carga al examinar <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=fullName>.  Para obtener más información, vea [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### TypeConverterAttribute  
 **Documentación de referencia:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **Se aplica a:** clase, propiedad, método \(el único caso de método válido para XAML es un descriptor de acceso `get` que admite un miembro adjuntable\).  
  
 **Argumentos:** <xref:System.Type> del objeto <xref:System.ComponentModel.TypeConverter>.  
  
 <xref:System.ComponentModel.TypeConverterAttribute> en un contexto de XAML hace referencia a un objeto <xref:System.ComponentModel.TypeConverter> personalizado.  Este objeto <xref:System.ComponentModel.TypeConverter> proporciona el comportamiento de conversión de tipos para los tipos personalizados o los miembros de ese tipo.  
  
 El atributo <xref:System.ComponentModel.TypeConverterAttribute> se aplica al tipo, haciendo referencia a la implementación del convertidor de tipos.  Los convertidores de tipos se pueden definir para XAML en las clases, estructuras o interfaces.  No es necesario proporcionar la conversión de tipos para las enumeraciones; esa conversión está habilitada de forma nativa.  
  
 El convertidor de tipos debe poder convertir una cadena que se usa para los atributos o el texto de inicialización del marcado en el tipo de destino deseado.  Para obtener más información, vea [Clases TypeConverter y XAML](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
 En lugar de aplicarlo a todos los valores de un tipo, un comportamiento de convertidor de tipos para XAML también se puede establecer en una propiedad concreta.  En este caso, se aplica <xref:System.ComponentModel.TypeConverterAttribute> a la definición de la propiedad \(la definición externa, no las definiciones de `get` y `set` concretas\).  
  
 Un comportamiento del convertidor de tipos para el uso por parte de XAML de un miembro adjuntable personalizado puede asignarse aplicando <xref:System.ComponentModel.TypeConverterAttribute> al descriptor de acceso del método `get` que admite el uso de XAML.  
  
 De forma similar a <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> existía en .NET Framework antes de la existencia de XAML y el modelo del convertidor de tipos servía para otros propósitos.  Para hacer referencia a <xref:System.ComponentModel.TypeConverterAttribute> y usarlo, debe calificarlo totalmente o proporcionar una instrucción `using` para <xref:System.ComponentModel>.  También debe incluir el ensamblado del sistema en el proyecto.  
  
### UidPropertyAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **Se aplica a:** clase.  
  
 **Argumentos:** una cadena que hace referencia a la propiedad pertinente por nombre.  
  
 Indica la propiedad CLR de una clase que establece el alias de [x:Uid Directive](../../../docs/framework/xaml-services/x-uid-directive.md).  
  
### UsableDuringInitializationAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **Se aplica a:** clase.  
  
 **Argumentos:** un valor booleano.  Si se utiliza para el propósito previsto del atributo, siempre se debe especificar como `true`.  
  
 Indica si este tipo se compila de forma descendente durante la creación de gráficos de objetos XAML.  Este es un concepto avanzado, que probablemente está estrechamente relacionado con la definición del modelo de programación.  Para obtener más información, vea <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.  
  
### ValueSerializerAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **Se aplica a:** clase, propiedad, método \(el único caso de método válido para XAML es un descriptor de acceso `get` que admite un miembro adjuntable\).  
  
 **Argumentos:** un objeto <xref:System.Type> que especifica la clase de soporte de serializador de valor que se va a usar al serializar todas las propiedades del tipo con atributos o la propiedad con atributos concreta.  
  
 <xref:System.Windows.Markup.ValueSerializer> especifica una clase de serialización de valor que requiere más estado y contexto que un objeto <xref:System.ComponentModel.TypeConverter>.  <xref:System.Windows.Markup.ValueSerializer> se puede asociar a un miembro adjuntable aplicando el atributo <xref:System.Windows.Markup.ValueSerializerAttribute> del método del descriptor de acceso `get` estático para el miembro adjuntable.  La serialización del valor también es aplicable a las enumeraciones, interfaces y estructuras, pero no a los delegados.  
  
### WhitespaceSignificantCollectionAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **Se aplica a:** clase, específicamente los tipos de colección que se espera que hospeden contenido mixto, donde el espacio en blanco alrededor de los elementos de objeto podría ser significativo para la representación de la interfaz de usuario.  
  
 **Argumentos:** ninguno.  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indica que un procesador XAML debe procesar un tipo de colección como si fuera un espacio en blanco significativo, lo que influye en la construcción de los nodos de valor del flujo de nodo XAML dentro de la colección.  Para obtener más información, vea [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### XamlDeferLoadAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **Se aplica a:** clase, propiedad.  
  
 **Argumentos:** admite dos tipos de formas de atribución como cadenas, o tipos como <xref:System.Type>.  Vea <xref:System.Windows.Markup.XamlDeferLoadAttribute>.  
  
 Indica que una clase o propiedad usa la carga aplazada para XAML \(como el comportamiento de una plantilla\) e informa de la clase que habilita el comportamiento de carga aplazada así como el tipo de contenido\/destino.  
  
### XamlSetMarkupExtensionAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **Se aplica a:** clase.  
  
 **Argumentos:** asigna un nombre a la devolución de llamada.  
  
 Indica que una clase puede utilizar una extensión de marcado para proporcionar un valor para una o más de sus propiedades, y hace referencia a un controlador al que un escritor de XAML debe llamar antes de realizarse una operación de establecimiento de la extensión de marcado en cualquier propiedad de la clase.  
  
### XamlSetTypeConverterAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **Se aplica a:** clase.  
  
 **Argumentos:** asigna un nombre a la devolución de llamada.  
  
 Indica que una clase puede utilizar un convertidor de tipos para proporcionar un valor para una o más de sus propiedades, y hace referencia a un controlador al que un escritor de XAML debe llamar antes de realizarse una operación de establecimiento del convertidor de tipos en cualquier propiedad de la clase.  
  
### XmlLangPropertyAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **Se aplica a:** clase.  
  
 **Argumentos:** una cadena que especifica el nombre de la propiedad para establecer el alias para `xml:lang` en el tipo con atributos.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute> notifica una propiedad del tipo con atributos que se asigna a la directiva `lang` de XML.  La propiedad no es necesariamente del tipo <xref:System.String>, pero debe poderse asignar desde una cadena \(esto se podría lograr asociando un convertidor de tipos al tipo de la propiedad o con la propiedad concreta\).  La propiedad debe ser de lectura y escritura.  
  
 El escenario para asignar `xml:lang` es tal que un modelo de objetos en tiempo de ejecución tiene acceso a la información del lenguaje especificada por XML sin procesarla específicamente con XMLDOM.  
  
 La definición hereda a todos los tipos derivados que se pueden asignar al tipo de definición.  Puede reemplazar la definición en un tipo derivado concreto aplicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> a ese tipo, aunque este es un escenario poco común.  
  
## Atributos de CLR relacionados con XAML en el nivel de ensamblado  
 En las siguientes secciones se describen los atributos relacionados con XAML que no se aplican a los tipos ni a las definiciones de miembros, sino que se aplican en su lugar a los ensamblados.  Estos atributos son pertinentes para el objetivo global de definir una biblioteca que contiene los tipos personalizados que se van a usar en XAML.  Algunos de los atributos no tienen por qué influir directamente en el flujo de nodo XAML, sino que se pasan en el flujo de nodo para que lo usen otros consumidores.  Los consumidores de la información incluyen los entornos de diseño o procesos de serialización que necesitan la información de espacio de nombres XAML y la información de prefijo asociada.  Un contexto de esquema XAML \(incluidos los servicios XAML de .NET Framework predeterminados\) también usa esta información.  
  
### XmlnsCompatibleWithAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **Argumentos:**  
  
-   Una cadena que especifica el identificador del espacio de nombres XAML que se va a incluir.  
  
-   Una cadena que especifica el identificador del espacio de nombres XAML que puede incluir el espacio de nombres XAML del argumento anterior.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> especifica que otro espacio de nombres XAML puede incluir un espacio de nombres XAML.  Normalmente, el espacio de nombres XAML incluido se indica en un <xref:System.Windows.Markup.XmlnsDefinitionAttribute> definido previamente.  Esta técnica se puede usar para controlar las versiones de un vocabulario XAML en una biblioteca y para hacerlo compatible con un marcado definido previamente en el vocabulario anterior controlado por versiones.  
  
### XmlnsDefinitionAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **Argumentos:**  
  
-   Una cadena que especifica el identificador del espacio de nombres XAML que se va a definir.  
  
-   Una cadena que denomina un espacio de nombres CLR.  El espacio de nombres CLR debe definir los tipos públicos del ensamblado y al menos uno de los tipos del espacio de nombres CLR debe estar diseñado para el uso de XAML.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> especifica una asignación por ensamblado entre un espacio de nombres XAML y un espacio de nombres CLR que, a continuación, se utiliza para la resolución de tipos mediante un contexto de sistema de escritura de objetos XAML o de esquema XAML.  
  
 Se puede aplicar más de un objeto <xref:System.Windows.Markup.XmlnsDefinitionAttribute> a un ensamblado.  Esto se podría realizar por cualquier combinación de los siguientes motivos:  
  
-   El diseño de la biblioteca contiene varios espacios de nombres CLR para la organización lógica del acceso de API en tiempo de ejecución. Sin embargo, es conveniente que todos los tipos de esos espacios de nombres sean utilizables en el XAML con referencias al mismo espacio de nombres XAML.  En este caso, aplicaría varios atributos <xref:System.Windows.Markup.XmlnsDefinitionAttribute> usando el mismo valor de <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> pero diferentes valores de <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A>.  Esto es especialmente útil si está definiendo las asignaciones para el espacio de nombres XAML cuyo marco o aplicación va a ser el espacio de nombres XAML predeterminado de uso común.  
  
-   El diseño de la biblioteca contiene varios espacios de nombres CLR y el desarrollador desea una separación de los espacios de nombres XAML deliberada entre los usos de tipos en esos espacios de nombres CLR.  
  
-   Define un espacio de nombres CLR en el ensamblado y desea que sea accesible a través de más de un espacio de nombres XAML.  Este escenario se da cuando se admiten varios vocabularios con el mismo código base.  
  
-   Define la compatibilidad con el lenguaje XAML en uno o más espacios de nombres CLR.  Para estos, el valor de <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> debe ser `http://schemas.microsoft.com/winfx/2006/xaml`.  
  
### XmlnsPrefixAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **Argumentos:**  
  
-   Una cadena que especifica el identificador de un espacio de nombres XAML.  
  
-   Una cadena que especifica un prefijo recomendado.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> especifica un prefijo recomendado que se debe usar para un espacio de nombres XAML.  El prefijo es útil al escribir los elementos y atributos en un archivo XAML serializado por <xref:System.Xaml.XamlXmlWriter> de los Servicios XAML de .NET Framework, o cuando una biblioteca que implementa XAML interactúa con un entorno de diseño que tiene características de edición de XAML.  
  
 Se puede aplicar más de un objeto <xref:System.Windows.Markup.XmlnsPrefixAttribute> a un ensamblado.  Esto se podría realizar por cualquier combinación de los siguientes motivos:  
  
-   Su ensamblado define los tipos para más de un espacio de nombres XAML.  En este caso, debe definir valores de prefijo diferentes para cada espacio de nombres XAML.  
  
-   Va a admitir varios vocabularios y utiliza prefijos diferentes para cada vocabulario y el espacio de nombres XAML.  
  
-   Define la compatibilidad con el lenguaje XAML en el ensamblado y tiene un objeto <xref:System.Windows.Markup.XmlnsDefinitionAttribute> para `http://schemas.microsoft.com/winfx/2006/xaml`.  En este caso, normalmente debe promover el prefijo `x`.  
  
> [!NOTE]
>  Los servicios XAML de .NET Framework también definen el atributo <xref:System.Windows.Markup.RootNamespaceAttribute> relacionado con XAML.  Este atributo es un atributo de nivel de ensamblado para la compatibilidad del sistema de proyectos y no es pertinente para los tipos XAML personalizados.  
  
## Vea también  
 <xref:System.Attribute>   
 [Defining Custom Types for Use with .NET Framework XAML Services](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)