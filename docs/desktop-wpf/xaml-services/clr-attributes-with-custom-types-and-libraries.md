---
title: Atributos de CLR relacionados con XAML para los tipos y bibliotecas personalizados
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 5481d02e4d393312fa0f0dd13b45c54acc567e13
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432987"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>Atributos CLR relacionados con XAML para bibliotecas y tipos personalizados

En este tema se describen los atributos de Common Language Runtime (CLR) definidos por los servicios XAML de .NET. También describe otros atributos CLR que se definen en .NET que tienen un escenario relacionado con XAML para la aplicación a ensamblados o tipos. Atribuir ensamblados, tipos o miembros con estos atributos CLR proporciona información del sistema de tipos XAML relacionada con los tipos. La información se proporciona a cualquier consumidor XAML que use los servicios XAML de .NET para procesar el flujo de nodo XAML directamente o a través de los lectores XAML dedicados y escritores XAML.

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>Atributos CLR relacionados con XAML para tipos personalizados y miembros personalizados

El uso de atributos CLR implica que está utilizando el CLR general para definir los tipos, de lo contrario dichos atributos no están disponibles. Si usa clr para definir la copia de seguridad de tipos, el contexto de esquema XAML predeterminado utilizado por los escritores XAML de servicios XAML de .NET puede leer la atribución de CLR a través de la reflexión en ensamblados de respaldo.

En las secciones siguientes se describen los atributos relacionados con XAML que se pueden aplicar a tipos personalizados o miembros personalizados. Cada atributo CLR comunica información relevante para un sistema de tipos XAML. En la ruta de acceso de carga, la información con atributos ayuda al lector XAML a formar un flujo de nodo XAML válido o ayuda al escritor XAML a generar un gráfico de objetos válido. En la ruta de acceso de guardado, la información con atributos ayuda al lector XAML a formar un flujo de nodo XAML válido que reconstituye la información del sistema de tipos XAML; o declara sugerencias de serialización o requisitos para el escritor XAML u otros consumidores XAML.

### <a name="ambientattribute"></a>AmbientAttribute

**Documentación de referencia:**<xref:System.Windows.Markup.AmbientAttribute>

**Se aplica a:** Miembros de `get` clase, propiedad o descriptor de acceso que admiten propiedades adjuntables.

**Argumentos:** Ninguno

<xref:System.Windows.Markup.AmbientAttribute>indica que la propiedad, o todas las propiedades que toman el tipo con atributos, deben interpretarse bajo el concepto de propiedad ambiente en XAML. El concepto de ambiente se relaciona con la forma en que los procesadores XAML determinan los propietarios de tipos de los miembros. Una propiedad ambiente es una propiedad donde se espera que el valor esté disponible en el contexto del analizador al crear un gráfico de objetos, pero donde se suspende la búsqueda típica de miembro de tipo para el conjunto de nodoXAML inmediato que se está creando.

El concepto ambiente se puede aplicar a los miembros adjuntables, que <xref:System.AttributeTargets>no se representan como propiedades en términos de cómo define la atribución de CLR . El uso de atribución `get` del método solo se debe aplicar a un descriptor de acceso que admita el uso adjuntable para XAML.

### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>

**Se aplica a:** Clase

**Argumentos:** Cadena que especifica el nombre de la propiedad que coincide con un único argumento de constructor.

<xref:System.Windows.Markup.ConstructorArgumentAttribute>especifica que un objeto se puede inicializar mediante una sintaxis de constructor sin parámetros y que una propiedad del nombre especificado proporciona información de construcción. Esta información sirve principalmente para la serialización XAML. Para obtener más información, vea <xref:System.Windows.Markup.ConstructorArgumentAttribute>.

### <a name="contentpropertyattribute"></a>ContentPropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.ContentPropertyAttribute>

**Se aplica a:** Clase

**Argumentos:** Cadena que especifica el nombre de un miembro del tipo con atributos.

<xref:System.Windows.Markup.ContentPropertyAttribute>indica que la propiedad nombrada por el argumento debe servir como la propiedad de contenido XAML para ese tipo. La definición de propiedad de contenido XAML hereda a todos los tipos derivados que se pueden asignar al tipo de definición. Puede invalidar la definición en un tipo <xref:System.Windows.Markup.ContentPropertyAttribute> derivado específico aplicando en el tipo derivado específico.

