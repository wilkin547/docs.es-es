---
title: "Defining Custom Types for Use with .NET Framework XAML Services | Microsoft Docs"
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
  - "defining custom types [XAML Services]"
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
caps.latest.revision: 11
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 11
---
# Defining Custom Types for Use with .NET Framework XAML Services
Al definir tipos personalizados que son objetos de negocios o tipos que no tienen una dependencia en marcos concretos, hay ciertos procedimientos recomendados para XAML que puede seguir.  Si sigue estos procedimientos, los Servicios XAML de .NET Framework y los lectores y sistemas de escritura de XAML pueden detectar las características de XAML de su tipo y darle la representación apropiada en un flujo de nodo XAML utilizando el sistema de tipos XAML.  En este tema se describen los procedimientos recomendados para las definiciones de tipo, definiciones de miembros y atribuciones de tipos o miembros de CLR.  
  
## Modelos de constructor y definiciones de tipos para XAML  
 Para que se cree una instancia de una clase personalizada como elemento de objeto en XAML, dicha clase debe cumplir los requisitos siguientes:  
  
-   La clase personalizada debe ser pública y exponer un constructor público predeterminado \(sin parámetros\).  \(Vea en la siguiente sección las notas relativas a las estructuras\).  
  
-   La clase personalizada no debe ser una clase anidada.  El "punto" adicional en la ruta de acceso del nombre completo hace que la división del espacio de nombres de clase sea ambigua e interfiera con otras características de XAML, como las propiedades adjuntas.  
  
 Si se pueden crear instancias de un objeto como un elemento de objeto, el objeto creado puede rellenar el formulario de elemento de cualquier propiedad que tome el objeto como su tipo subyacente.  
  
 Todavía puede proporcionar los valores de objeto para los tipos que no cumplen estos criterios si habilita un convertidor de valores.  Para obtener más información, vea [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
### Estructuras  
 Las estructuras siempre pueden construirse en XAML, mediante la definición de CLR.  Esto se debe a que un compilador de CLR crea implícitamente un constructor predeterminado para una estructura.  Este constructor inicializa todos los valores de propiedad con sus valores predeterminados.  
  
 En algunos casos, el comportamiento predeterminado de construcción no es deseable para una estructura.  Esto podría deberse a que la estructura se ha diseñado para rellenar los valores y funciona conceptualmente como una unión.  Al ser una unión, los valores contenidos podrían tener interpretaciones mutuamente excluyentes y, en consecuencia, no se podría establecer ninguna de sus propiedades.  Un ejemplo de este tipo de estructura en el vocabulario de WPF es <xref:System.Windows.GridLength>.  Estas estructuras deberían implementar un convertidor de tipos, de forma que los valores se puedan expresar en forma de atributo usando las convenciones de cadena que crean las diferentes interpretaciones o modos de los valores de la estructura.  La estructura también debería exponer un comportamiento similar por la construcción del código a través de un constructor no predeterminado.  
  
### Interfaces  
 Las interfaces se pueden utilizar como tipos subyacentes de miembros.  El sistema de tipos XAML comprueba la lista asignable y espera que el objeto que se proporciona como valor se pueda asignar a la interfaz.  No hay ningún concepto acerca de cómo se debe presentar la interfaz como un tipo XAML siempre y cuando el tipo asignable pertinente admita los requisitos de construcción de XAML.  
  
### Métodos de generador  
 Los métodos de generador son una característica de XAML 2009.  Modifican el principio de XAML según el cual los objetos deben tener constructores predeterminados.  Los métodos de generador no se documentan en este tema.  Vea [x:FactoryMethod Directive](../../../docs/framework/xaml-services/x-factorymethod-directive.md).  
  
## Enumeraciones  
 Las enumeraciones tienen el comportamiento de conversión de tipos nativa de XAML.  Los nombres constantes de enumeración especificados en XAML se resuelven a partir del tipo de enumeración subyacente y devuelven el valor de enumeración a un sistema de escritura de objetos XAML.  
  
 XAML admite el uso del estilo de marcas para las enumeraciones con el atributo <xref:System.FlagsAttribute> aplicado.  Para obtener más información, vea [Detalles de la sintaxis XAML](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  \([Detalles de la sintaxis XAML](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md) se ha escrito para la audiencia de WPF, pero la mayor parte de la información de ese tema es pertinente para el XAML que no es específico de un marco de implementación determinado\).  
  
## Definiciones de miembros  
 Los tipos pueden definir los miembros para el uso de XAML.  Es posible que los tipos definan miembros utilizables por XAML aunque ese tipo específico no lo sea.  Esto es posible debido a la herencia de CLR.  XAML puede usar un miembro siempre y cuando herede el miembro que admite el uso de XAML como tipo, y el miembro admita el uso de XAML para su tipo subyacente o tenga disponible una sintaxis XAML nativa.  
  
### Propiedades  
 Si define las propiedades como propiedades públicas de CLR mediante los modelos de descriptor de acceso `get` y `set` típicos de CLR y las palabras clave apropiadas para el lenguaje, el sistema de tipos XAML puede notificar la propiedad como un miembro con la información adecuada proporcionada para las propiedades de <xref:System.Xaml.XamlMember>, como <xref:System.Xaml.XamlMember.IsReadPublic%2A> y <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Las propiedades concretas pueden habilitar una sintaxis de texto aplicando <xref:System.ComponentModel.TypeConverterAttribute>.  Para obtener más información, vea [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 En ausencia de una sintaxis de texto o de la conversión de XAML nativa y en ausencia de un direccionamiento indirecto más extenso como un uso de la extensión de marcado, el tipo de una propiedad \(<xref:System.Xaml.XamlMember.TargetType%2A> en el sistema de tipos XAML\) debe poder devolver una instancia a un sistema de escritura de objetos XAML tratando el tipo de destino como un tipo CLR.  
  
 Si está utilizando XAML 2009, se puede utilizar [x:Reference Markup Extension](../../../docs/framework/xaml-services/x-reference-markup-extension.md) para proporcionar los valores cuando no se cumplen las consideraciones anteriores. Sin embargo, esto es más un problema de uso que un problema de definición de tipos.  
  
### Eventos  
 Si define los eventos como un evento CLR público, el sistema de tipos XAML puede notificar el evento como un miembro con <xref:System.Xaml.XamlMember.IsEvent%2A> como `true`.  La conexión de los controladores de eventos está fuera del ámbito de las capacidades de los Servicios XAML de .NET Framework; esto queda para los marcos e implementaciones concretos.  
  
### Métodos  
 El código alineado para los métodos no es una capacidad predeterminada de XAML.  En la mayoría de los casos, no se hace referencia directamente a los miembros de método desde XAML, y el rol de métodos de XAML solamente sirve para proporcionar compatibilidad con modelos de XAML concretos.  [x:FactoryMethod Directive](../../../docs/framework/xaml-services/x-factorymethod-directive.md) es una excepción.  
  
### Campos  
 Las instrucciones de diseño de CLR desaconsejan los campos no estáticos.  Para los campos estáticos, solo se puede tener acceso a los valores de campos estáticos a través de [x:Static Markup Extension](../../../docs/framework/xaml-services/x-static-markup-extension.md); en este caso, no se realiza ninguna acción especial en la definición de CLR para exponer un campo para los usos de [x:Static](../../../docs/framework/xaml-services/x-static-markup-extension.md).  
  
## Miembros adjuntables  
 Los miembros adjuntables se exponen a XAML a través de un modelo de método de descriptor de acceso en un tipo de definición.  El propio tipo de definición no necesita ser utilizable por XAML como un objeto.  De hecho, un modelo común consiste en declarar una clase de servicio cuyo rol es poseer el miembro adjuntable e implementar los comportamientos relacionados, sin ninguna otra función \(por ejemplo, una representación de interfaz de usuario\).  Para las siguientes secciones, el marcador de posición*PropertyName* representa el nombre del miembro adjuntable.  Ese nombre debe ser válido en la [Gramática de XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 Tenga precaución con los conflictos de nombres entre estos modelos y otros métodos de un tipo.  Si existe un miembro que coincide con uno de los modelos, un procesador XAML puede interpretarlo como una ruta de uso de miembro adjuntable aunque no fuera esa su intención.  
  
#### El descriptor de acceso GetPropertyName  
 La firma del descriptor de acceso `Get`*nombreDePropiedad* debe ser:  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
-   El objeto `target` se puede especificar como un tipo más específico en la implementación.  Puede usar esto para establecer el ámbito del uso del miembro adjuntable; los usos fuera del ámbito deseado producirán excepciones de conversión de tipos no válida, que se exponen a través de un error de análisis de XAML.  El `target` del nombre de parámetro no es un requisito, pero se denomina `target` por convención en la mayoría de las implementaciones.  
  
-   El valor devuelto se puede especificar como un tipo más específico en la implementación.  
  
 Para admitir la sintaxis de texto habilitada por <xref:System.ComponentModel.TypeConverter> para el uso de atributo del miembro adjuntable, aplique <xref:System.ComponentModel.TypeConverterAttribute> al descriptor de acceso `Get`*nombreDePropiedad*.  Aplicarlo a `get` en lugar de `set`, puede no parecer intuitivo; sin embargo, esta convención puede admitir el concepto de miembros adjuntables de solo lectura que son serializables, lo que resulta útil en los escenarios de diseñador.  
  
#### El descriptor de acceso SetPropertyName  
 La firma para el descriptor de acceso Set*PropertyName* debe ser:  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   El objeto `target` se puede especificar como un tipo más específico en la implementación, con la misma lógica y consecuencias tal y como se describe en la sección anterior.  
  
-   El objeto `value` se puede especificar como un tipo más específico en la implementación.  
  
 Recuerde que el valor para este método es la entrada que proviene del uso de XAML, normalmente en forma de atributo.  En la forma de atributo debe existir compatibilidad del convertidor de valores con una sintaxis de texto y con el atributo en el descriptor de acceso `Get`*nombreDePropiedad*.  
  
### Almacenes de miembros adjuntables  
 Los métodos de descriptor de acceso no suelen ser suficientes como medio para colocar los valores de los miembros adjuntables en un gráfico de objeto o para recuperar los valores del gráfico de objetos y serializarlos correctamente.  Para proporcionar esta funcionalidad, los objetos `target` de las firmas de descriptores de acceso anteriores deben poder almacenar valores.  El mecanismo de almacenamiento debe ser coherente con el principio de miembro adjuntable, que indica que el miembro se puede asociar a los destinos en cuyas listas de miembros no aparezca.  Los Servicios XAML de .NET Framework proporcionan una técnica de implementación para almacenes de miembros adjuntables a través de las API <xref:System.Xaml.IAttachedPropertyStore> y <xref:System.Xaml.AttachablePropertyServices>.  Los sistemas de escritura XAML usan <xref:System.Xaml.IAttachedPropertyStore> para detectar la implementación del almacén y se debe implementar en el tipo que es `target` para los descriptores de acceso.  Las API del <xref:System.Xaml.AttachablePropertyServices> estático se utilizan dentro del cuerpo de los descriptores de acceso y hacen referencia al miembro adjuntable por su <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## Atributos de CLR relacionados con XAML  
 Es importante atribuir los tipos, miembros y ensamblados correctamente para notificar la información del sistema de tipos de XAML a los Servicios XAML de .NET Framework.  Esto es pertinente si piensa usar sus tipos con sistemas XAML basados directamente en los lectores y sistemas de escritura de XAML de los Servicios XAML de .NET Framework, o si define o usa un marco que utiliza XAML y está basado en esos lectores y sistemas de escritura de XAML.  
  
 Para consultar una lista de cada atributo relacionado con XAML que es pertinente para la compatibilidad de XAML con sus tipos personalizados, vea [XAML\-Related CLR Attributes for Custom Types and Libraries](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## Uso  
 El uso de tipos personalizados requiere que el autor del marcado asigne un prefijo para el ensamblado y el espacio de nombres CLR que contienen el tipo personalizado.  Este procedimiento no está documentado en este tema.  
  
## Nivel de acceso  
 XAML proporciona un medio para cargar y crear instancias de tipos que tienen un nivel de acceso `internal`.  Esta funcionalidad se proporciona para que el código de usuario pueda definir sus propios tipos y, a continuación, crear instancias de esas clases desde marcado que también es parte del mismo ámbito de código de usuario.  
  
 Un ejemplo extraído de WPF es cuando el código de usuario define un control <xref:System.Windows.Controls.UserControl> diseñado como medio para refactorizar un comportamiento de la interfaz de usuario, pero no como parte de un posible mecanismo de extensión que pudiera estar implícito mediante la declaración de la clase auxiliar con nivel de acceso `public`.  Este tipo de <xref:System.Windows.Controls.UserControl> se puede declarar con acceso `internal` si el código de respaldo se compila en el mismo ensamblado desde el que se hace referencia como tipo XAML.  
  
 Para una aplicación que carga XAML en plena confianza y usa <xref:System.Xaml.XamlObjectWriter>, siempre se permite cargar las clases con el nivel de acceso `internal`.  
  
 Para una aplicación que carga XAML con confianza parcial, puede controlar características de nivel de acceso mediante la API <xref:System.Xaml.Permissions.XamlAccessLevel>.  Además, los mecanismos de aplazamiento \(como el sistema de plantilla de WPF\) deben poder propagar cualquier permiso de nivel de acceso y mantenerlo para las posibles evaluaciones en tiempo de ejecución; esto se controla internamente al pasar la información de <xref:System.Xaml.Permissions.XamlAccessLevel>.  
  
### Implementación de WPF  
 XAML de WPF utiliza un modelo de acceso de confianza parcial según el cual si BAML se carga con confianza parcial, el acceso se limita a <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> para el ensamblado que es el origen BAML.  Para el aplazamiento, WPF utiliza <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=fullName> como un mecanismo para pasar información de nivel de acceso.  
  
 En la terminología XAML de WPF, un *tipo interno*  es un tipo definido por el mismo ensamblado que también incluye el XAML que hace referencia.  Dicho tipo puede asignarse a un espacio de nombres XAML que omita deliberadamente la parte assembly\= de una asignación; por ejemplo, `xmlns:local="clr-namespace:WPFApplication1"`.  Si BAML hace referencia a un tipo interno y ese tipo tiene el nivel de acceso `internal`, se genera una clase `GeneratedInternalTypeHelper` para el ensamblado.  Si desea evitar `GeneratedInternalTypeHelper`, debe utilizar el nivel de acceso `public` o factorizar la clase pertinente en un ensamblado independiente y convertirlo en dependiente.  
  
## Vea también  
 [XAML\-Related CLR Attributes for Custom Types and Libraries](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)   
 [XAML Services](../../../docs/framework/xaml-services/index.md)