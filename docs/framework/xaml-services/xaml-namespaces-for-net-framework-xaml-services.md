---
title: Espacios de nombres XAML para los servicios XAML de .NET Framework
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 2e9e2d9e2257e5e6059210b82a69d7a837254032
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736804"
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>Espacios de nombres XAML para los servicios XAML de .NET Framework
Un espacio de nombres XAML es un concepto que se expande en la definición de un espacio de nombres XML. Al igual que el espacio de nombres XML, puede definir un espacio de nombres XAML mediante una `xmlns` atributo en el marcado. Los espacios de nombres XAML también se representan en el flujo de nodo XAML y otras API de servicios de XAML. En este tema define el concepto de espacio de nombres XAML y se describe cómo los espacios de nombres XAML se pueden definir y utilizan los contextos de esquema XAML y otros aspectos de servicios XAML de .NET Framework.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>Namespace XML y XAML Namespace  
 Un espacio de nombres XAML es un espacio de nombres XML especializado, tal como XAML es una forma especializada de XML y usa la forma XML básica para su marcado. En el marcado, declara un espacio de nombres XAML y su asignación a través de un `xmlns` atributo aplicado a un elemento. El `xmlns` declaración puede realizarse al mismo elemento declarado en el espacio de nombres XAML. Una declaración de espacio de nombres XAML realizada a un elemento es válida para ese elemento, todos los atributos de ese elemento y todos los elementos secundarios de ese elemento. Atributos pueden usar un espacios de nombres XAML que no es igual que el elemento que contiene el atributo, siempre y cuando el nombre del atributo hace referencia el prefijo como parte de su nombre de atributo de marcado.  
  
 La diferencia de un espacio de nombres XAML frente a un espacio de nombres XML es que un espacio de nombres XML podría utilizarse para hacer referencia a un esquema, o podría utilizarse para diferenciar simplemente las entidades. Para XAML, en última instancia, se deben resolver los tipos y miembros que se usa en XAML a tipos de respaldo y conceptos de esquema XML no se aplican también a esta funcionalidad. El espacio de nombres XAML contiene información que el contexto de esquema XAML debe tener disponibles para realizar esta asignación de tipos.  
  