Para la propiedad que actúa como la propiedad de contenido XAML, el etiquetado de elementos de propiedad para la propiedad se puede omitir en el uso XAML. Normalmente, se designan propiedades de contenido XAML que promueven un marcado XAML simplificado para el contenido y los modelos de contención. Dado que solo un miembro se puede designar como la propiedad de contenido XAML, a veces tiene opciones de diseño para realizar con respecto a cuál de varias propiedades de contenedor de un tipo se debe designar como la propiedad de contenido XAML. Las otras propiedades de contenedor se deben usar con elementos de propiedad explícitos.

En el flujo de nodo XAML, `StartMember` `EndMember` las propiedades de contenido XAML <xref:System.Xaml.XamlMember>siguen produciendo y nodos, utilizando el nombre de la propiedad para el archivo . Para determinar si un miembro es la <xref:System.Xaml.XamlType> propiedad `StartObject` de contenido XAML, <xref:System.Xaml.XamlType.ContentProperty%2A>examine el valor de la posición y obtenga el valor de .

### <a name="contentwrapperattribute"></a>ContentWrapperAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.ContentWrapperAttribute>

**Se aplica a:** Clase, específicamente tipos de colección.

**Argumentos:** A <xref:System.Type> que especifica el tipo que se usará como tipo de contenedor de contenido para contenido externo.

<xref:System.Windows.Markup.ContentWrapperAttribute>especifica uno o varios tipos en el tipo de colección asociado que se usará para ajustar el contenido externo. Contenido externo hace referencia a casos en los que las restricciones del sistema de tipos en el tipo de la propiedad de contenido no capturan todos los posibles casos de contenido que admitiría el uso de XAML para el tipo propietario. Por ejemplo, la compatibilidad con XAML para el contenido de <xref:System.Collections.ObjectModel.Collection%601>un tipo determinado podría admitir cadenas en un genérico fuertemente tipado. Los contenedores de contenido son útiles para migrar convenciones de marcado preexistentes a la concepción de XAML de valores asignables para colecciones, como la migración de modelos de contenido relacionados con el texto.

Para especificar más de un tipo de contenedor de contenido, aplique el atributo varias veces.

### <a name="dependsonattribute"></a>DependsOnAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.DependsOnAttribute>

**Se aplica a:** Propiedad

**Argumentos:** Cadena que especifica el nombre de otro miembro del tipo con atributos.

<xref:System.Windows.Markup.DependsOnAttribute>indica que la propiedad con atributos depende del valor de otra propiedad. Aplicar este atributo a una definición de propiedad garantiza que las propiedades dependientes se procesan primero en la escritura de objetos XAML. Los usos de <xref:System.Windows.Markup.DependsOnAttribute> especificar los casos excepcionales de propiedades en tipos donde se debe seguir un orden específico de análisis para la creación de objetos válidos.

Puede aplicar <xref:System.Windows.Markup.DependsOnAttribute> varios casos a una definición de propiedad.

### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

**Se aplica a:** Clase, que se espera <xref:System.Windows.Markup.MarkupExtension> que sea un tipo derivado.

**Argumentos:** A <xref:System.Type> que especifica el tipo más `ProvideValue` preciso que se <xref:System.Windows.Markup.MarkupExtension>puede esperar como resultado del atributo .

Para obtener más información, vea [Extensiones](markup-extensions-overview.md)de marcado para información general sobre XAML .

### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>

**Se aplica a:** Clase

**Argumentos:** Admite dos formas de atribución:

- Cadena que especifica el nombre de una propiedad en el tipo con atributos.

- Cadena que especifica el nombre de una <xref:System.Type> propiedad y un para el tipo que define la propiedad con nombre. Este formulario es para especificar un miembro adjuntable como la propiedad de ámbito de nombres XAML.

<xref:System.Windows.Markup.NameScopePropertyAttribute>especifica una propiedad que proporciona el valor de ámbito de nombres XAML para la clase con atributos. Se espera que la propiedad de ámbito <xref:System.Windows.Markup.INameScope> de nombres XAML haga referencia a un objeto que implementa y contiene el ámbito de nombres XAML real, su almacén y su comportamiento.

### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

**Se aplica a:** Clase

