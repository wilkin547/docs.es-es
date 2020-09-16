---
title: Atributos de CLR relacionados con XAML para los tipos y bibliotecas personalizados
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: a4b8a58ea2c7d9de2b59ed78dc37e4ce1c434b79
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535402"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>Atributos de CLR relacionados con XAML para los tipos y bibliotecas personalizados

En este tema se describen los atributos de Common Language Runtime (CLR) definidos por los servicios XAML de .NET. También se describen otros atributos CLR definidos en .NET que tienen un escenario relacionado con XAML para la aplicación a ensamblados o tipos. La atribución de ensamblados, tipos o miembros con estos atributos CLR proporciona información del sistema de tipos XAML relacionada con los tipos. Se proporciona información a cualquier consumidor XAML que use los servicios XAML de .NET para procesar el flujo de nodo XAML directamente o a través de los lectores XAML y escritores de XAML dedicados.

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>Atributos de CLR relacionados con XAML para los tipos personalizados y los miembros personalizados

El uso de atributos CLR implica que se usa el CLR global para definir los tipos; de lo contrario, estos atributos no estarán disponibles. Si usa CLR para definir la copia de seguridad de tipos, el contexto de esquema XAML predeterminado utilizado por los escritores de XAML de los servicios XAML de .NET puede leer la atribución de CLR mediante la reflexión en los ensamblados de respaldo.

En las secciones siguientes se describen los atributos relacionados con XAML que se pueden aplicar a los tipos personalizados o a los miembros personalizados. Cada atributo CLR comunica información que es relevante para un sistema de tipos XAML. En la ruta de acceso de carga, la información con atributos ayuda al lector de XAML a formar un flujo de nodo XAML válido o ayuda al escritor de XAML a generar un gráfico de objetos válido. En la ruta de acceso de guardado, la información con atributos ayuda al lector de XAML a formar una secuencia de nodo XAML válida que reconstituye la información del sistema de tipos XAML. también se declaran sugerencias o requisitos de serialización para el escritor XAML u otros consumidores XAML.

### <a name="ambientattribute"></a>AmbientAttribute

**Documentación de referencia:**<xref:System.Windows.Markup.AmbientAttribute>

**Se aplica a:** Miembros de clase, propiedad o `get` descriptor de acceso que admiten propiedades adjuntables.

**Argumentos:** Ninguna

<xref:System.Windows.Markup.AmbientAttribute> indica que la propiedad, o todas las propiedades que toman el tipo con atributos, debe interpretarse en el concepto de propiedad de ambiente en XAML. El concepto de ambiente se relaciona con la forma en que los procesadores XAML determinan los propietarios de tipos de los miembros. Una propiedad de ambiente es una propiedad en la que se espera que el valor esté disponible en el contexto del analizador al crear un gráfico de objetos, pero donde se suspende la búsqueda de miembros de tipo típica para el conjunto de nodos XAML inmediato que se está creando.

El concepto ambiente se puede aplicar a los miembros que se pueden adjuntar, que no se representan como propiedades en cuanto a cómo se define la atribución de CLR <xref:System.AttributeTargets> . El uso de atribución de métodos solo debe aplicarse a un `get` descriptor de acceso que admita el uso adjuntable para XAML.

### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>

**Se aplica a:** Las

**Argumentos:** Cadena que especifica el nombre de la propiedad que coincide con un argumento de constructor único.

<xref:System.Windows.Markup.ConstructorArgumentAttribute> Especifica que un objeto se puede inicializar usando una sintaxis de constructor sin parámetros y que una propiedad del nombre especificado proporciona información de construcción. Esta información sirve principalmente para la serialización XAML. Para obtener más información, vea <xref:System.Windows.Markup.ConstructorArgumentAttribute>.

### <a name="contentpropertyattribute"></a>ContentPropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.ContentPropertyAttribute>

**Se aplica a:** Las

**Argumentos:** Cadena que especifica el nombre de un miembro del tipo con atributos.

<xref:System.Windows.Markup.ContentPropertyAttribute> indica que la propiedad con el nombre del argumento debe servir como la propiedad de contenido XAML para ese tipo. La definición de la propiedad de contenido XAML hereda de todos los tipos derivados que se pueden asignar al tipo de definición. Puede invalidar la definición en un tipo derivado específico aplicando <xref:System.Windows.Markup.ContentPropertyAttribute> en el tipo derivado específico.

