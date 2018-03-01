---
title: Atributos de CLR relacionados con XAML para los tipos y bibliotecas personalizados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
caps.latest.revision: 
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 25aac1d4478279561cbcdda6c1cf912c3c3b2cde
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>Atributos de CLR relacionados con XAML para los tipos y bibliotecas personalizados
En este tema se describe los atributos de runtime (CLR) de lenguaje común que se definen por los servicios XAML de .NET Framework. También se describen otros atributos CLR que se definen en .NET Framework que tienen un escenario de aplicación a los ensamblados o tipos relacionados con XAML. Atribución de ensamblados, tipos o miembros con estos atributos CLR proporciona información de sistema de tipos XAML relacionada con los tipos. Se proporciona información a cualquier consumidor XAML que usa los servicios XAML de .NET Framework para procesar el flujo de nodo XAML directamente o a través de los lectores dedicados de XAML y escritores de XAML.  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>Atributos CLR relacionados con XAML para los tipos personalizados y los miembros personalizados  
 Uso de atributos CLR implica que está utilizando el CLR general para definir sus tipos, en caso contrario, estos atributos no están disponibles. Si utiliza el CLR para definir el tipo de copia, el contexto de esquema XAML predeterminado utilizado por los escritores de servicios XAML de .NET Framework puede leer la atribución de CLR a través de reflexión en realizar una copia de los ensamblados.  
  
 En las siguientes secciones se describen los atributos relacionados con XAML que se pueden aplicar a los tipos o miembros personalizados. Cada atributo CLR comunica la información que es relevante para un sistema de tipos XAML. En la ruta de acceso de carga, la información con atributos ayuda ya sea el lector de XAML a formar un flujo de nodo XAML válido o ayuda al escritor de XAML generar un gráfico de objeto válido. En la operación de guardar ruta de acceso, la información con atributos ayuda al lector de XAML formar un flujo de nodo XAML válido que reconstituye la información del sistema de tipos XAML; o declara sugerencias de serialización o requisitos para el escritor de XAML u otros consumidores XAML.  
  
### <a name="ambientattribute"></a>AmbientAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **Se aplica a:** (clase), propiedad, o `get` los miembros de descriptor de acceso que admiten propiedades adjuntables.  
  
 **Argumentos:** ninguno  
  
 <xref:System.Windows.Markup.AmbientAttribute>indica que la propiedad, o todas las propiedades que toman el tipo con atributos, se deben interpretar bajo el concepto de propiedad de ambiente en XAML. El concepto de ambiente se relaciona con la forma en que los procesadores XAML determinan los propietarios de tipos de los miembros. Una propiedad de ambiente es una propiedad donde se espera que el valor esté disponible en el contexto del analizador al crear un gráfico de objetos, pero donde se suspende la búsqueda típica de miembro de tipo para el nodo XAML inmediato establecido que se está creando.  
  
 El concepto de ambiente se puede aplicar a los miembros adjuntables, que no se representan como propiedades en cuanto a cómo la atribución de CLR define <xref:System.AttributeTargets>. El uso de la atribución de método debe aplicarse únicamente en el caso de un `get` descriptor de acceso que admite el uso adjuntable para XAML.  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **Se aplica a:** (clase)  
  
 **Argumentos:** una cadena que especifica el nombre de la propiedad que coincide con un argumento de constructor único.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute>Especifica que un objeto se puede inicializar con una sintaxis de constructor no predeterminado y que una propiedad del nombre especificado proporciona información de construcción. Esta información sirve principalmente para la serialización XAML. Para obtener más información, consulta <xref:System.Windows.Markup.ConstructorArgumentAttribute>.  
  