**Argumentos:** Cadena que especifica el nombre de la propiedad de nombre en tiempo de ejecución en el tipo con atributos.

<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>notifica una propiedad del tipo con atributos que se asigna a la [directiva x:Name de](xname-directive.md)XAML . La propiedad debe <xref:System.String> ser de tipo y debe ser de lectura y escritura.

La definición hereda a todos los tipos derivados que se pueden asignar al tipo de definición. Puede invalidar la definición en un tipo <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> derivado específico aplicando en el tipo derivado específico.

### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

**Se aplica a:** Tipos

**Argumentos:** Ninguno.

<xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>se aplica a tipos específicos que pueden aparecer como elementos secundarios dentro <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>de contenido significativo de espacio en blanco (contenido mantenido por una colección que tiene ). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>es principalmente relevante para la ruta de acceso de guardado, pero <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>está disponible en el sistema de tipos XAML en la ruta de acceso de carga examinando . Para obtener más información, vea [Procesamiento de espacio en blanco en XAML](white-space-processing.md).

### <a name="typeconverterattribute"></a>TypeConverterAttribute

**Documentación de referencia:**  <xref:System.ComponentModel.TypeConverterAttribute>

**Se aplica a:** Clase, propiedad, método (el único caso `get` de método válido para XAML es un descriptor de acceso que admite un miembro adjuntable).

**Argumentos:** El <xref:System.Type> de <xref:System.ComponentModel.TypeConverter>la .

<xref:System.ComponentModel.TypeConverterAttribute>en un contexto XAML <xref:System.ComponentModel.TypeConverter>hace referencia a un archivo . Esto <xref:System.ComponentModel.TypeConverter> proporciona un comportamiento de conversión de tipos para tipos personalizados o miembros de ese tipo.

Aplique <xref:System.ComponentModel.TypeConverterAttribute> el atributo al tipo, haciendo referencia a la implementación del convertidor de tipos. Puede definir convertidores de tipos para XAML en clases, estructuras o interfaces. No es necesario proporcionar la conversión de tipos para las enumeraciones, que la conversión está habilitada de forma nativa.

El convertidor de tipos debe ser capaz de convertir de una cadena que se usa para atributos o texto de inicialización en el marcado, en el tipo de destino previsto. Para obtener más información, vea [TypeConverters y XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).

En lugar de aplicar a todos los valores de un tipo, también se puede establecer un comportamiento de convertidor de tipos para XAML en una propiedad específica. En este caso, <xref:System.ComponentModel.TypeConverterAttribute> se aplica a la definición `get` de `set` propiedad (la definición externa, no la específica y las definiciones).

Un comportamiento de convertidor de tipos para el uso XAML <xref:System.ComponentModel.TypeConverterAttribute> de `get` un miembro adjuntable personalizado se puede asignar mediante la aplicación al descriptor de acceso de método que admite el uso XAML.

Similar <xref:System.ComponentModel.TypeConverter>a <xref:System.ComponentModel.TypeConverterAttribute> , existía en .NET antes de la existencia de XAML y el modelo de convertidor de tipos servía a otros propósitos. Para hacer referencia <xref:System.ComponentModel.TypeConverterAttribute>y utilizar, debe calificarlo `using` completamente <xref:System.ComponentModel>o proporcionar una declaración para . Incluya también el ensamblado del sistema en el proyecto.

### <a name="uidpropertyattribute"></a>UidPropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.UidPropertyAttribute>

**Se aplica a:** Clase

**Argumentos:** Cadena que hace referencia a la propiedad relevante por nombre.

Indica la propiedad CLR de una clase que da alias a la [directiva x:Uid](xuid-directive.md).

### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>

**Se aplica a:** Clase

**Argumentos:** Un booleano. Si se utiliza para el propósito previsto del `true`atributo, el valor debe establecerse en .

Indica si el tipo se compila de arriba hacia abajo durante la creación del gráfico de objetos XAML. Este es un concepto avanzado, que probablemente está estrechamente relacionado con la definición de su modelo de programación. Para obtener más información, vea <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.

### <a name="valueserializerattribute"></a>ValueSerializerAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.ValueSerializerAttribute>

**Se aplica a:** Clase, propiedad, método (el único caso `get` de método válido para XAML es un descriptor de acceso que admite un miembro adjuntable).

