---
title: Espacios de nombres XAML para servicios XAML de .NET
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 2ae57d08fade85c59fea2a54b653a2f775b57415
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433065"
---
# <a name="xaml-namespaces-for-net-xaml-services"></a>Espacios de nombres XAML para servicios XAML de .NET
Un espacio de nombres XAML es un concepto que se expande en la definición de un espacio de nombres XML. De forma similar a un espacio de `xmlns` nombres XML, puede definir un espacio de nombres XAML mediante un atributo en el marcado. Los espacios de nombres XAML también se representan en el flujo de nodo XAML y otras API de servicios XAML. En este tema se define el concepto de espacio de nombres XAML y se describe cómo se pueden definir los espacios de nombres XAML y los usan los contextos de esquema XAML y otros aspectos de los servicios XAML de .NET.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>Espacio de nombres XML y espacio de nombres XAML  
 Un espacio de nombres XAML es un espacio de nombres XML especializado, al igual que XAML es una forma especializada de XML y usa el formulario XML básico para su marcado. En el marcado, se declara un `xmlns` espacio de nombres XAML y su asignación a través de un atributo aplicado a un elemento. La `xmlns` declaración se puede realizar en el mismo elemento en el que se declara el espacio de nombres XAML. Una declaración de espacio de nombres XAML realizada a un elemento es válida para ese elemento, todos los atributos de ese elemento y todos los elementos secundarios de ese elemento. Los atributos pueden usar un espacio de nombres XAML que no es el mismo que el elemento que contiene el atributo, siempre y cuando el propio nombre del atributo haga referencia al prefijo como parte de su nombre de atributo en el marcado.  
  
 La distinción de un espacio de nombres XAML frente a un espacio de nombres XML es que un espacio de nombres XML se puede usar para hacer referencia a un esquema o simplemente para diferenciar entidades. Para XAML, los tipos y miembros tal como se usan en XAML deben resolverse en última instancia en tipos de respaldo y los conceptos de esquema XML no se aplican bien a esta capacidad. El espacio de nombres XAML contiene información que el contexto de esquema XAML debe tener disponible para realizar esta asignación de tipos.  
  