En el caso de la propiedad que actúa como la propiedad de contenido XAML, el etiquetado de elementos de propiedad de la propiedad se puede omitir en el uso de XAML. Normalmente, se designan propiedades de contenido XAML que promueven un marcado XAML simplificado para los modelos de contenido y de contención. Dado que solo se puede designar un miembro como la propiedad de contenido XAML, a veces tiene que elegir las opciones de diseño para la que se deben designar varias propiedades de contenedor de un tipo como la propiedad de contenido XAML. Las demás propiedades del contenedor deben usarse con elementos de propiedad explícitos.

En el flujo de nodo XAML, las propiedades de contenido XAML siguen produciendo `StartMember` `EndMember` nodos y, utilizando el nombre de la propiedad para <xref:System.Xaml.XamlMember> . Para determinar si un miembro es la propiedad de contenido XAML, examine el <xref:System.Xaml.XamlType> valor de la `StartObject` posición y obtenga el valor de <xref:System.Xaml.XamlType.ContentProperty%2A> .

### <a name="contentwrapperattribute"></a>ContentWrapperAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.ContentWrapperAttribute>

**Se aplica a:** Clase, específicamente tipos de colección.

**Argumentos:** <xref:System.Type> Que especifica el tipo que se va a usar como tipo de contenedor de contenido para el contenido externo.

<xref:System.Windows.Markup.ContentWrapperAttribute> especifica uno o más tipos en el tipo de colección asociado que se usará para encapsular el contenido externo. El contenido externo hace referencia a los casos en los que las restricciones del sistema de tipos en el tipo de la propiedad de contenido no capturan todos los casos de contenido posibles que el uso de XAML para el tipo propietario admita. Por ejemplo, la compatibilidad con XAML para el contenido de un tipo determinado podría admitir cadenas en un genérico fuertemente tipado <xref:System.Collections.ObjectModel.Collection%601> . Los contenedores de contenido son útiles para migrar convenciones de marcado preexistentes a la concepción de XAML de valores asignables para colecciones, como la migración de modelos de contenido relacionados con texto.

Para especificar más de un tipo de contenedor de contenido, aplique varias veces el atributo.

### <a name="dependsonattribute"></a>DependsOnAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.DependsOnAttribute>

**Se aplica a:** Propiedad

**Argumentos:** Cadena que especifica el nombre de otro miembro del tipo con atributos.

<xref:System.Windows.Markup.DependsOnAttribute> indica que la propiedad con atributos depende del valor de otra propiedad. Aplicar este atributo a una definición de propiedad garantiza que las propiedades dependientes se procesan en primer lugar en la escritura de objetos XAML. Los usos de <xref:System.Windows.Markup.DependsOnAttribute> especifican los casos excepcionales de propiedades en tipos en los que se debe seguir un orden específico de análisis para la creación de objetos válidos.

Puede aplicar varios <xref:System.Windows.Markup.DependsOnAttribute> casos a una definición de propiedad.

### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

**Se aplica a:** Clase, que se espera que sea un <xref:System.Windows.Markup.MarkupExtension> tipo derivado.

**Argumentos:** <xref:System.Type> Que especifica el tipo más preciso que se va a esperar como `ProvideValue` resultado del atributo <xref:System.Windows.Markup.MarkupExtension> .

Para obtener más información, vea [información general sobre las extensiones de marcado para XAML](markup-extensions-overview.md).

### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>

**Se aplica a:** Las

**Argumentos:** Admite dos formas de atribución:

- Cadena que especifica el nombre de una propiedad en el tipo con atributos.

- Una cadena que especifica el nombre de una propiedad y un <xref:System.Type> para el tipo que define la propiedad con nombre. Este formulario consiste en especificar un miembro adjuntable como la propiedad del ámbito de nombres XAML.

<xref:System.Windows.Markup.NameScopePropertyAttribute> especifica una propiedad que proporciona el valor de ámbito de nombres XAML para la clase con atributos. Se espera que la propiedad de ámbito de nombres XAML haga referencia a un objeto que implementa <xref:System.Windows.Markup.INameScope> y contiene el ámbito de nombres XAML real, su almacén y su comportamiento.

### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

**Se aplica a:** Las

