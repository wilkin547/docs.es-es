---
title: Espacios de nombres XAML para los servicios XAML de .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: e09279209bf3d6925b61d55d6988b5af658f5aab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>Espacios de nombres XAML para los servicios XAML de .NET Framework
Un espacio de nombres XAML es un concepto que se expande en la definición de un espacio de nombres XML. Similar a un espacio de nombres XML, puede definir un espacio de nombres XAML mediante un `xmlns` atributo en el marcado. Espacios de nombres XAML también se representan en el flujo de nodo XAML y otras API de servicios XAML. Este tema define el concepto de espacio de nombres XAML y describe cómo los espacios de nombres XAML pueden definirse y usan contextos de esquema XAML y otros aspectos de servicios XAML de .NET Framework.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>Namespace XML y XAML Namespace  
 Un espacio de nombres XAML es un espacio de nombres XML especializado, como XAML es una forma especializada de XML y usa la forma XML básica para su marcado. En el marcado, se declaran un espacio de nombres XAML y su asignación a través de un `xmlns` atributo aplicado a un elemento. El `xmlns` declaración puede realizarse al mismo elemento declarado en el espacio de nombres XAML. Una declaración de espacio de nombres XAML realizada en un elemento es válida para ese elemento, todos los atributos de ese elemento y todos los elementos secundarios de ese elemento. Atributos pueden usar espacios de nombres XAML que no es el mismo que el elemento que contiene el atributo, siempre y cuando el propio nombre de atributo hace referencia el prefijo como parte de su nombre de atributo en el marcado.  
  
 La distinción de un espacio de nombres XAML frente a un espacio de nombres XML es que un espacio de nombres XML podría utilizarse para hacer referencia a un esquema, o puede utilizar para diferenciar los simplemente entidades. Para XAML, en última instancia se deben resolver los tipos y miembros tal y como se utilizan en XAML como tipos de respaldo y conceptos de esquema XML no se aplican también a esta capacidad. El espacio de nombres XAML contiene información que el contexto de esquema XAML debe estar disponible para realizar esta asignación de tipos.  
  
