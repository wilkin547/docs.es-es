---
title: Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
caps.latest.revision: "11"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7cce479c7c7a5f6c7112f08f1e15f3bc7e4d366
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework
Al definir tipos personalizados que son objetos de negocios o son tipos que no tienen una dependencia en marcos concretos, hay algunas prácticas recomendadas para XAML que puede seguir. Si sigue estas prácticas, los servicios XAML de .NET Framework y sus lectores XAML y escritores de XAML pueden detectar las características XAML de su tipo y darle la representación apropiada en un flujo de nodo XAML con el sistema de tipos XAML. En este tema se describe procedimientos recomendados para las definiciones de tipo, definiciones de miembros y CLR atribución de tipos o miembros.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Patrones de constructor y definiciones de tipos para XAML  
 Para crear una instancia como un elemento de objeto en XAML, una clase personalizada debe cumplir los siguientes requisitos:  
  
-   La clase personalizada debe ser pública y debe exponer un constructor público (sin parámetros) de forma predeterminada. (Vea en la siguiente sección las notas relativas a las estructuras).  
  
-   La clase personalizada no debe ser una clase anidada. El archivo extra "punto" en la ruta de acceso del nombre completo realiza la división de espacio de nombres de clase ambiguo e interfiere con otras características XAML como propiedades adjuntas.  
  
 Si un objeto se puede crear instancias como un elemento de objeto, el objeto creado puede rellenar el formulario de elemento de propiedad de las propiedades que toman el objeto como su tipo subyacente.  
  
 Todavía puede proporcionar valores de objeto para los tipos que no cumplen estos criterios, si habilita un convertidor de valores. Para obtener más información, consulte [convertidores de tipos y extensiones de marcado para XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
### <a name="structures"></a>Estructuras  
 Las estructuras siempre pueden crearse en XAML, por definición de CLR. Esto es porque un compilador CLR crea implícitamente un constructor predeterminado para una estructura. Este constructor inicializa todos los valores de propiedad en sus valores predeterminados.  
  
 En algunos casos, el comportamiento predeterminado de la construcción de una estructura no es deseable. Esto podría deberse a que la estructura está pensada para rellenar los valores y la función conceptualmente como una unión. Como una unión, los valores contenidos podrían tener interpretaciones mutuamente excluyentes y, por lo tanto, ninguna de sus propiedades son configurable. Un ejemplo de este tipo de estructura en el vocabulario de WPF es <xref:System.Windows.GridLength>. Estas estructuras deben implementar un convertidor de tipos para que los valores se pueden expresar en forma de atributo usando las convenciones de cadena que crean las diferentes interpretaciones o modos de los valores de la estructura. La estructura también debería exponer un comportamiento similar por la construcción del código a través de un constructor no predeterminado.  
  
### <a name="interfaces"></a>Interfaces  
 Interfaces pueden usarse como tipos subyacentes de miembros. El sistema de tipos XAML comprueba la lista asignable y espera que el objeto que se proporciona como el valor puede asignarse a la interfaz. No hay ningún concepto de cómo la interfaz debe presentarse como un tipo XAML como un tipo asignable pertinente admita los requisitos de construcción de XAML.  
  
### <a name="factory-methods"></a>Métodos de generador  
 Métodos de generador son una característica de XAML 2009. Modifican el principio XAML que los objetos deben tener constructores predeterminados. Métodos de generador no se documentan en este tema. Vea [x: FactoryMethod (directiva)](../../../docs/framework/xaml-services/x-factorymethod-directive.md).  
  
## <a name="enumerations"></a>Enumeraciones  
 Las enumeraciones tienen el comportamiento de conversión de tipo nativo de XAML. Nombres de constantes de enumeración especificados en XAML se resuelven en el tipo de enumeración subyacente y devuelven el valor de enumeración a un escritor de objetos XAML.  
  
 XAML admite el uso de estilo de marcas para las enumeraciones con <xref:System.FlagsAttribute> aplicado. Para obtener más información, consulte [XAML Syntax In Detail](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md). ([XAML Syntax In Detail](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md) se ha diseñado para la audiencia WPF, pero la mayor parte de la información de ese tema es pertinente para XAML que no es específico de un marco de trabajo de implementación concreto.)  
  
## <a name="member-definitions"></a>Definiciones de miembros  
 Los tipos pueden definir a miembros para el uso XAML. Es posible para los tipos que definen a los miembros que se pueden utilizar XAML aunque ese tipo específico no esté XAML utilizable. Esto es posible debido a la herencia de CLR. Siempre y cuando algún tipo que hereda al miembro es compatible con el uso XAML como un tipo y el miembro admite el uso XAML para su tipo subyacente o tiene una sintaxis XAML nativo disponible, ese miembro es XAML utilizable.  
  
### <a name="properties"></a>Propiedades  
 Si define propiedades como una propiedad pública de CLR mediante CLR típico `get` y `set` correspondiente al lenguaje, las palabras clave y los patrones de descriptor de acceso, el sistema de tipos XAML puede notificar la propiedad como un miembro con la información correspondiente se proporciona para <xref:System.Xaml.XamlMember> propiedades, como <xref:System.Xaml.XamlMember.IsReadPublic%2A> y <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Propiedades concretas pueden habilitar una sintaxis de texto aplicando <xref:System.ComponentModel.TypeConverterAttribute>. Para obtener más información, consulte [convertidores de tipos y extensiones de marcado para XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 En ausencia de una sintaxis de texto o la conversión de XAML nativa y en ausencia de más direccionamiento indirecto, como el uso de una extensión de marcado, el tipo de una propiedad (<xref:System.Xaml.XamlMember.TargetType%2A> sistema de tipos en el código XAML) debe ser capaz de devolver una instancia a un escritor de objetos XAML tratando el t tipo de arget como un tipo CLR.  
  
 Si utiliza XAML 2009, [extensión de marcado x: Reference](../../../docs/framework/xaml-services/x-reference-markup-extension.md) puede usarse para proporcionar valores si no se cumplen las consideraciones anteriores; sin embargo, que es más de un problema de uso de un problema de definición de tipo.  
  
### <a name="events"></a>Eventos  
 Si define los eventos como un evento CLR público, el sistema de tipos XAML puede notificar el evento como un miembro con <xref:System.Xaml.XamlMember.IsEvent%2A> como `true`. Cableado de los controladores de eventos no está dentro del ámbito de las capacidades de servicios XAML de .NET Framework; Esto se deja para las implementaciones y marcos de trabajo específicos.  
  
### <a name="methods"></a>Métodos  
 Código en línea para los métodos no es una capacidad XAML de forma predeterminada. En la mayoría de los casos no haga referencia directamente los miembros de método desde XAML y el rol de métodos en XAML es solo proporcionar compatibilidad con modelos de XAML concretos. [x: FactoryMethod (directiva)](../../../docs/framework/xaml-services/x-factorymethod-directive.md) es una excepción.  
  
### <a name="fields"></a>Campos  
 Instrucciones de diseño CLR desaconsejar campos no estáticos. Para los campos estáticos, puede tener acceso a valores de campo estático solo mediante [extensión de marcado x: Static](../../../docs/framework/xaml-services/x-static-markup-extension.md); en este caso, no realiza ninguna acción especial en la definición de CLR para exponer un campo para [x: Static](../../../docs/framework/xaml-services/x-static-markup-extension.md) usos.  
  
## <a name="attachable-members"></a>Miembros adjuntables  
 Los miembros adjuntables se exponen a XAML a través de un patrón de método de descriptor de acceso en un tipo de definición. El propio tipo de definición no es necesario que se pueda usar XAML como un objeto. De hecho, un patrón común es declarar una clase de servicio cuya función es el propietario del miembro adjuntable e implementar comportamientos relacionados, pero no sirven ninguna otra función como una representación de la interfaz de usuario. Para las siguientes secciones, el marcador de posición *PropertyName* representa el nombre del miembro adjuntable. Este nombre debe ser válido en el [XamlName (gramática)](../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 Tenga cuidado de conflictos de nombres entre estos modelos y otros métodos de un tipo. Si existe un miembro que coincide con uno de los modelos, se puede interpretar como una ruta de uso del miembro adjuntable con un procesador XAML aunque no era su intención.  
  
#### <a name="the-getpropertyname-accessor"></a>El descriptor de acceso GetPropertyName  
 La signatura del descriptor de acceso `Get`*NombreDePropiedad* debe ser:  
  
 `public static object Get` *NombreDePropiedad* `(object`  `target` `)`  
  
-   El objeto `target` puede especificarse como un tipo más específico en la implementación. Ya puede utilizarla para definir el ámbito del uso del miembro adjuntable; usos fuera del ámbito deseado producirán excepciones de conversión no válida que se exponen a través de un error de análisis XAML. El nombre del parámetro `target` no es un requisito, pero se denomina `target` por convención en la mayoría de las implementaciones.  
  
-   El valor devuelto puede especificarse como un tipo más específico en la implementación.  
  
 Para admitir un <xref:System.ComponentModel.TypeConverter> sintaxis de texto habilitada para el uso de atributos del miembro adjuntable, aplicar <xref:System.ComponentModel.TypeConverterAttribute> a la `Get` *PropertyName* descriptor de acceso. Aplicar a la `get` en lugar de la `set` puede parecer intuitivo; sin embargo, esta convención puede admitir el concepto de solo lectura que se puede asociar los miembros que son serializables, lo que resulta útil en escenarios del diseñador.  
  
#### <a name="the-setpropertyname-accessor"></a>El descriptor de acceso SetPropertyName  
 La firma para el conjunto de*PropertyName* descriptor de acceso debe ser:  
  
 `public static void Set` *NombreDePropiedad* `(object`  `target` `, object`  `value` `)`  
  
-   La `target` objeto puede especificarse como un tipo más específico en la implementación, con la misma lógica y consecuencias tal y como se describe en la sección anterior.  
  
-   El objeto `value` puede especificarse como un tipo más específico en la implementación.  
  
 Recuerde que el valor de este método es la entrada procedente del uso de XAML, normalmente en forma de atributo. De forma de atributo debe ser compatibles con la conversión de valor para una sintaxis de texto y atributo en la `Get` *PropertyName* descriptor de acceso.  
  
### <a name="attachable-member-stores"></a>Almacenes de miembro adjuntable  
 Los métodos de descriptor de acceso normalmente no son suficientes para proporcionar un medio para situar los valores de miembro adjuntable en un gráfico de objetos, o para recuperar los valores del gráfico de objetos y serializarlos correctamente. Para proporcionar esta funcionalidad, la `target` objetos en las firmas de descriptor de acceso anterior deben ser capaces de almacenar valores. El mecanismo de almacenamiento debe ser coherente con el principio del miembro adjuntable que el miembro es que se puede asociar a los destinos donde el miembro adjuntable no está en la lista de miembros. Servicios XAML de .NET framework proporciona una técnica de implementación para el miembro adjuntable almacena a través de la API <xref:System.Xaml.IAttachedPropertyStore> y <xref:System.Xaml.AttachablePropertyServices>. <xref:System.Xaml.IAttachedPropertyStore>se usa por los escritores XAML para detectar la implementación del almacén y deben implementarse en el tipo que es el `target` de los descriptores de acceso. El método estático <xref:System.Xaml.AttachablePropertyServices> API se utilizan dentro del cuerpo de los descriptores de acceso y hacer referencia al miembro adjuntable por su <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## <a name="xaml-related-clr-attributes"></a>Atributos CLR relacionados con XAML  
 Atribución correctamente sus tipos, miembros y ensamblados es importante para notificar información del sistema de tipo XAML a los servicios XAML de .NET Framework. Esto es importante si piensa que los tipos para su uso con los sistemas de XAML directamente se basan en lectores de servicios XAML de .NET Framework y escritores XAML, o si define o usar un marco de uso de XAML que se basa en los lectores XAML y escritores de XAML.  
  
 Para obtener una lista de cada atributo relacionados con XAML que es relevante para la compatibilidad XAML de sus tipos personalizados, vea [Related CLR atributos para tipos y bibliotecas personalizados](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="usage"></a>Uso  
 Uso de tipos personalizados requiere que el autor de marcado debe asignar un prefijo para el ensamblado y el espacio de nombres CLR que contienen el tipo personalizado. Este procedimiento no está documentado en este tema.  
  
## <a name="access-level"></a>Nivel de acceso  
 XAML proporciona un medio para cargar y crear instancias de tipos que tienen un `internal` nivel de acceso. Esta funcionalidad se proporciona para que el código de usuario puede definir sus propios tipos y, a continuación, crear instancias de esas clases desde el marcado que también forma parte del mismo ámbito de código de usuario.  
  
 Un ejemplo de WPF es cada vez que el código de usuario define un <xref:System.Windows.Controls.UserControl> que sirve como una manera de refactorizar un comportamiento de la interfaz de usuario, pero no como parte de cualquier mecanismo de extensión posibles que se puede deducir mediante la declaración de la clase de compatibilidad con `public` nivel de acceso. Este tipo una <xref:System.Windows.Controls.UserControl> se pueden declarar con `internal` acceso si se compila el código auxiliar en el mismo ensamblado desde el que se hace referencia como un tipo XAML.  
  
 Para una aplicación que carga el XAML con plena confianza y usa <xref:System.Xaml.XamlObjectWriter>, cargar clases con `internal` siempre está habilitado el nivel de acceso.  
  
 Para una aplicación que carga el XAML con confianza parcial, puede controlar las características de nivel de acceso mediante el <xref:System.Xaml.Permissions.XamlAccessLevel> API. Además, debe tener propagar los permisos de nivel de acceso y los conserva para las evaluaciones de tiempo de ejecución eventual; mecanismos de aplazamiento (por ejemplo, el sistema de plantilla WPF) Esto se controla internamente pasando el <xref:System.Xaml.Permissions.XamlAccessLevel> información.  
  
### <a name="wpf-implementation"></a>Implementación de WPF  
 XAML de WPF usa un modelo de acceso de confianza parcial donde si BAML se carga bajo confianza parcial, el acceso está restringido a <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> para el ensamblado que es el origen BAML. Para el aplazamiento, WPF utiliza <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> como un mecanismo para pasar la información de nivel de acceso.  
  
 En la terminología de XAML de WPF, un *tipo interno* es un tipo definido por el mismo ensamblado que también incluye el archivo XAML de referencia. Estos tipos pueden asignarse a través de un espacio de nombres XAML que omite deliberadamente el ensamblado = parte de una asignación, por ejemplo, `xmlns:local="clr-namespace:WPFApplication1"`.  Si BAML hace referencia a un tipo interno y que tiene el tipo `internal` tener acceso a nivel de esta forma se genera un `GeneratedInternalTypeHelper` clase del ensamblado. Si desea evitar `GeneratedInternalTypeHelper`, ya sea debe usar `public` acceso a nivel de, o debe separe la clase relevante en un ensamblado independiente y hacer que ese ensamblado dependiente.  
  
## <a name="see-also"></a>Vea también  
 [Atributos de CLR relacionados con XAML para los tipos y bibliotecas personalizados](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)  
 [Servicios XAML](../../../docs/framework/xaml-services/index.md)
