---
title: Espacios de nombres XAML para los servicios XAML de .NET Framework
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 11bf5d112c64fb0b942decf7635f02b90a98bdeb
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837173"
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>Espacios de nombres XAML para los servicios XAML de .NET Framework
Un espacio de nombres XAML es un concepto que se expande en la definición de un espacio de nombres XML. De forma similar a un espacio de nombres XML, puede definir un espacio de nombres XAML mediante un atributo `xmlns` en el marcado. Los espacios de nombres XAML también se representan en el flujo de nodo XAML y en otras API de servicios XAML. En este tema se define el concepto de espacio de nombres XAML y se describe cómo se pueden definir y usar los contextos de esquema XAML y otros aspectos de .NET Framework servicios XAML.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>Espacio de nombres XML y espacio de nombres XAML  
 Un espacio de nombres XAML es un espacio de nombres XML especializado, al igual que XAML es una forma especializada de XML y utiliza el formulario XML básico para su marcado. En el marcado, se declara un espacio de nombres XAML y su asignación a través de un `xmlns` atributo aplicado a un elemento. La declaración de `xmlns` se puede realizar en el mismo elemento en el que se declara el espacio de nombres XAML. Una declaración de espacio de nombres XAML realizada en un elemento es válida para ese elemento, todos los atributos de ese elemento y todos los elementos secundarios de ese elemento. Los atributos pueden usar espacios de nombres XAML que no son iguales que el elemento que contiene el atributo, siempre que el propio nombre de atributo haga referencia al prefijo como parte del nombre del atributo en el marcado.  
  
 La distinción entre un espacio de nombres XAML y un espacio de nombres XML es que se podría usar un espacio de nombres XML para hacer referencia a un esquema, o bien se puede utilizar para diferenciar simplemente las entidades. En el caso de XAML, los tipos y miembros que se usan en XAML deben resolverse en última instancia para los tipos de respaldo, y los conceptos de esquemas XML no se aplican bien a esta funcionalidad. El espacio de nombres XAML contiene información que el contexto de esquema XAML debe tener disponible para poder realizar esta asignación de tipos.  
  