**Argumentos:** A <xref:System.Type> que especifica la clase de compatibilidad del serializador de valores que se usará al serializar todas las propiedades del tipo con atributos o la propiedad con atributos específica.

<xref:System.Windows.Markup.ValueSerializer>especifica una clase de serialización de valores <xref:System.ComponentModel.TypeConverter> que requiere más estado y contexto que un valor. <xref:System.Windows.Markup.ValueSerializer>se puede asociar a un miembro <xref:System.Windows.Markup.ValueSerializerAttribute> adjuntable aplicando el atributo en el método de descriptor de acceso estático `get` para el miembro adjuntable. La serialización de valores también es aplicable a enumeraciones, interfaces y estructuras, pero no a los delegados.

### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

**Se aplica a:** Clase, específicamente tipos de colección que se espera que hospeden contenido mixto, donde el espacio en blanco alrededor de los elementos de objeto podría ser significativo para la representación de la interfaz de usuario.

**Argumentos:** Ninguno.

<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>indica que un procesador XAML debe procesar un tipo de colección como espacio en blanco significativo, lo que influye en la construcción de los nodos de valor del flujo de nodo XAML dentro de la colección. Para obtener más información, vea [Procesamiento de espacio en blanco en XAML](white-space-processing.md).

### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>

**Se aplica a:** Clase, propiedad.

**Argumentos:** Admite dos tipos de formularios de <xref:System.Type>atribución como cadenas o tipos como . Vea <xref:System.Windows.Markup.XamlDeferLoadAttribute>.

Indica que una clase o propiedad usa la carga aplazada para XAML (como el comportamiento de una plantilla) e informa de la clase que habilita el comportamiento de carga aplazada así como el tipo de contenido/destino.

### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>

**Se aplica a:** Clase

**Argumentos:** Asigna un nombre a la devolución de llamada.

Indica que una clase puede usar una extensión de marcado para proporcionar un valor para una o varias de sus propiedades y hace referencia a un controlador al que un escritor XAML debe llamar antes de realizar una operación de conjunto de extensión de marcado en cualquier propiedad de la clase.

### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>

**Se aplica a:** Clase

**Argumentos:** Asigna un nombre a la devolución de llamada.

Indica que una clase puede usar un convertidor de tipos para proporcionar un valor para una o varias de sus propiedades y hace referencia a un controlador al que un escritor XAML debe llamar antes de realizar una operación de conjunto de convertidor escalonados en cualquier propiedad de la clase.

### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>

**Se aplica a:** Clase

**Argumentos:** Cadena que especifica el nombre de la `xml:lang` propiedad a la que se va a alias en el tipo con atributos.

<xref:System.Windows.Markup.XmlLangPropertyAttribute>notifica una propiedad del tipo con atributos que se asigna a la directiva XML. `lang` La propiedad no es <xref:System.String> necesariamente de tipo, pero debe ser asignable desde una cadena (la asignación podría realizarse asociando un convertidor de tipos con el tipo de propiedad o con la propiedad específica). La propiedad debe ser de lectura y escritura.

El escenario `xml:lang` para la asignación es para que un modelo de objetos en tiempo de ejecución tenga acceso a información de lenguaje especificada por XML sin procesar específicamente con un XMLDOM.

La definición hereda a todos los tipos derivados que se pueden asignar al tipo de definición. Puede invalidar la definición en un tipo <xref:System.Windows.Markup.XmlLangPropertyAttribute> derivado específico aplicando en el tipo derivado específico, aunque se trata de un escenario poco común.

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>Atributos CLR relacionados con XAML en el nivel de ensamblado

En las secciones siguientes se describen los atributos relacionados con XAML que no se aplican a tipos o definiciones de miembro, sino que se aplican a ensamblados. Estos atributos son pertinentes para el objetivo general de definir una biblioteca que contiene tipos personalizados para usar en XAML. Algunos de los atributos no influyen necesariamente en el flujo de nodo XAML directamente, pero se pasan en el flujo de nodo para que otros consumidores los usen. Los consumidores de la información incluyen entornos de diseño o procesos de serialización que necesitan información de espacio de nombres XAML e información de prefijo asociada. Un contexto de esquema XAML (incluido el valor predeterminado de Servicios XAML de .NET) también usa esta información.

### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

**Argumentos:**