### <a name="contentpropertyattribute"></a>ContentPropertyAttribute válido  
 **Documentación de referencia:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **Se aplica a:** (clase)  
  
 **Argumentos:** una cadena que especifica el nombre de un miembro del tipo con atributos.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute>indica que la propiedad denominada por el argumento debe actuar como la propiedad de contenido XAML para ese tipo. La definición de propiedad de contenido XAML hereda a todos los tipos derivados que se pueden asignables al tipo de definición. Puede reemplazar la definición en un tipo derivado concreto aplicando <xref:System.Windows.Markup.ContentPropertyAttribute> en específico del tipo derivado.  
  
 Para la propiedad que actúa como la propiedad de contenido de XAML, se puede omitir etiquetado para la propiedad de elemento de propiedad en el uso XAML. Normalmente, se designan propiedades de contenido de XAML que promueven un marcado XAML simplificado para los modelos de contención y contenido. Dado que un único miembro se puede designar como la propiedad de contenido de XAML, a veces tiene las opciones de diseño para realizar respecto a qué contenedor varias propiedades de un tipo deben designarse como la propiedad de contenido XAML. Las propiedades del contenedor deben utilizarse con elementos de propiedad explícitos.  
  
 En el flujo de nodo XAML, propiedades de contenido XAML producen `StartMember` y `EndMember` nodos, con el nombre de la propiedad para el <xref:System.Xaml.XamlMember>. Para determinar si un miembro es la propiedad de contenido XAML, examine la <xref:System.Xaml.XamlType> valor de la `StartObject` colocar y obtener el valor de <xref:System.Xaml.XamlType.ContentProperty%2A>.  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **Se aplica a:** (clase), específicamente los tipos de colección.  
  
 **Argumentos:** A <xref:System.Type> que especifica el tipo que se usará como el tipo de contenedor de contenido para contenido externo.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute>Especifica uno o varios tipos en el tipo de colección asociado que se usará para encapsular el contenido externo. Contenido externo hace referencia a los casos donde las restricciones de sistema de tipos en el tipo de la propiedad de contenido no capturan todos los posibles casos de contenido que fuera compatible con el uso de XAML para el tipo de propiedad. Por ejemplo, de soporte de XAML para el contenido de un tipo determinado podría admitir cadenas en un tipo genérico fuertemente tipado <xref:System.Collections.ObjectModel.Collection%601>. Los contenedores de contenido son útiles para migrar las convenciones de marcado preexistentes en el concepto de XAML de valores asignables para las colecciones, como la migración de los modelos de contenido relacionados con el texto.  
  
 Para especificar más de un tipo de contenedor de contenido, aplique el atributo varias veces.  
  
