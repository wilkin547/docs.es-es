---
title: "XAML Namespaces for .NET Framework XAML Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
caps.latest.revision: 3
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 3
---
# XAML Namespaces for .NET Framework XAML Services
Un espacio de nombres XAML es un concepto que amplía la definición de un espacio de nombres XML.  Similar a un espacio de nombres XML, puede definir un espacio de nombres XAML mediante un atributo `xmlns` en el marcado.  Los espacios de nombres XAML también se representan en el flujo de nodo XAML y otras API de servicios XAML.  En este tema se define el concepto de espacio de nombres XAML, y se describe cómo se pueden definir los espacios de nombres XAML y cómo los usan los contextos de esquema XAML, además de otros aspectos de los servicios XAML de .NET Framework.  
  
## Espacio de nombres XML y espacio de nombres XAML  
 Un espacio de nombres XAML es un espacio de nombres XML especializado, básicamente porque el XAML es una forma de XML y utiliza el formato básico de XML para el marcado.  En el marcado, se declara un espacio de nombres XAML y su asignación con un atributo `xmlns` que se aplica a un elemento.  La declaración de `xmlns` se puede hacer para el mismo elemento en el que se declara el espacio de nombres XAML.  Una declaración de espacio de nombres XAML realizada en un elemento es válida para ese elemento, todos los atributos de ese elemento y todos los elementos secundarios de ese elemento.  Los atributos pueden utilizar un espacio de nombres XAML que no sea igual que el elemento que contiene el atributo, siempre y cuando el nombre de atributo haga referencia por sí mismo al prefijo como parte del nombre del atributo en el marcado.  
  
 Lo que diferencia un espacio de nombres XAML y un espacio de nombres XML es que un espacio de nombres XML se podría utilizar para hacer referencia a un esquema, o se puede utilizar simplemente para distinguir entidades.  Para XAML, los tipos y miembros tal como se usan en XAML deben ser resueltos en última instancia en tipos de respaldo, y los conceptos de esquema XML no se aplican bien a esta capacidad.  El espacio de nombres XAML contiene información que el contexto de esquema XAML debe tener disponible para realizar esta asignación de tipos.  
  