- Cadena que especifica el identificador del espacio de nombres XAML para subsume.

- Cadena que especifica el identificador del espacio de nombres XAML que puede subsume el espacio de nombres XAML del argumento anterior.

  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>especifica que otro espacio de nombres XAML puede subsumir un espacio de nombres XAML. Normalmente, el espacio de nombres XAML que realiza la inclusión se indica en un objeto <xref:System.Windows.Markup.XmlnsDefinitionAttribute> definido anteriormente. Esta técnica se puede usar para versionar un vocabulario XAML en una biblioteca y para hacerlo compatible con el marcado definido anteriormente con el vocabulario versionado anterior.

### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

**Argumentos:**

- Cadena que especifica el identificador del espacio de nombres XAML que se va a definir.

- Cadena que nombra un espacio de nombres CLR. El espacio de nombres CLR debe definir tipos públicos en el ensamblado y al menos uno de los tipos de espacio de nombres CLR debe estar pensado para el uso XAML.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>especifica una asignación por ensamblado entre un espacio de nombres XAML y un espacio de nombres CLR, que luego se usa para la resolución de tipos por un escritor de objetos XAML o un contexto de esquema XAML.

  Se puede <xref:System.Windows.Markup.XmlnsDefinitionAttribute> aplicar más de uno a un ensamblaje. Esto se puede hacer por cualquier combinación de las siguientes razones:

- El diseño de la biblioteca contiene varios espacios de nombres CLR para la organización lógica del acceso a la API en tiempo de ejecución; sin embargo, desea que todos los tipos de esos espacios de nombres sean utilizables por XAML haciendo referencia al mismo espacio de nombres XAML. En este caso, <xref:System.Windows.Markup.XmlnsDefinitionAttribute> se aplican <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> varios atributos con el mismo valor pero valores diferentes. <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> Esto es especialmente útil si está definiendo asignaciones para el espacio de nombres XAML que el marco de trabajo o la aplicación pretende ser el espacio de nombres XAML predeterminado en uso común.

- El diseño de biblioteca contiene varios espacios de nombres CLR y desea una separación deliberada del espacio de nombres XAML entre los usos de tipos en esos espacios de nombres CLR.

- Defina un espacio de nombres CLR en el ensamblado y desea que sea accesible a través de más de un espacio de nombres XAML. Este escenario se produce cuando se admiten varios vocabularios con el mismo código base.

- La compatibilidad con el lenguaje XAML se define en uno o varios espacios de nombres CLR. En este caso, <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> el `http://schemas.microsoft.com/winfx/2006/xaml`valor debe ser .

### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>

**Argumentos:**

- Cadena que especifica el identificador de un espacio de nombres XAML.

- Cadena que especifica un prefijo recomendado.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>especifica un prefijo recomendado para usar para un espacio de nombres XAML. El prefijo es útil al escribir elementos y atributos en <xref:System.Xaml.XamlXmlWriter>un archivo XAML serializado por los servicios XAML de .NET o cuando una biblioteca de implementación XAML interactúa con un entorno de diseño que tiene características de edición XAML.

  Se puede <xref:System.Windows.Markup.XmlnsPrefixAttribute> aplicar más de uno a un ensamblaje. Esto se puede hacer por cualquier combinación de las siguientes razones:

- El ensamblado define tipos para más de un espacio de nombres XAML. En este caso, defina valores de prefijo diferentes para cada espacio de nombres XAML.

- Admite varios vocabularios y usa prefijos diferentes para cada vocabulario y espacio de nombres XAML.

- La compatibilidad con el lenguaje XAML <xref:System.Windows.Markup.XmlnsDefinitionAttribute> `http://schemas.microsoft.com/winfx/2006/xaml`se define en el ensamblado y tiene un for . En este caso, normalmente debe `x`promover el prefijo .

> [!NOTE]
> Servicios XAML de .NET también <xref:System.Windows.Markup.RootNamespaceAttribute>define el atributo relacionado con XAML. Este atributo es un atributo de nivel de ensamblado para la compatibilidad con el sistema de proyectos y no es relevante para los tipos personalizados XAML.

## <a name="see-also"></a>Consulte también

- <xref:System.Attribute>
- [Definición de tipos personalizados para usarlos con los servicios XAML de .NET](define-custom-types.md)