## <a name="xaml-namespace-components"></a>Componentes XAML Namespace  
 La definición de espacio de nombres XAML tiene dos componentes: un prefijo y un identificador. Cada uno de estos componentes están presentes cuando un espacio de nombres XAML se declara en el marcado o definido en el sistema de tipos XAML.  
  
 El prefijo puede ser cualquier cadena según lo permitido por el [espacios de nombres de W3C en la especificación XML 1.0](https://go.microsoft.com/fwlink/?LinkID=161735) . Por convención, los prefijos son cadenas normalmente muy cortas, porque el prefijo se repite varias veces en un archivo de marcado típico. Determinados espacios de nombres XAML que están diseñados para usarse en varias implementaciones de XAML utilizan los prefijos convencionales determinados. Por ejemplo, el espacio de nombres XAML de lenguaje XAML normalmente se asigna utilizando el prefijo `x`. Puede definir un XAML espacio de nombres predeterminado, donde el prefijo no se proporciona en la definición, pero se representa como una cadena vacía si no definido o consultar by.NET API de servicios XAML de Framework. Normalmente, espacio de nombres XAML predeterminado es elegido deliberadamente a fin de promover una cantidad maximizada de omisión de prefijo de marcado mediante una tecnología de implementación de XAML y sus escenarios y vocabularios.  
  
 El identificador puede ser cualquier cadena según lo permitido por el [espacios de nombres de W3C en la especificación XML 1.0](https://go.microsoft.com/fwlink/?LinkID=161735). Por convención, los identificadores para los espacios de nombres XML o espacios de nombres XAML a menudo reciben en formato URI, normalmente como un URI absoluto completo de protocolo. A menudo, la información de versión que define un vocabulario XAML concreto está implícita como parte de la cadena de ruta de acceso. Los espacios de nombres XAML agregar una convención de identificador adicional más allá de la convención URI XML. Espacios de nombres XAML, el identificador comunica información que necesita un contexto de esquema XAML con el fin de resolver los tipos que se especifican como elementos en ese espacio de nombres XAML o para resolver los atributos a los miembros.  
  
 Para fines de comunicación de información a un contexto de esquema XAML, el identificador de un espacio de nombres XAML todavía podría en forma de URI. Sin embargo, en este caso también se declara el identificador URI como un identificador coincidente en un ensamblado determinado o una lista de ensamblados. Esto se realiza en ensamblados mediante atribución el ensamblado con <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Este método de identificar el espacio de nombres XAML y que admiten un comportamiento de resolución de tipos basados en CLR del ensamblado con atributos es compatible con el contexto de esquema XAML predeterminado en los servicios XAML de .NET Framework. Por lo general, esta convención puede usarse para los casos donde el contexto de esquema XAML incorpora CLR o se basa en el contexto de esquema XAML predeterminado, que es necesario para leer los atributos CLR de los ensamblados CLR.  
  
 Los espacios de nombres XAML también pueden identificarse por una convención que se comunica un espacio de nombres CLR y un ensamblado de definición de tipo. Esta convención se utiliza en casos donde no <xref:System.Windows.Markup.XmlnsDefinitionAttribute> atribución existe en los ensamblados que contienen tipos. Esta convención es potencialmente más compleja que la convención de URI y también tiene la posibilidad de ambigüedad y duplicación, porque hay varias maneras de hacer referencia a un ensamblado.  
  
 La forma más básica de un identificador que usa la convención de espacio de nombres y ensamblado CLR es como sigue:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:` y `; assembly=` son componentes literales de la sintaxis.  
  
 *clrnsName* es el nombre de cadena que identifica un espacio de nombres CLR. Este nombre de la cadena incluye cualquier carácter interno de punto (.) que proporcionan sugerencias sobre el espacio de nombres CLR y su relación con otros espacios de nombres CLR.  
  
 *assemblyShortName* es el nombre de cadena de un ensamblado que define los tipos que son útiles en XAML. Se esperan que los tipos que se va a obtenerse a través del espacio de nombres XAML declarado a definirse mediante el ensamblado y específicamente declarado en el espacio de nombres CLR especificado por *clrnsName*. Este nombre de la cadena es normalmente la información similar notificado por <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.  
  
 Una definición completa de la convención de espacio de nombres y ensamblado CLR es como sigue:  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyName*  
  
 *assemblyName* representa cualquier cadena válida como un <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> entrada. Esta cadena puede incluir la referencia cultural, clave pública o información de versión (definiciones de estos conceptos se definen en el tema de referencia <xref:System.Reflection.Assembly>). COFF formato y la evidencia (tal como los usan otras sobrecargas de <xref:System.Reflection.Assembly.Load%2A>) no son relevantes para el ensamblado XAML al cargar fines; toda la información de carga se debe presentar como una cadena.  
  
 Especifica una clave pública para el ensamblado es una técnica útil para la seguridad XAML o para quitar posibles ambigüedades que pueden existir si los ensamblados cargados por el nombre simple o existan previamente en un dominio de aplicación o la memoria caché. Para obtener más información, consulte [XAML Security Considerations](../../../docs/framework/xaml-services/xaml-security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Declaraciones de Namespace XAML en la API de servicios XAML  
 En la API de servicios XAML, una declaración de espacio de nombres XAML se representa mediante un <xref:System.Xaml.NamespaceDeclaration> objeto. Si declara un espacio de nombres XAML en el código, llame a la <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> constructor. El `ns` y `prefix` parámetros se especifican como cadenas, y la entrada que proporcione para estos parámetros se corresponde a la definición del identificador de espacio de nombres XAML y el prefijo de espacio de nombres XAML como indicadas anteriormente en este tema.  
  
 Si está examinando la información de espacio de nombres XAML como parte de un flujo de nodo XAML o a través de otros accesos al sistema de tipos XAML, <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> notifica el identificador de espacio de nombres XAML, y <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> notifica el prefijo de espacio de nombres XAML.  
  
 En un flujo de nodo XAML, la información de espacio de nombres XAML puede aparecer como un nodo XAML que precede a la entidad a la que se aplica. Esto incluye los casos donde la información de espacio de nombres XAML precede el `StartObject` del elemento raíz XAML. Para obtener más información, consulta [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Para muchos escenarios que usan la API de servicios XAML de .NET Framework, al menos una declaración de espacio de nombres XAML que se espera que exista, y la declaración debe contener o hacer referencia a la información que necesita un contexto de esquema XAML. Los espacios de nombres XAML deben especificar los ensamblados para ser cargados o para ayudar a resolver tipos específicos dentro de espacios de nombres y ensamblados que ya están cargados o conocidos por el contexto de esquema XAML.  
  
 Para generar un flujo de nodo XAML, información de tipo XAML debe estar disponible, mediante el contexto de esquema XAML. No se puede determinar la información de tipo XAML sin determinar primero el espacio de nombres XAML pertinente para cada nodo crear. En este momento, no hay instancias de tipos se crean aún, pero el contexto de esquema XAML que necesite ver la información de la definición de ensamblado y tipo de respaldo. Por ejemplo, para procesar el marcado `<Party><PartyFavor/></Party>`, el contexto de esquema XAML debe ser capaz de determinar el nombre y tipo de la `ContentProperty` de `Party`y, por tanto, también debe conocer la información de espacio de nombres XAML para `Party` y `PartyFavor`. En el caso del contexto de esquema XAML predeterminado, reflexión estática informa gran parte de la información del sistema de tipo XAML que es necesario para generar nodos de tipo XAML del flujo de nodo.  
  
 Para generar un gráfico de objetos de un flujo de nodo XAML, las declaraciones de espacio de nombres XAML deben existir para cada prefijo XAML usado en el marcado original y se registran en el flujo de nodo XAML. En este momento, se crean instancias, y se produce el comportamiento de asignación de tipo es true.  
  
 Si tiene que rellenar la información de espacio de nombres XAML, en casos donde el espacio de nombres XAML que piensa que el contexto de esquema XAML para usar no está definido en el marcado, es una técnica que puede utilizar declarar las declaraciones de espacio de nombres XML en el <xref:System.Xml.XmlParserContext> para un <xref:System.Xml.XmlReader>. A continuación, úsela <xref:System.Xml.XmlReader> como entrada de un constructor de lector XAML o <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>.  
  
 Otra dos API que son relevantes para el espacio de nombres XAML de control en los servicios XAML de .NET Framework son los atributos <xref:System.Windows.Markup.XmlnsDefinitionAttribute> y <xref:System.Windows.Markup.XmlnsPrefixAttribute>. Estos atributos se aplican a los ensamblados. <xref:System.Windows.Markup.XmlnsDefinitionAttribute> está usando un contexto de esquema XAML para interpretar las declaraciones de espacio de nombres XAML que incluye un URI. <xref:System.Windows.Markup.XmlnsPrefixAttribute> usa las herramientas que emiten XAML para que se puede serializar un espacio de nombres XAML determinado con un prefijo de predicción. Para obtener más información, consulte [Related atributos de CLR para tipos personalizados y bibliotecas](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Vea también
- [Introducción a las estructuras y conceptos de secuencias de nodo XAML](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