### <a name="dependsonattribute"></a>DependsOnAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **Se aplica a:** propiedad  
  
 **Argumentos:** una cadena que especifica el nombre de otro miembro del tipo con atributos.  
  
 <xref:System.Windows.Markup.DependsOnAttribute>indica que la propiedad con atributos depende del valor de otra propiedad. Este atributo se aplica a una definición de propiedad garantiza que las propiedades dependientes se procesan primero en la escritura de objeto XAML. Usos de <xref:System.Windows.Markup.DependsOnAttribute> especifican los casos excepcionales de propiedades en tipos donde se debe seguir un orden concreto de análisis para la creación de objeto válido.  
  
 Puede aplicar varias <xref:System.Windows.Markup.DependsOnAttribute> casos para una definición de propiedad.  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **Se aplica a:** (clase), que se espera que sea un <xref:System.Windows.Markup.MarkupExtension> tipo derivado.  
  
 **Argumentos:** A <xref:System.Type> que especifica el tipo más preciso para esperar la `ProvideValue` resultado de los atributos <xref:System.Windows.Markup.MarkupExtension>.  
  
 Para obtener más información, consulte [extensiones de marcado para XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **Se aplica a:** (clase)  
  
 **Argumentos:** admite dos formas de atribución:  
  
-   Una cadena que especifica el nombre de una propiedad en el tipo con atributos.  
  
-   Una cadena que especifica el nombre de una propiedad y un <xref:System.Type> para el tipo que define la propiedad con nombre. Esta forma sirve para especificar a un miembro adjuntable como la propiedad de ámbito de nombres XAML.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute>Especifica una propiedad que proporciona el valor de ámbito de nombres XAML para la clase con atributos. Se espera la propiedad de ámbito de nombres XAML que hacen referencia a un objeto que implementa <xref:System.Windows.Markup.INameScope> y contiene el ámbito de nombres XAML real, su almacén y su comportamiento.  
  
### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **Se aplica a:** (clase)  
  
 **Argumentos:** una cadena que especifica el nombre de la propiedad name de tiempo de ejecución en el tipo con atributos.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>notifica una propiedad del tipo con atributos que se asigna al XAML [Directiva x: Name](../../../docs/framework/xaml-services/x-name-directive.md). La propiedad debe ser de tipo <xref:System.String> y debe ser de lectura/escritura.  
  
 La definición hereda a todos los tipos derivados que se pueden asignables al tipo de definición. Puede reemplazar la definición en un tipo derivado concreto aplicando <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> en específico del tipo derivado.  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **Se aplica a:** tipos  
  
 **Argumentos:** ninguno.  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>se aplica a tipos específicos que pueden aparecer como elementos secundarios en el contenido de un espacio en blanco significativo (contenido mantenidos por una colección que tiene <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>es principalmente relevante para la operación de guardar ruta de acceso, pero está disponible en el sistema de tipos XAML en la ruta de acceso de carga mediante el examen de <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>. Para obtener más información, consulte [procesamiento de espacios en blanco en XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **Documentación de referencia:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **Se aplica a:** (clase), propiedad, método (el único caso de método válido de XAML es un `get` descriptor de acceso que es compatible con un miembro adjuntable).  
  
 **Argumentos:** el <xref:System.Type> de la <xref:System.ComponentModel.TypeConverter>.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>en un XAML contexto hace referencia a una personalizada <xref:System.ComponentModel.TypeConverter>. Esto <xref:System.ComponentModel.TypeConverter> proporciona el comportamiento de conversión de tipos para tipos personalizados o los miembros de ese tipo.  
  
 Aplicar el <xref:System.ComponentModel.TypeConverterAttribute> a su tipo, que hacen referencia a la implementación de convertidor de tipos de atributo. Puede definir los convertidores de tipos para XAML en las clases, estructuras o interfaces. No es necesario proporcionar la conversión de tipo para las enumeraciones, que la conversión está habilitada de forma nativa.  
  
 El convertidor de tipos debe ser capaz de convertir una cadena que se usa para atributos o texto de inicialización del marcado, en el tipo de destino previsto. Para obtener más información, consulte [clases TypeConverter y XAML](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
 En lugar de aplicar a todos los valores de un tipo, un comportamiento del convertidor de tipos para XAML también se puede establecer en una propiedad concreta. En este caso, aplicar <xref:System.ComponentModel.TypeConverterAttribute> a la definición de propiedad (la definición externa, no específico del `get` y `set` definiciones).  
  
 Un comportamiento del convertidor de tipos para el uso XAML de un miembro adjuntable personalizado puede asignarse aplicando <xref:System.ComponentModel.TypeConverterAttribute> a la `get` descriptor de acceso de método que admite el uso de XAML.  
  
 Similar a <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> existía en .NET Framework anteriores a la existencia de XAML y el modelo del convertidor de tipos servía para otros propósitos. Para hacer referencia y utilizar <xref:System.ComponentModel.TypeConverterAttribute>, debe calificarlo totalmente o proporcionar un `using` instrucción para <xref:System.ComponentModel>. También debe incluir el ensamblado del sistema en el proyecto.  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **Se aplica a:** (clase)  
  
 **Argumentos:** una cadena que hace referencia a la propiedad correspondiente por su nombre.  
  
 Indica la propiedad CLR de una clase que crea alias el [x: Uid (directiva)](../../../docs/framework/xaml-services/x-uid-directive.md).  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **Se aplica a:** (clase)  
  
 **Argumentos:** un valor booleano. Si se usa para la finalidad prevista del atributo, esto siempre se debe especificar como `true`.  
  
 Indica si este tipo se compila de arriba a abajo durante la creación de gráficos de objetos XAML. Se trata de un concepto avanzado, que está probablemente estrechamente relacionado con la definición de su modelo de programación. Para obtener más información, consulta <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **Se aplica a:** (clase), propiedad, método (el único caso de método válido de XAML es un `get` descriptor de acceso que es compatible con un miembro adjuntable).  
  
 **Argumentos:** A <xref:System.Type> que especifica la clase de compatibilidad de serializador de valor que se utilizará al serializar todas las propiedades del tipo con atributos o específico del atributo de propiedad.  
  
 <xref:System.Windows.Markup.ValueSerializer>Especifica una clase de serialización de valor que requiere más estado y contexto que un <xref:System.ComponentModel.TypeConverter> does. <xref:System.Windows.Markup.ValueSerializer>se puede asociar con un miembro adjuntable aplicando el <xref:System.Windows.Markup.ValueSerializerAttribute> atributo en el método estático `get` método de descriptor de acceso para el miembro adjuntable. Serialización de valor también es aplicable para enumeraciones, interfaces y estructuras, pero no para los delegados.  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **Se aplica a:** (clase), específicamente los tipos de colección que se esperan para hospedar contenido mixto, donde el espacio en blanco alrededor de los elementos de objeto puede ser significativo para la representación de la interfaz de usuario.  
  
 **Argumentos:** ninguno.  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>indica que un procesador XAML, lo que influye en la construcción de nodos de valor del flujo de nodo XAML dentro de la colección debe procesar un tipo de colección como espacio en blanco significativo. Para obtener más información, consulte [procesamiento de espacios en blanco en XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **Se aplica a:** propiedad de clase.  
  
 **Argumentos:** atribución admite dos formularios tipos como cadenas o tipos como <xref:System.Type>. Vea <xref:System.Windows.Markup.XamlDeferLoadAttribute>.  
  
 Indica que una clase o propiedad tiene un uso de la carga aplazada para XAML (por ejemplo, el comportamiento de una plantilla) y notifica la clase que habilita el comportamiento aplazar y su tipo de contenido/destino.  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **Se aplica a:** (clase)  
  
 **Argumentos:** nombres de la devolución de llamada.  
  
 Indica que una clase puede utilizar una extensión de marcado para proporcionar un valor para uno o más de sus propiedades y hace referencia a un controlador al que un escritor de XAML debe llamar antes de realizar una operación de establecimiento de extensión de marcado en cualquier propiedad de la clase.  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **Se aplica a:** (clase)  
  
 **Argumentos:** nombres de la devolución de llamada.  
  
 Indica que una clase puede utilizar un convertidor de tipos para proporcionar un valor para uno o más de sus propiedades y hace referencia a un controlador al que un escritor de XAML debe llamar antes de realizar una operación de conjunto de convertidor de tipos en cualquier propiedad de la clase.  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **Se aplica a:** (clase)  
  
 **Argumentos:** una cadena que especifica el nombre de la propiedad de alias para `xml:lang` en el tipo con atributos.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute>notifica una propiedad del tipo con atributos que se asigna al XML `lang` directiva. La propiedad no es necesariamente de tipo <xref:System.String>, pero se debe poder asignar desde una cadena (Esto puede realizarse mediante la asociación de un convertidor de tipos con el tipo de propiedad, o con la propiedad específica). La propiedad debe ser de lectura/escritura.  
  
 El escenario de asignación `xml:lang` es para que un modelo de objetos en tiempo de ejecución tiene acceso a información del idioma especificado por el XML sin tener que procesar específicamente con un XMLDOM.  
  
 La definición hereda a todos los tipos derivados que se pueden asignables al tipo de definición. Puede reemplazar la definición en un tipo derivado concreto aplicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> en específico del tipo derivado, aunque es un escenario poco común.  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>Atributos CLR relacionados con XAML en el nivel de ensamblado  
 Las siguientes secciones describen los atributos relacionados con XAML que no se aplican a tipos o definiciones de miembros, pero en su lugar, se aplican a los ensamblados. Estos atributos son pertinentes para el objetivo global de definir una biblioteca que contiene los tipos personalizados para utilizar en XAML. Algunos de los atributos no necesariamente influyen en el flujo de nodo XAML directamente, sino que se pasan en el flujo de nodo para otros consumidores de usar. Los consumidores para ver la información incluyen los entornos de diseño o procesos de serialización que necesitan información del espacio de nombres XAML y la información de prefijo asociada. Un contexto de esquema XAML (incluida la predeterminada de servicios XAML de .NET Framework) también usa esta información.  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **Argumentos:**  
  
-   Una cadena que especifica el identificador del espacio de nombres XAML para agregar.  
  
-   Una cadena que especifica el identificador del espacio de nombres XAML que puede agregar el espacio de nombres XAML del argumento anterior.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>Especifica que otro espacio de nombres XAML puede incluir un espacio de nombres XAML. Normalmente, se indica el espacio de nombres XAML integrador en definida previamente <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Esta técnica puede ser utilizado para las versiones de un vocabulario XAML en una biblioteca y para que sea compatible con marcado definido previamente en el vocabulario con control de versiones anterior.  
  
### <a name="xmlnsdefinitionattribute"></a>Atributo XmlnsDefinitionAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **Argumentos:**  
  
-   Una cadena que especifica el identificador del espacio de nombres XAML para definir.  
  
-   Una cadena que designa un espacio de nombres CLR. El espacio de nombres CLR debe definir los tipos públicos en el ensamblado y al menos uno de los tipos del espacio de nombres CLR debe ser destinado al uso XAML.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>Especifica una asignación por cada ensamblado entre un espacio de nombres XAML y un espacio de nombres CLR, que se usa para la resolución de tipo de un escritor de objetos XAML o un contexto de esquema XAML.  
  
 Más de un <xref:System.Windows.Markup.XmlnsDefinitionAttribute> pueden aplicarse a un ensamblado. Esto puede hacerse para cualquier combinación de los siguientes motivos:  
  
-   El diseño de la biblioteca contiene varios espacios de nombres CLR para la organización lógica de acceso de la API de tiempo de ejecución; Sin embargo, desea que todos los tipos en los espacios de nombres se puedan utilizar XAML haciendo referencia al mismo espacio de nombres XAML. En este caso, aplicar varias <xref:System.Windows.Markup.XmlnsDefinitionAttribute> atributos con el mismo <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> valor pero distintos <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> valores. Esto es especialmente útil si va a definir las asignaciones para el espacio de nombres XAML que el marco de trabajo o la aplicación pretende ser el espacio de nombres XAML predeterminado de uso común.  
  
-   El diseño de la biblioteca contiene varios espacios de nombres CLR y desea una separación de espacio de nombres XAML deliberada entre los usos de tipos en los espacios de nombres CLR.  
  
-   Definir un espacio de nombres CLR en el ensamblado, y desea que sea accesible a través de más de un espacio de nombres XAML. Este escenario se produce cuando va a admitir varios vocabularios con el mismo código base.  
  
-   Definir la compatibilidad del lenguaje XAML en uno o varios espacios de nombres CLR. En estos casos, el <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> valor debe ser `http://schemas.microsoft.com/winfx/2006/xaml`.  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **Documentación de referencia:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **Argumentos:**  
  
-   Una cadena que especifica el identificador de un espacio de nombres XAML.  
  
-   Una cadena que especifica un prefijo recomendado.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>Especifica un prefijo recomendado para usar un espacio de nombres XAML. El prefijo es útil al escribir elementos y atributos en un archivo XAML que se serializó con los servicios XAML de .NET Framework <xref:System.Xaml.XamlXmlWriter>, o cuando una biblioteca de implementación de XAML interactúa con un entorno de diseño que tiene XAML características de edición.  
  
 Más de un <xref:System.Windows.Markup.XmlnsPrefixAttribute> pueden aplicarse a un ensamblado. Esto puede hacerse para cualquier combinación de los siguientes motivos:  
  
-   El ensamblado define los tipos para más de un espacio de nombres XAML. En este caso debe definir valores de prefijo diferente para cada espacio de nombres XAML.  
  
-   Son compatibles con varios vocabularios y utiliza prefijos diferentes para cada vocabulario y el espacio de nombres XAML.  
  
-   Definir la compatibilidad del lenguaje XAML en el ensamblado y tienen un <xref:System.Windows.Markup.XmlnsDefinitionAttribute> para `http://schemas.microsoft.com/winfx/2006/xaml`. En este caso, normalmente debe promover el prefijo `x`.  
  
> [!NOTE]
>  Servicios XAML de .NET framework define también los atributos relacionados con XAML <xref:System.Windows.Markup.RootNamespaceAttribute>. Este atributo es un atributo de nivel de ensamblado para la compatibilidad con el sistema de proyecto, y no es relevante para los tipos personalizados de XAML.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Attribute>  
 [Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)