## <a name="xaml-namespace-components"></a>Componentes del espacio de nombres XAML  
 La definición del espacio de nombres XAML tiene dos componentes: un prefijo y un identificador. Cada uno de estos componentes está presente cuando se declara un espacio de nombres XAML en el marcado o se define en el sistema de tipos XAML.  
  
 El prefijo puede ser cualquier cadena que permita la [especificación de los espacios de nombres del W3C en XML 1,0](https://www.w3.org/TR/REC-xml-names/) . Por Convención, los prefijos suelen ser cadenas muy cortas, porque el prefijo se repite varias veces en un archivo de marcado típico. Algunos espacios de nombres XAML que están pensados para usarse en varias implementaciones de XAML usan prefijos convencionales concretos. Por ejemplo, el espacio de nombres XAML del lenguaje XAML normalmente se asigna mediante el prefijo `x`. Puede definir un espacio de nombres XAML predeterminado, en el que el prefijo no se proporciona en la definición, sino que se representa como una cadena vacía si se define o se consulta la API de los servicios XAML de by.NET Framework. Normalmente, el espacio de nombres XAML predeterminado se elige deliberadamente con el fin de promover una cantidad maximizada de marcado omitido por prefijo por una tecnología de implementación de XAML y sus escenarios y vocabularios.  
  
 El identificador puede ser cualquier cadena que permita la [especificación de los espacios de nombres del W3C en XML 1,0](https://www.w3.org/TR/REC-xml-names/). Por Convención, a menudo se proporcionan identificadores para espacios de nombres XML o espacios de nombres XAML en formato de URI, normalmente como un URI absoluto calificado con el protocolo. A menudo, la información de versión que define un vocabulario XAML determinado se implica como parte de la cadena de ruta de acceso. Los espacios de nombres XAML agregan una Convención de identificador adicional más allá de la Convención de URI XML. En el caso de los espacios de nombres XAML, el identificador comunica la información que necesita un contexto de esquema XAML para resolver los tipos que se especifican como elementos en dicho espacio de nombres XAML o para resolver atributos en miembros.  
  
 A efectos de la comunicación de información en un contexto de esquema XAML, el identificador de un espacio de nombres XAML puede seguir en el formato de URI. Sin embargo, en este caso, el URI también se declara como un identificador coincidente en un ensamblado o una lista de ensamblados determinados. Esto se hace en los ensamblados mediante la atribución del ensamblado con <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Este método de identificación del espacio de nombres XAML y la compatibilidad de un comportamiento de resolución de tipos basado en CLR en el ensamblado con atributos es compatible con el contexto de esquema XAML predeterminado en .NET Framework servicios XAML. En general, esta Convención se puede usar para los casos en los que el contexto de esquema XAML incorpora CLR o se basa en el contexto de esquema XAML predeterminado, que es necesario para leer los atributos CLR de los ensamblados CLR.  
  
 Los espacios de nombres XAML también se pueden identificar mediante una Convención que comunica un espacio de nombres CLR y un ensamblado que define el tipo. Esta Convención se usa en los casos en los que no existe ninguna atribución de <xref:System.Windows.Markup.XmlnsDefinitionAttribute> en los ensamblados que contienen tipos. Esta Convención es potencialmente más compleja que la Convención de URI y también tiene la posibilidad de ambigüedad y duplicación, ya que hay varias maneras de hacer referencia a un ensamblado.  
  
 La forma más básica de un identificador que utiliza el espacio de nombres CLR y la Convención de ensamblado es la siguiente:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:` y `; assembly=` son componentes literales de la sintaxis.  
  
 *clrnsName* es el nombre de la cadena que identifica un espacio de nombres CLR. Este nombre de cadena incluye cualquier carácter interno de punto (.) que proporcione sugerencias sobre el espacio de nombres CLR y su relación con otros espacios de nombres CLR.  
  
 *assemblyShortName* es el nombre de cadena de un ensamblado que define los tipos que son útiles en XAML. Se espera que los tipos a los que se tiene acceso a través del espacio de nombres XAML declarado estén definidos por el ensamblado y que se declaren específicamente dentro del espacio de nombres CLR especificado por *clrnsName*. Normalmente, este nombre de cadena es el paralelo de la información que se muestra en <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.  
  
 A continuación se muestra una definición más completa del espacio de nombres CLR y la Convención de ensamblado:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyName*  
  
 *AssemblyName* representa cualquier cadena que sea legal como entrada <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>. Esta cadena puede incluir información de referencia cultural, clave pública o versión (las definiciones de estos conceptos se definen en el tema de referencia de <xref:System.Reflection.Assembly>). El formato COFF y la evidencia (que usan otras sobrecargas de <xref:System.Reflection.Assembly.Load%2A>) no son relevantes para la carga de ensamblados de XAML; toda la información de carga debe presentarse como una cadena.  
  
 La especificación de una clave pública para el ensamblado es una técnica útil para la seguridad de XAML o para quitar la posible ambigüedad que puede existir si los ensamblados se cargan por nombre simple, o ya existen en una caché o un dominio de aplicación. Para obtener más información, vea [consideraciones de seguridad de XAML](xaml-security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Declaraciones de espacios de nombres XAML en la API de servicios XAML  
 En la API de servicios XAML, una declaración de espacio de nombres XAML se representa mediante un objeto <xref:System.Xaml.NamespaceDeclaration>. Si está declarando un espacio de nombres XAML en el código, llame al constructor <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29>. Los parámetros `ns` y `prefix` se especifican como cadenas, y la entrada que se debe proporcionar para estos parámetros corresponde a la definición de identificador de espacio de nombres XAML y prefijo de espacio de nombres XAML tal y como se proporcionó anteriormente en este tema.  
  
 Si está examinando la información del espacio de nombres XAML como parte de un flujo de nodo XAML o a través de otro acceso al sistema de tipos XAML, <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> notifica el identificador del espacio de nombres XAML y <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> notifica el prefijo del espacio de nombres XAML.  
  
 En un flujo de nodo XAML, la información del espacio de nombres XAML puede aparecer como un nodo XAML que precede a la entidad a la que se aplica. Esto incluye los casos en los que la información del espacio de nombres XAML precede al `StartObject` del elemento raíz XAML. Para obtener más información, consulta [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md).  
  
 En muchos escenarios en los que se usa .NET Framework API de servicios XAML, se espera que exista al menos una declaración de espacio de nombres XAML, y la declaración debe contener o hacer referencia a la información que necesita un contexto de esquema XAML. Los espacios de nombres XAML deben especificar ensamblados que se van a cargar o ayudar a resolver tipos específicos dentro de los espacios de nombres y ensamblados que ya están cargados o conocidos por el contexto de esquema XAML.  
  
 Para generar un flujo de nodo XAML, la información de tipo XAML debe estar disponible a través del contexto de esquema XAML. No se puede determinar la información de tipo XAML sin determinar primero el espacio de nombres XAML relevante para cada nodo que se va a crear. En este momento, no se crean instancias de tipos todavía, pero el contexto de esquema XAML puede necesitar buscar información del ensamblado de definición y del tipo de respaldo. Por ejemplo, para procesar el marcado `<Party><PartyFavor/></Party>`, el contexto de esquema XAML debe ser capaz de determinar el nombre y el tipo de la `ContentProperty` de `Party`y, por tanto, también debe conocer la información de espacio de nombres XAML para `Party` y `PartyFavor`. En el caso del contexto de esquema XAML predeterminado, la reflexión estática informa de gran parte de la información del sistema de tipos XAML necesaria para generar nodos de tipo XAML en el flujo de nodo.  
  
 Para generar un gráfico de objetos a partir de un flujo de nodo XAML, las declaraciones de espacios de nombres XAML deben existir para cada prefijo XAML utilizado en el marcado original y registrarse en el flujo de nodo XAML. En este momento, se crean instancias y se produce un comportamiento de asignación de tipos verdadero.  
  
 Si tiene que rellenar previamente la información del espacio de nombres XAML, en los casos en los que el espacio de nombres XAML que desea que use el contexto de esquema XAML no esté definido en el marcado, una técnica que puede usar es declarar declaraciones de espacios de nombres XML en el <xref:System.Xml.XmlParserContext> para un <xref:System.Xml.XmlReader>. A continuación, use ese <xref:System.Xml.XmlReader> como entrada para un constructor de lector XAML o <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>.  
  
 Otras dos API que son relevantes para el control de espacios de nombres XAML en .NET Framework los servicios XAML son los atributos <xref:System.Windows.Markup.XmlnsDefinitionAttribute> y <xref:System.Windows.Markup.XmlnsPrefixAttribute>. Estos atributos se aplican a los ensamblados. un contexto de esquema XAML usa <xref:System.Windows.Markup.XmlnsDefinitionAttribute> para interpretar cualquier declaración de espacio de nombres XAML que incluya un URI. <xref:System.Windows.Markup.XmlnsPrefixAttribute> lo usan las herramientas que emiten XAML para que se pueda serializar un espacio de nombres XAML determinado con un prefijo de predicción. Para obtener más información, vea [atributos de CLR relacionados con XAML para tipos y bibliotecas personalizados](xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Vea también

- [Introducción a las estructuras y conceptos de secuencias de nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