**Argumentos:** Cadena que especifica el nombre de la propiedad de nombre en tiempo de ejecución en el tipo con atributos.

<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> notifica una propiedad del tipo con atributos que se asigna a la [Directiva x:Name](xname-directive.md)de XAML. La propiedad debe ser de tipo <xref:System.String> y debe ser de lectura/escritura.

La definición hereda a todos los tipos derivados que se pueden asignar al tipo de definición. Puede invalidar la definición en un tipo derivado específico aplicando <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> en el tipo derivado específico.

### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

**Se aplica a:** Distintos

**Argumentos:** Ninguna.

<xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> se aplica a tipos específicos que pueden aparecer como elementos secundarios dentro de contenido significativo de espacio en blanco (contenido mantenido por una colección que tiene <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> ). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> está principalmente relacionado con la ruta de acceso de guardado, pero está disponible en el sistema de tipos XAML en la ruta de acceso de carga examinando <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType> . Para obtener más información, vea [procesamiento de espacios en blanco en XAML](white-space-processing.md).

### <a name="typeconverterattribute"></a>TypeConverterAttribute

**Documentación de referencia:**  <xref:System.ComponentModel.TypeConverterAttribute>

**Se aplica a:** Clase, propiedad, método (el único caso de método válido de XAML es un `get` descriptor de acceso que admite un miembro adjuntable).

**Argumentos:** <xref:System.Type> Del <xref:System.ComponentModel.TypeConverter> .

<xref:System.ComponentModel.TypeConverterAttribute> en un contexto XAML hace referencia a un personalizado <xref:System.ComponentModel.TypeConverter> . Esto <xref:System.ComponentModel.TypeConverter> proporciona el comportamiento de la conversión de tipos para los tipos personalizados o los miembros de ese tipo.

Aplique el <xref:System.ComponentModel.TypeConverterAttribute> atributo al tipo, haciendo referencia a la implementación del convertidor de tipos. Puede definir convertidores de tipos para XAML en clases, estructuras o interfaces. No es necesario proporcionar la conversión de tipos para las enumeraciones, la conversión se habilita de forma nativa.

El convertidor de tipos debe ser capaz de convertir de una cadena que se utiliza para los atributos o el texto de inicialización en el marcado, en el tipo de destino deseado. Para obtener más información, vea [clases TypeConverter y XAML](/dotnet/desktop/wpf/advanced/typeconverters-and-xaml).

En lugar de aplicar a todos los valores de un tipo, un comportamiento del convertidor de tipos para XAML también se puede establecer en una propiedad concreta. En este caso, se aplica <xref:System.ComponentModel.TypeConverterAttribute> a la definición de propiedad (la definición externa, no las `get` definiciones y especificadas `set` ).

Un comportamiento del convertidor de tipos para el uso de XAML de un miembro adjuntable personalizado se puede asignar aplicando <xref:System.ComponentModel.TypeConverterAttribute> al `get` descriptor de acceso de método que admite el uso de XAML.

Similar a <xref:System.ComponentModel.TypeConverter> , <xref:System.ComponentModel.TypeConverterAttribute> existía en .net antes de la existencia de XAML y el modelo de convertidor de tipos ocupó otros propósitos. Para hacer referencia a ella y usarla <xref:System.ComponentModel.TypeConverterAttribute> , debe calificarla por completo o proporcionar una `using` instrucción para <xref:System.ComponentModel> . Incluya también el ensamblado del sistema en el proyecto.

### <a name="uidpropertyattribute"></a>UidPropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.UidPropertyAttribute>

**Se aplica a:** Las

**Argumentos:** Cadena que hace referencia a la propiedad pertinente por nombre.

Indica la propiedad CLR de una clase que tiene un alias de la [Directiva x:UID](xuid-directive.md).

### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>

**Se aplica a:** Las

**Argumentos:** Un valor booleano. Si se utiliza para la finalidad prevista del atributo, el valor debe establecerse en `true` .

Indica si el tipo se compila de forma descendente durante la creación del gráfico de objetos XAML. Se trata de un concepto avanzado, que probablemente esté estrechamente relacionado con la definición del modelo de programación. Para obtener más información, vea <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.

### <a name="valueserializerattribute"></a>ValueSerializerAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.ValueSerializerAttribute>

**Se aplica a:** Clase, propiedad, método (el único caso de método válido de XAML es un `get` descriptor de acceso que admite un miembro adjuntable).