## <a name="xaml-namespace-components"></a>Componentes de espacio de nombres XAML  
 La definición de espacio de nombres XAML tiene dos componentes: un prefijo y un identificador. Cada uno de estos componentes está presente cuando se declara un espacio de nombres XAML en el marcado o se define en el sistema de tipos XAML.  
  
 El prefijo puede ser cualquier cadena según lo permitido por los espacios de nombres [W3C en la especificación XML 1.0.](https://www.w3.org/TR/REC-xml-names/) Por convención, los prefijos suelen ser cadenas cortas, porque el prefijo se repite muchas veces en un archivo de marcado típico. Ciertos espacios de nombres XAML que están diseñados para usarse en varias implementaciones XAML usan prefijos convencionales concretos. Por ejemplo, el espacio de nombres XAML `x`del lenguaje XAML normalmente se asigna con el prefijo . Puede definir un espacio de nombres XAML predeterminado, donde el prefijo no se proporciona en la definición, pero se representa como una cadena vacía si se define o se consulta by.NET API de servicios XAML. Normalmente, el espacio de nombres XAML predeterminado se elige deliberadamente para promover una cantidad maximizada de marcado de omisión de prefijos mediante una tecnología de implementación XAML y sus escenarios y vocabularios.  
  
 El identificador puede ser cualquier cadena según lo permitido por los espacios de nombres [W3C en la especificación XML 1.0](https://www.w3.org/TR/REC-xml-names/). Por convención, los identificadores de espacios de nombres XML o espacios de nombres XAML a menudo se dan en forma de URI, normalmente como un URI absoluto calificado por protocolo. A menudo, la información de versión que define un vocabulario XAML determinado está implícita como parte de la cadena de ruta de acceso. Los espacios de nombres XAML agregan una convención de identificador adicional más allá de la convención URI XML. Para los espacios de nombres XAML, el identificador comunica la información que necesita un contexto de esquema XAML para resolver los tipos que se especifican como elementos en ese espacio de nombres XAML o para resolver atributos a los miembros.  
  
 Para comunicar información a un contexto de esquema XAML, el identificador de un espacio de nombres XAML puede seguir en forma de URI. Sin embargo, en este caso, el URI también se declara como un identificador coincidente en un ensamblado o lista de ensamblados determinado. Esto se hace en ensamblados mediante <xref:System.Windows.Markup.XmlnsDefinitionAttribute>la atribución del ensamblado con . Este método para identificar el espacio de nombres XAML y admitir un comportamiento de resolución de tipos basado en CLR en el ensamblado con atributos es compatible con el contexto de esquema XAML predeterminado en los servicios XAML de .NET. De forma más general, esta convención se puede usar para los casos en los que el contexto de esquema XAML incorpora CLR o se basa en el contexto de esquema XAML predeterminado, que es necesario para leer los atributos CLR de ensamblados CLR.  
  
 Los espacios de nombres XAML también se pueden identificar mediante una convención que comunica un espacio de nombres CLR y un ensamblado de definición de tipos. Esta convención se utiliza <xref:System.Windows.Markup.XmlnsDefinitionAttribute> en casos en los que no existe ninguna atribución en los ensamblados que contienen tipos. Esta convención es potencialmente más compleja que la convención URI y también tiene el potencial de ambiguedad y duplicación, porque hay varias maneras de hacer referencia a un ensamblado.  
  
 La forma más básica de un identificador que usa el espacio de nombres CLR y la convención de ensamblado es la siguiente:  
  
 `clr-namespace:clrnsName; assembly=assemblyShortName`
  
 `clr-namespace:`y `; assembly=` son componentes literales de la sintaxis.  
  
 *clrnsName* es el nombre de cadena que identifica un espacio de nombres CLR. Este nombre de cadena incluye cualquier carácter de punto interno (.) que proporcione sugerencias sobre el espacio de nombres CLR y su relación con otros espacios de nombres CLR.
  
 *assemblyShortName* es el nombre de cadena de un ensamblado que define tipos que son útiles en XAML. Se espera que el ensamblado defina los tipos a los que se va a tener acceso a través del espacio de nombres XAML declarado y que se declaren dentro del espacio de nombres CLR especificado por *clrnsName*. Este nombre de cadena normalmente es <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>paralelo a la información según lo informado por .  
  
 Una definición más completa del espacio de nombres CLR y la convención de ensamblado es la siguiente:  
  
 `clr-namespace:clrnsName; assembly=assemblyName`
  
 *assemblyName* representa cualquier cadena que <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> sea legal como entrada. Esta cadena puede incluir información de referencia cultural, clave pública o versión <xref:System.Reflection.Assembly>(las definiciones de estos conceptos se definen en el tema de referencia para ). El formato COFF y las pruebas <xref:System.Reflection.Assembly.Load%2A>(como se usan en otras sobrecargas de ) no son relevantes para los propósitos de carga de ensamblados XAML; toda la información de carga debe presentarse como una cadena.  
  
 Especificar una clave pública para el ensamblado es una técnica útil para la seguridad XAML o para quitar la posible ambiguedad que puede existir si los ensamblados se cargan por nombre simple o preexistentes en una memoria caché o dominio de aplicación. Para obtener más información, vea [Consideraciones](security-considerations.md)de seguridad XAML .  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Declaraciones de espacio de nombres XAML en la API de servicios XAML  
 En la API de servicios XAML, una <xref:System.Xaml.NamespaceDeclaration> declaración de espacio de nombres XAML se representa mediante un objeto. Si declara un espacio de nombres XAML <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> en el código, llame al constructor. Los `ns` `prefix` parámetros y se especifican como cadenas y la entrada para proporcionar estos parámetros corresponde a la definición de identificador de espacio de nombres XAML y prefijo de espacio de nombres XAML como se proporciona anteriormente en este tema.  
  
 Si está examinando la información del espacio de nombres XAML como parte de <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> un flujo de <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> nodo XAML o a través de otro acceso al sistema de tipos XAML, notifica el identificador de espacio de nombres XAML e informa del prefijo de espacio de nombres XAML.  
  
 En un flujo de nodo XAML, la información del espacio de nombres XAML puede aparecer como un nodo XAML que precede a la entidad a la que se aplica. Esto incluye los casos en los `StartObject` que la información del espacio de nombres XAML precede al elemento raíz XAML. Para obtener más información, consulta [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Para muchos escenarios que usan la API de servicios XAML de .NET, se espera que exista al menos una declaración de espacio de nombres XAML y la declaración debe contener o hacer referencia a la información que requiere un contexto de esquema XAML. Los espacios de nombres XAML deben especificar los ensamblados que se van a cargar o ayudar a resolver tipos específicos dentro de espacios de nombres y ensamblados que ya están cargados o conocidos por el contexto de esquema XAML.  
  
 Para generar un flujo de nodo XAML, la información de tipo XAML debe estar disponible, a través del contexto de esquema XAML. La información de tipo XAML no se puede determinar sin determinar primero el espacio de nombres XAML relevante para cada nodo que se va a crear. En este momento, todavía no se ha creado ninguna instancia de tipos, pero es posible que el contexto del esquema XAML deba buscar información del ensamblado de definición y el tipo de respaldo. Por ejemplo, para procesar `<Party><PartyFavor/></Party>`el marcado , el contexto de esquema XAML `ContentProperty` debe `Party`ser capaz de determinar el `Party` nombre `PartyFavor`y el tipo de la de , y por lo tanto también debe conocer la información de espacio de nombres XAML para y . En el caso del contexto de esquema XAML predeterminado, la reflexión estática notifica gran parte de la información del sistema de tipos XAML necesaria para generar nodos de tipo XAML en el flujo de nodo.  
  
 Para generar un gráfico de objetos a partir de un flujo de nodo XAML, deben existir declaraciones de espacio de nombres XAML para cada prefijo XAML utilizado en el marcado original y registrado en el flujo de nodo XAML. En este punto, se están creando instancias y se produce un comportamiento de asignación de tipos verdadero.  
  
 Si necesita rellenar previamente la información del espacio de nombres XAML, en los casos en los que el espacio de nombres XAML <xref:System.Xml.XmlParserContext> que <xref:System.Xml.XmlReader>desea usar el contexto de esquema XAML no está definido en el marcado, una técnica que puede usar es declarar declaraciones de espacio de nombres XML en el for an . A continuación, úselo <xref:System.Xml.XmlReader> como entrada <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>para un constructor de lector XAML o .  
  
 Otras dos API que son relevantes para el control <xref:System.Windows.Markup.XmlnsDefinitionAttribute> de <xref:System.Windows.Markup.XmlnsPrefixAttribute>espacios de nombres XAML en .NET XAML Services son los atributos y . Estos atributos se aplican a los ensamblados. <xref:System.Windows.Markup.XmlnsDefinitionAttribute>un contexto de esquema XAML lo usa para interpretar cualquier declaración de espacio de nombres XAML que incluya un URI. <xref:System.Windows.Markup.XmlnsPrefixAttribute>las herramientas que emiten XAML para que un espacio de nombres XAML determinado se pueda serializar con un prefijo de predicción. Para obtener más información, vea [Atributos CLR relacionados con XAML para bibliotecas y tipos personalizados.](clr-attributes-with-custom-types-and-libraries.md)  
  
## <a name="see-also"></a>Consulte también

- [Introducción a las estructuras y conceptos de secuencias de nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