## <a name="xaml-namespace-components"></a>Componentes de Namespace XAML  
 La definición de espacio de nombres XAML tiene dos componentes: un prefijo y un identificador. Cada uno de estos componentes están presentes cuando un espacio de nombres XAML está declarado en el marcado o definido en el sistema de tipos XAML.  
  
 El prefijo puede ser cualquier cadena según lo permitido por el [espacios de nombres de W3C en la especificación XML 1.0](http://go.microsoft.com/fwlink/?LinkID=161735) . Por convención, los prefijos son normalmente muy cortas cadenas, ya que el prefijo se repite tantas veces en un archivo de marcado típico. Determinados espacios de nombres XAML que están diseñados para usarse en varias implementaciones de XAML utilizan los prefijos convencionales determinados. Por ejemplo, el espacio de nombres XAML de lenguaje XAML normalmente se asigna con el prefijo `x`. Puede definir un valor predeterminado espacio de nombres XAML, donde el prefijo no está especificado en la definición, pero se representa como una cadena vacía si no definido o consultar by.NET API de servicios XAML de Framework. Normalmente, el espacio de nombres XAML predeterminado se elige deliberadamente con el fin de promover una cantidad máxima de omisión de prefijo marcado con una tecnología de implementación de XAML y sus escenarios y vocabularios.  
  
 El identificador puede ser cualquier cadena según lo permitido por el [espacios de nombres de W3C en la especificación XML 1.0](http://go.microsoft.com/fwlink/?LinkID=161735). Por convención, identificadores de espacios de nombres XML o espacios de nombres XAML a menudo tienen en forma URI, normalmente como un URI absoluto calificado por el protocolo. A menudo, información de versión que define un vocabulario XAML concreto se considera como parte de la cadena de ruta de acceso. Espacios de nombres XAML agregar una convención de identificador adicionales más allá de la convención de URI XML. Para espacios de nombres XAML, el identificador comunica información es necesaria para un contexto de esquema XAML para resolver los tipos que se especifican como elementos en ese espacio de nombres XAML, o para resolver los atributos a los miembros.  
  
 Para fines de comunicación de información a un contexto de esquema XAML, el identificador de un espacio de nombres XAML todavía podría en forma URI. Sin embargo, en este caso también se declara el identificador URI como un identificador de búsqueda de coincidencias en un ensamblado determinado o una lista de ensamblados. Esto se hace en ensamblados mediante atribución el ensamblado con <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Este método para identificar el espacio de nombres XAML y admitir un comportamiento de resolución de tipos basado en CLR en el ensamblado con atributos es compatible con el contexto de esquema XAML predeterminado en los servicios XAML de .NET Framework. Por lo general, esta convención sirve para los casos donde el contexto de esquema XAML incorpora CLR o que se basa en el contexto de esquema XAML predeterminado, que es necesario para leer los atributos CLR desde los ensamblados CLR.  
  
 Espacios de nombres XAML también pueden identificarse mediante una convención que se comunica un espacio de nombres CLR y un ensamblado de definición de tipo. Esta convención se utiliza en casos donde no <xref:System.Windows.Markup.XmlnsDefinitionAttribute> atribución existe en los ensamblados que contienen tipos. Esta convención es potencialmente más compleja que la convención URI pero también tiene la posibilidad de ambigüedad y duplicados, porque hay varias maneras de hacer referencia a un ensamblado.  
  
 La forma más básica de un identificador que utiliza la convención de espacio de nombres y ensamblado CLR es como sigue:  
  
 `clr-namespace:`*clrnsName* `; assembly=` *nombreCortoDeEnsamblado*  
  
 `clr-namespace:`y `; assembly=` son componentes literales de la sintaxis.  
  
 *clrnsName* es el nombre de cadena que identifica un espacio de nombres CLR. Este nombre de la cadena incluye cualquier carácter interno de punto (.) que proporcionan sugerencias sobre el espacio de nombres CLR y su relación con otros espacios de nombres CLR.  
  
 *nombreCortoDeEnsamblado* es el nombre de cadena de un ensamblado que define los tipos que son útiles en XAML. Los tipos que se va a tener acceso a través del espacio de nombres declarado en XAML se esperan a definirse mediante el ensamblado y que se declaren específicamente en el espacio de nombres CLR especificado por *clrnsName*. Este nombre de cadena normalmente asemeja a la información notificados por <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.  
  
 Una definición más completa de la convención de espacio de nombres y ensamblado CLR es como sigue:  
  
 `clr-namespace:`*clrnsName* `; assembly=` *assemblyName*  
  
 *assemblyName* representa una cadena que sea válida como una <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> entrada. Esta cadena puede incluir la referencia cultural, clave pública o información de versión (definiciones de estos conceptos se definen en el tema de referencia para <xref:System.Reflection.Assembly>). COFF formato y la evidencia (como se hace otras sobrecargas del <xref:System.Reflection.Assembly.Load%2A>) no son relevantes para el ensamblado XAML cargando fines; toda la información de carga se debe presentar como una cadena.  
  
 Especifique una clave pública para el ensamblado es una técnica útil para la seguridad XAML, o para quitar la posible ambigüedad que puede existir si los ensamblados se cargan por el nombre simple o ya existan en un dominio de aplicación o de la memoria caché. Para obtener más información, consulte [consideraciones de seguridad sobre XAML](../../../docs/framework/xaml-services/xaml-security-considerations.md).  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Declaraciones de Namespace XAML en la API de servicios XAML  
 En la API de servicios XAML, una declaración de espacio de nombres XAML se representa mediante un <xref:System.Xaml.NamespaceDeclaration> objeto. Si declara un espacio de nombres XAML en el código, se llama a la <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> constructor. El `ns` y `prefix` se especifican como cadenas y la entrada que proporcione para estos parámetros se corresponde a la definición del identificador del espacio de nombres XAML y el prefijo de espacio de nombres XAML como indicadas anteriormente en este tema.  
  
 Si está examinando la información del espacio de nombres XAML como parte de un flujo de nodo XAML o a través de otro acceso al sistema de tipos XAML, <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> notifica el identificador del espacio de nombres XAML, y <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> notifica el prefijo de espacio de nombres XAML.  
  
 En un flujo de nodo XAML, la información de espacio de nombres XAML puede aparecer como un nodo XAML que precede a la entidad a la que se aplica. Esto incluye los casos donde la información de espacio de nombres XAML precede el `StartObject` del elemento raíz XAML. Para obtener más información, consulta [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
 Para muchos escenarios que usan la API de servicios XAML de .NET Framework, se espera que al menos una declaración de espacio de nombres XAML existe, y la declaración debe contener o hacer referencia a la información que requiere un contexto de esquema XAML. Los espacios de nombres XAML deben especificar ensamblados de los que se va a cargar o ayudar a resolver los tipos específicos dentro de espacios de nombres y ensamblados que ya están cargados o conocidos por el contexto de esquema XAML.  
  
 Con el fin de generar un flujo de nodo XAML, información de tipos XAML debe estar disponible a través del contexto de esquema XAML. No se puede determinar la información de tipo XAML sin primero determinar el espacio de nombres XAML pertinente para cada nodo que se va a crear. En este momento, no hay instancias de tipos aún se han creado, pero el contexto de esquema XAML que necesite ver la información de la definición de ensamblado y tipo de respaldo. Por ejemplo, para procesar el marcado `<Party><PartyFavor/></Party>`, el contexto de esquema XAML debe ser capaz de determinar el nombre y tipo de la `ContentProperty` de `Party`y, por tanto, también debe conocer la información de espacio de nombres XAML para `Party` y `PartyFavor`. En el caso el contexto de esquema XAML predeterminado de reflexión estática informa gran parte de la información del sistema de tipo XAML que es necesario para generar los nodos de tipo XAML del flujo de nodo.  
  
 Para generar un gráfico de objetos de un flujo de nodo XAML, declaraciones de espacios de nombres XAML deben existir para cada prefijo XAML usa en el marcado original y se graba en el flujo de nodo XAML. En este punto, se crea instancias y se produce el comportamiento de asignación de tipo es true.  
  
 Si tiene que rellenar la información de espacio de nombres XAML, en casos donde el espacio de nombres XAML que piensa que el contexto de esquema XAML para usar no está definido en el marcado, es una técnica que se puede utilizar declarar las declaraciones de espacio de nombres XML en el <xref:System.Xml.XmlParserContext> para un <xref:System.Xml.XmlReader>. A continuación, usar ese <xref:System.Xml.XmlReader> como entrada para un constructor de lector XAML, o <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>.  
  
 Dos otra API que son relevantes para el espacio de nombres XAML de control en los servicios XAML de .NET Framework son los atributos <xref:System.Windows.Markup.XmlnsDefinitionAttribute> y <xref:System.Windows.Markup.XmlnsPrefixAttribute>. Estos atributos se aplican a los ensamblados. <xref:System.Windows.Markup.XmlnsDefinitionAttribute>se usa un contexto de esquema XAML para interpretar una declaración de espacio de nombres XAML que incluye un URI. <xref:System.Windows.Markup.XmlnsPrefixAttribute>se utiliza con herramientas que emiten XAML para que un espacio de nombres XAML determinado se puede serializar con un prefijo de predicción. Para obtener más información, consulte [Related atributos de CLR para tipos personalizados y bibliotecas](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las estructuras y conceptos de secuencias de nodo XAML](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