**Argumentos:** <xref:System.Type> Que especifica la clase de compatibilidad del serializador de valor que se va a utilizar al serializar todas las propiedades del tipo con atributos o la propiedad con atributos específica.

<xref:System.Windows.Markup.ValueSerializer> especifica una clase de serialización de valor que requiere más estado y contexto que un <xref:System.ComponentModel.TypeConverter> . <xref:System.Windows.Markup.ValueSerializer> se puede asociar a un miembro adjuntable aplicando el <xref:System.Windows.Markup.ValueSerializerAttribute> atributo en el `get` método de descriptor de acceso estático para el miembro que se puede adjuntar. La serialización de valor también es aplicable a las enumeraciones, interfaces y estructuras, pero no a los delegados.

### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

**Se aplica a:** Clase, en concreto, los tipos de colección que se espera que hospeden contenido mixto, donde los espacios en blanco alrededor de los elementos de objeto podrían ser significativos para la representación de la interfaz de usuario.

**Argumentos:** Ninguna.

<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indica que un procesador XAML debe procesar un tipo de colección como un espacio en blanco significativo, lo que influye en la construcción de los nodos de valor del flujo de nodo XAML dentro de la colección. Para obtener más información, vea [procesamiento de espacios en blanco en XAML](white-space-processing.md).

### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>

**Se aplica a:** Clase, propiedad.

**Argumentos:** Admite dos tipos de formularios de atribución como cadenas, o tipos como <xref:System.Type> . Vea <xref:System.Windows.Markup.XamlDeferLoadAttribute>.

Indica que una clase o propiedad usa la carga aplazada para XAML (como el comportamiento de una plantilla) e informa de la clase que habilita el comportamiento de carga aplazada así como el tipo de contenido/destino.

### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>

**Se aplica a:** Las

**Argumentos:** Asigna un nombre a la devolución de llamada.

Indica que una clase puede utilizar una extensión de marcado para proporcionar un valor para una o varias de sus propiedades y hace referencia a un controlador que un escritor de XAML debe llamar antes de realizar una operación de establecimiento de extensión de marcado en cualquier propiedad de la clase.

### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>

**Se aplica a:** Las

**Argumentos:** Asigna un nombre a la devolución de llamada.

Indica que una clase puede utilizar un convertidor de tipos para proporcionar un valor para una o varias de sus propiedades y hace referencia a un controlador que un escritor de XAML debe llamar antes de realizar una operación de conjunto de convertidores de tipos en cualquier propiedad de la clase.

### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>

**Se aplica a:** Las

**Argumentos:** Cadena que especifica el nombre de la propiedad a la que se va a asignar `xml:lang` el alias en el tipo con atributos.

<xref:System.Windows.Markup.XmlLangPropertyAttribute> notifica una propiedad del tipo con atributos que se asigna a la `lang` directiva XML. La propiedad no tiene por qué ser de tipo <xref:System.String> , pero debe poder asignarse desde una cadena (la asignación se puede realizar asociando un convertidor de tipos al tipo de la propiedad o con la propiedad específica). La propiedad debe ser de lectura/escritura.

El escenario de asignación `xml:lang` es para que un modelo de objetos de tiempo de ejecución tenga acceso a la información de lenguaje especificada por XML sin procesarlo específicamente con un XMLDOM.

La definición hereda a todos los tipos derivados que se pueden asignar al tipo de definición. Puede invalidar la definición en un tipo derivado específico aplicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> en el tipo derivado específico, aunque es un escenario poco frecuente.

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>Atributos de CLR relacionados con XAML en el nivel de ensamblado

En las secciones siguientes se describen los atributos relacionados con XAML que no se aplican a los tipos o definiciones de miembros, sino que se aplican a los ensamblados. Estos atributos son pertinentes para el objetivo general de definir una biblioteca que contenga los tipos personalizados que se van a usar en XAML. Algunos de los atributos no influyen necesariamente directamente en el flujo de nodo XAML, sino que se pasan en el flujo de nodo para que los usen otros consumidores. Los consumidores de la información incluyen entornos de diseño o procesos de serialización que necesitan información de espacio de nombres XAML e información de prefijos asociada. Un contexto de esquema XAML (incluido el valor predeterminado de los servicios XAML de .NET) también usa esta información.

### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

**Argumentos:**

- Cadena que especifica el identificador del espacio de nombres XAML que se va a abarcar.

- Una cadena que especifica el identificador del espacio de nombres XAML que puede abarcar el espacio de nombres XAML del argumento anterior.

  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> Especifica que otro espacio de nombres XAML puede incluir un espacio de nombres XAML. Normalmente, el espacio de nombres XAML que realiza la inclusión se indica en un objeto <xref:System.Windows.Markup.XmlnsDefinitionAttribute> definido anteriormente. Esta técnica se puede usar para el control de versiones de un vocabulario XAML en una biblioteca y para que sea compatible con el marcado previamente definido en el vocabulario con versiones anteriores.

### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

**Argumentos:**

- Cadena que especifica el identificador del espacio de nombres XAML que se va a definir.

- Una cadena que asigna un nombre a un espacio de nombres CLR. El espacio de nombres CLR debe definir tipos públicos en el ensamblado y, al menos, uno de los tipos de espacio de nombres CLR debe estar pensado para el uso de XAML.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute> especifica una asignación por cada ensamblado entre un espacio de nombres XAML y un espacio de nombres CLR, que un escritor de objetos XAML o un contexto de esquema XAML usan para la resolución de tipos.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>Se puede aplicar más de una a un ensamblado. Esto puede hacerse por cualquier combinación de las siguientes razones:

- El diseño de la biblioteca contiene varios espacios de nombres CLR para la organización lógica del acceso de API en tiempo de ejecución. sin embargo, desea que todos los tipos de esos espacios de nombres puedan usarse en XAML haciendo referencia al mismo espacio de nombres XAML. En este caso, se aplican varios <xref:System.Windows.Markup.XmlnsDefinitionAttribute> atributos con el mismo <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> valor pero con <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> valores distintos. Esto es especialmente útil si está definiendo asignaciones para el espacio de nombres XAML que el marco o la aplicación pretende que sea el espacio de nombres XAML predeterminado en el uso común.

- El diseño de la biblioteca contiene varios espacios de nombres CLR y desea una separación deliberada del espacio de nombres XAML entre los usos de los tipos de esos espacios de nombres CLR.

- Se define un espacio de nombres CLR en el ensamblado y se desea que sea accesible a través de más de un espacio de nombres XAML. Este escenario se produce cuando se admiten varios vocabularios con el mismo código base.

- La compatibilidad con el lenguaje XAML se define en uno o varios espacios de nombres CLR. En este caso, el <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> valor debe ser `http://schemas.microsoft.com/winfx/2006/xaml` .

### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute

**Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>

**Argumentos:**

- Cadena que especifica el identificador de un espacio de nombres XAML.

- Cadena que especifica un prefijo recomendado.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute> especifica un prefijo recomendado que se va a usar para un espacio de nombres XAML. El prefijo es útil cuando se escriben elementos y atributos en un archivo XAML serializado por los servicios XAML de .NET <xref:System.Xaml.XamlXmlWriter> o cuando una biblioteca de implementación de XAML interactúa con un entorno de diseño que tiene características de edición de XAML.

  <xref:System.Windows.Markup.XmlnsPrefixAttribute>Se puede aplicar más de una a un ensamblado. Esto puede hacerse por cualquier combinación de las siguientes razones:

- El ensamblado define tipos para más de un espacio de nombres XAML. En este caso, defina diferentes valores de prefijo para cada espacio de nombres XAML.

- Se admiten varios vocabularios y se usan prefijos diferentes para cada vocabulario y espacio de nombres XAML.

- Puede definir la compatibilidad del lenguaje XAML en el ensamblado y tener un <xref:System.Windows.Markup.XmlnsDefinitionAttribute> para `http://schemas.microsoft.com/winfx/2006/xaml` . En este caso, normalmente debe promover el prefijo `x` .

> [!NOTE]
> Los servicios XAML de .NET también definen el atributo relacionado con XAML <xref:System.Windows.Markup.RootNamespaceAttribute> . Este atributo es un atributo de nivel de ensamblado para la compatibilidad del sistema del proyecto y no es relevante para los tipos personalizados de XAML.

## <a name="see-also"></a>Vea también

- <xref:System.Attribute>
- [Definición de tipos personalizados para usarlos con los servicios XAML de .NET](define-custom-types.md)