## Componentes del espacio de nombres XAML  
 La definición de espacio de nombres XAML tiene dos componentes: un prefijo y un identificador.  Cada uno de estos componentes está presente cuando se declara un espacio de nombres XAML en el marcado, o bien está definido en el sistema de tipos XAML.  
  
 El prefijo puede ser cualquier cadena permitida por la [especificación W3C Namespaces in XML 1.0](http://go.microsoft.com/fwlink/?LinkID=161735).  Por convención, los prefijos suelen ser cadenas muy cortas, porque el prefijo se repite varias veces en un archivo de marcado típico.  Algunos espacios de nombres XAML que están pensados para usarse en varias implementaciones de XAML utilizan prefijos convencionales específicos.  Por ejemplo, el espacio de nombres XAML del lenguaje XAML se suele asignar mediante el prefijo `x`.  Puede definir un espacio de nombres XAML predeterminado cuando el prefijo no se proporcione en la definición pero se represente como una cadena vacía si se define o consulta desde la API de los servicios XAML de .NET Framework.  Normalmente, una tecnología que implemente XAML y sus escenarios y vocabularios elige deliberadamente el espacio de nombres XAML predeterminado para promover la cantidad máxima de marcado que omita el prefijo.  
  
 El identificador puede ser cualquier cadena permitida por la [especificación W3C Namespaces in XML 1.0](http://go.microsoft.com/fwlink/?LinkID=161735).  Por convención, los identificadores de los espacios de nombres XML o XAML se proporcionan a menudo en forma de URI, normalmente como un URI absoluto calificado por protocolo.  Con frecuencia, la información de versión que define un vocabulario XAML determinado está implícito como parte de la cadena de la ruta de acceso.  Los espacios de nombres XAML agregan una convención adicional de identificador más allá de convención de URI XML.  Para los espacios de nombres XAML, el identificador comunica la información que necesita un contexto de esquema XAML para resolver los tipos que se especifican como elementos en ese espacio de nombres XAML, o para resolver los atributos en miembros.  
  
 A efectos de comunicar información para un contexto de esquema XAML, el identificador de un espacio de nombres XAML puede hallarse aún en forma de URI.  Sin embargo, en este caso, el URI también se declara como identificador coincidente en un ensamblado o lista de ensamblados concretos.  Esto se hace en los ensamblados mediante la atribución del ensamblado con <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.  Este método para identificar el espacio de nombres XAML y admitir un comportamiento de resolución de tipos basado en CLR en el ensamblado con atributos es compatible con el contexto de esquema XAML predeterminado en los servicios XAML de .NET Framework.  De forma más general, esta convención se puede usar en los casos en que el contexto de esquema XAML incorpore CLR o se base en el contexto de esquema XAML predeterminado, que es necesario para leer los atributos de CLR en los ensamblados de CLR.  
  
 Los espacios de nombres XAML también se pueden identificar mediante una convención que comunique un espacio de nombres CLR y un ensamblado de definición de tipos.  Esta convención se usa en caso de que no exista ninguna atribución de <xref:System.Windows.Markup.XmlnsDefinitionAttribute> en los ensamblados que contienen tipos.  Esta convención es potencialmente más compleja que la convención de URI y también tiene un potencial de ambigüedad y duplicación, porque hay varias maneras de hacer referencia a un ensamblado.  
  
 El formato más básico para un identificador que utilice la convención de espacio de nombres y ensamblado de CLR es el siguiente:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:` y `; assembly=` son componentes literales de la sintaxis.  
  
 *clrnsName* es el nombre de cadena que identifica un espacio de nombres CLR.  Este nombre de cadena incluye cualquier carácter de punto interno \(.\) que proporcione sugerencias sobre el espacio de nombres CLR y su relación con otros espacios de nombres CLR.  
  
 *assemblyShortName* es el nombre de cadena de un ensamblado que define los tipos que son útiles en XAML.  Los tipos a los que se va a tener acceso a través del espacio de nombres XAML declarado se espera que sean definidos por el ensamblado y que se declaren específicamente dentro del espacio de nombres CLR especificado por *clrnsName*.  Este nombre de cadena normalmente es semejante a la información que notifica <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=fullName>.  
  
 A continuación se ofrece una definición más completa de la convención de espacio de nombres y ensamblado de CLR:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyName*  
  
 *assemblyName* representa cualquier cadena válida como entrada de <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>.  Esta cadena puede incluir la referencia cultural, la clave pública o información de versión \(las definiciones de estos conceptos se encuentran en el tema de referencia de <xref:System.Reflection.Assembly>\).  El formato y la prueba COFF \(que se utiliza en otras sobrecargas de <xref:System.Reflection.Assembly.Load%2A>\) no son pertinentes para la carga de ensamblados de XAML; toda la información de carga debe presentarse como una cadena.  
  
 Especificar una clave pública para el ensamblado es una técnica útil para la seguridad de XAML, o también para eliminar las posibles ambigüedades si los ensamblados se cargan solo por su nombre o preexisten en un dominio de aplicación o caché.  Para obtener más información, vea [XAML Security Considerations](../../../docs/framework/xaml-services/xaml-security-considerations.md).  
  
## Declaraciones de espacio de nombres XAML en la API de servicios XAML  
 En la API de servicios XAML, una declaración de espacio de nombres XAML se representa mediante un objeto <xref:System.Xaml.NamespaceDeclaration>.  Si se declara un espacio de nombres XAML en el código, se llama al constructor <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29>.  Los parámetros `ns` y `prefix` se especifican como cadenas, y la entrada que se va a proporcionar para estos parámetros corresponde a la definición del identificador del espacio de nombres XAML y el prefijo de espacio de nombres XAML proporcionados previamente en este tema.  
  
 Si se examina la información de espacio de nombres XAML como parte de un flujo de nodo XAML o con el otro acceso al sistema de tipos XAML, <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=fullName> notifica el identificador del espacio de nombres XAML y <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=fullName> notifica el prefijo de espacio de nombres XAML.  
  
 En un flujo de nodo XAML, la información de espacio de nombres XAML puede aparecer como nodo XAML antepuesto a la entidad a la que se aplica.  Esto incluye los casos en los que la información de espacio de nombres XAML precede al `StartObject` del elemento raíz XAML.  Para obtener más información, vea [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
 En muchos escenarios que utilizan la API de los servicios XAML de .NET Framework se espera que por lo menos exista una declaración de espacio de nombres XAML, y la declaración debe contener o hacer referencia a la información necesaria para un contexto de esquema XAML.  Los espacios de nombres XAML deben especificar los ensamblados que se van a cargar, o ayudar a resolver los tipos específicos de los espacios de nombres y los ensamblados que ya están cargados o ya reconoce el contexto de esquema XAML.  
  
 Para generar un flujo de nodo XAML, la información de tipo XAML debe estar disponible, a través del contexto de esquema XAML.  La información de tipos XAML no se puede determinar sin determinar antes el espacio de nombres XAML pertinente para cada nodo que se va a crear.  En este punto, todavía no se crean instancias de tipos, pero el contexto de esquema XAML puede necesitar buscar información en el ensamblado de definición y el tipo de respaldo.  Por ejemplo, para procesar el marcado `<Party><PartyFavor/></Party>`, el contexto de esquema XAML debe poder determinar el nombre y el tipo de `ContentProperty` de `Party`, y también debe conocer la información de espacio de nombres XAML para `Party` y `PartyFavor`.  En el caso del contexto de esquema XAML predeterminado, la reflexión estática proporciona gran parte de la información del sistema de tipos XAML necesaria para generar los nodos de tipos XAML en el flujo de nodo.  
  
 Para generar un gráfico de objeto a partir de un flujo de nodo XAML, debe haber declaraciones de espacio de nombres XAML para cada prefijo XAML utilizado en el marcado original y registrado en el flujo de nodo XAML.  En este punto, se están creando instancias y se produce el comportamiento real de asignación de tipos.  
  
 Si necesita rellenar de antemano la información del espacio de nombres XAML, en caso de que el espacio de nombres XAML que tiene pensado que use el contexto de esquema XAML no esté definido en el marcado, una posible técnica es declarar las declaraciones de espacio de nombres XML de <xref:System.Xml.XmlParserContext> para <xref:System.Xml.XmlReader>.  A continuación, utilice ese <xref:System.Xml.XmlReader> como entrada para un constructor de lector de XAML o <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=fullName>.  
  
 Otras dos API que son pertinentes para el control del espacio de nombres XAML en los servicios XAML de .NET Framework son los atributos <xref:System.Windows.Markup.XmlnsDefinitionAttribute> y <xref:System.Windows.Markup.XmlnsPrefixAttribute>.  Estos atributos se aplican a los ensamblados.  <xref:System.Windows.Markup.XmlnsDefinitionAttribute> se utiliza en un contexto de esquema XAML para interpretar cualquier declaración de espacio de nombres XAML que incluya un URI.  Las herramientas que emiten XAML usan <xref:System.Windows.Markup.XmlnsPrefixAttribute> de modo que un espacio de nombres XAML determinado pueda serializarse con un prefijo predecible.  Para obtener más información, vea [XAML\-Related CLR Attributes for Custom Types and Libraries](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## Vea también  
 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)