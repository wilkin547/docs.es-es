---
title: Servicios XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 458b4c94d26b7bc083c5d31fcbccf05b42bba52e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-services"></a>Servicios XAML
Este tema describe las capacidades de un conjunto de tecnologías que se conoce como XAML de .NET Framework Services. La mayoría de los servicios y las API descritas se encuentran en el ensamblado System.Xaml, que es un ensamblado que se introdujo con la [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] conjunto de ensamblados de .NET core. Los servicios incluyen lectores y escritores, clases de esquema y compatibilidad de esquema, generadores, atribución de clases, compatibilidad intrínseca del lenguaje XAML y otras características del lenguaje XAML.  
  
## <a name="about-this-documentation"></a>Acerca de esta documentación  
 Documentación conceptual de los servicios XAML de .NET Framework, se da por supuesto que tiene experiencia con el lenguaje XAML y cómo aplicarlo a un marco concreto, por ejemplo [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] o [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)], o una tecnología específica de área, características para características de la personalización de compilación en el ejemplo <xref:Microsoft.Build.Framework.XamlTypes>. Esta documentación no intenta explicar los conceptos básicos de XAML como un lenguaje de marcado, terminología de la sintaxis XAML u otro material introductorio. En su lugar, esta documentación se centra en concreto utilizando los servicios XAML de .NET Framework que están habilitadas en la biblioteca de ensamblado System.Xaml. La mayoría de estas API es para escenarios de extensibilidad y la integración de lenguaje XAML. Esto podría incluir cualquiera de las siguientes acciones:  
  
-   Extender las capacidades de la base lectores de XAML o sistemas de escritura XAML (procesar el flujo de nodo XAML directamente; derivar su propio lector de XAML o el escritor de XAML).  
  
-   Definir tipos personalizados puede usar XAML que no tienen dependencias de un marco concreto y atribución los tipos para indicar su XAML tipo de características del sistema a los servicios XAML de .NET Framework.  
  
-   Hospedar los lectores o escritores XAML como un componente de una aplicación, como un diseñador visual o un editor interactivo para los orígenes de marcado XAML.  
  
-   Escribir los convertidores de valores XAML (extensiones de marcado; convertidores de tipos para los tipos personalizados).  
  
-   Define un contexto de esquema XAML personalizado (mediante técnicas de carga del ensamblado alternativas para copias de seguridad de los orígenes de tipo; mediante técnicas de búsqueda de tipos conocidos en lugar de siempre reflejar ensamblados; utilizando conceptos de ensamblado cargado que no usan el CLR `AppDomain` y su modelo de seguridad asociadas).  
  
-   Extender el sistema de tipos XAML base.  
  
-   Mediante el `Lookup` o `Invoker` técnicas para influir en el código XAML escriba sistema y cómo se evalúa los respaldos de tipo.  
  
 Si desea obtener material introductorio en XAML como un lenguaje, puede intentar [información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md). Ese tema discute XAML para una audiencia que es nueva para [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] y también al uso de marcado XAML y características del lenguaje XAML. Otro documento útil es el material introductorio en el [especificación del lenguaje XAML](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>Servicios XAML de .NET framework y System.Xaml en la arquitectura de .NET  
 En versiones anteriores de [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)], la compatibilidad con características del lenguaje XAML implementada por marcos de trabajo que se basan en [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] y [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)]) y, por tanto, modificarse en su comportamiento y la API que usa dependiendo de qué usaba un marco concreto. Esto incluye el XAML analizador y su objeto de gráfico mecanismo de creación, funciones intrínsecas del lenguaje XAML, compatibilidad con la serialización y así sucesivamente.  
  
 En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], servicios XAML de .NET Framework y el ensamblado System.Xaml definen gran parte de lo que se necesita para admitir características del lenguaje XAML. Esto incluye las clases base para los lectores y escritores de XAML. La característica más importante que se agregan a los servicios XAML de .NET Framework que no estaba presente en cualquiera de las implementaciones de XAML específicas del marco es una representación de sistema de tipos para XAML. La representación del sistema de tipo presenta XAML de una manera orientada a objetos que se centra en las capacidades XAML sin incurrir en las dependencias en las capacidades concretas de marcos de trabajo.  
  
 El sistema de tipos XAML no está limitado por el formulario de marcado o los detalles de tiempo de ejecución del origen de XAML; ni está limitado por cualquier sistema de tipos de copias de seguridad específico. El sistema de tipos XAML incluye las representaciones de objeto para los tipos, miembros, contextos de esquema XAML, conceptos del nivel XML y otros conceptos del lenguaje XAML o intrínsecos XAML. Usar o ampliar el sistema de tipos XAML hace posible derivar desde clases como lectores XAML y escritores XAML y ampliar la funcionalidad de representaciones XAML en características concretas habilitadas por un marco de trabajo, una tecnología o una aplicación que consume o emite XAML. El concepto de un contexto de esquema XAML habilita las operaciones de escritura del gráfico de objeto práctico de la combinación de una implementación de sistema de escritura de objeto XAML, sistema de tipos de respaldo de una tecnología tal y como se comunica a través de la información de ensamblado en el contexto y el nodo XAML origen. Para obtener más información sobre el concepto de esquema XAML. vea [contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>Secuencias de nodo XAML, los lectores y escritores de XAML  
 Para entender el rol que desempeña de servicios XAML de .NET Framework en la relación entre el lenguaje XAML y las tecnologías concretas que usan XAML como lenguaje, es útil comprender el concepto de un flujo de nodo XAML y cómo ese concepto da forma a la API y terminología. El flujo de nodo XAML es un conceptual intermedio entre una representación del lenguaje XAML y el gráfico de objetos que representa el código XAML o que define.  
  
-   Un lector XAML es una entidad que procesa XAML en ciertos formularios y genera un flujo de nodo XAML. En la API, un lector XAML se representa mediante la clase base <xref:System.Xaml.XamlReader>.  
  
-   Un escritor de XAML es una entidad que procesa un flujo de nodo XAML y genera otra cosa. En la API, un escritor de XAML se representa mediante la clase base <xref:System.Xaml.XamlWriter>.  
  
 Los dos escenarios más comunes que implican XAML se carga de XAML para crear instancias de un gráfico de objetos y guardar un gráfico de objetos de una aplicación o herramienta y generar una representación de XAML (normalmente en forma de marcado que se guarda como archivo de texto). Cargar XAML y crear un gráfico de objetos se conocen a menudo en esta documentación como la ruta de acceso de carga. Guardar o serializar un gráfico de objetos existentes en XAML se conoce a menudo en esta documentación como la operación de guardar ruta de acceso.  
  
 El tipo más común de ruta de acceso de carga se puede describir como sigue:  
  
-   Comience con una representación de XAML, en formato XML codificado en UTF- y guarda como un archivo de texto.  
  
-   Carga ese XAML en <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader>es un <xref:System.Xaml.XamlReader> subclase.  
  
-   El resultado es un flujo de nodo XAML. Puede tener acceso a los nodos individuales de la secuencia de nodo XAML utilizando <xref:System.Xaml.XamlXmlReader>  /  <xref:System.Xaml.XamlReader> API. La operación más habitual aquí es avanzar por el flujo de nodo XAML, procesamiento de cada nodo mediante un "registro actual" metáfora.  
  
-   Los nodos resultantes se transfieren desde el flujo de nodo XAML a un <xref:System.Xaml.XamlObjectWriter> API. <xref:System.Xaml.XamlObjectWriter>es un <xref:System.Xaml.XamlWriter> subclase.  
  
-   El <xref:System.Xaml.XamlObjectWriter> escribe un gráfico de objetos, un objeto a la vez, de acuerdo con el progreso a través de la secuencia de nodo XAML de origen. Esto se hace con la Ayuda de un contexto de esquema XAML y una implementación que puede tener acceso a los ensamblados y los tipos de un sistema de tipos de respaldo y un marco.  
  
-   Llame a <xref:System.Xaml.XamlObjectWriter.Result%2A> al final del flujo de nodo XAML para obtener el objeto raíz del gráfico de objetos.  
  
 El tipo más común de ruta de acceso se puede describir como sigue:  
  
-   Comience con el gráfico de objetos de un tiempo de ejecución de la aplicación completa, el contenido de la interfaz de usuario y el estado de un tiempo de ejecución o un segmento más pequeño de representación de objeto de la aplicación general en tiempo de ejecución.  
  
-   Desde un objeto de inicio lógico, como una raíz de la aplicación o la raíz del documento, cargue los objetos en <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader>es un <xref:System.Xaml.XamlReader> subclase.  
  
-   El resultado es un flujo de nodo XAML. Puede tener acceso a los nodos individuales de la secuencia de nodo XAML utilizando <xref:System.Xaml.XamlObjectReader> y <xref:System.Xaml.XamlReader> API. La operación más habitual aquí es avanzar por el flujo de nodo XAML, procesamiento de cada nodo mediante un "registro actual" metáfora.  
  
-   Los nodos resultantes se transfieren desde el flujo de nodo XAML a un <xref:System.Xaml.XamlXmlWriter> API. <xref:System.Xaml.XamlXmlWriter>es un <xref:System.Xaml.XamlWriter> subclase.  
  
-   El <xref:System.Xaml.XamlXmlWriter> escribe XAML en un XML UTF codificación. Puede guardar esto como un archivo de texto, como una secuencia o en otras formas.  
  
-   Llame a <xref:System.Xaml.XamlXmlWriter.Flush%2A> para obtener el resultado final.  
  
 Para obtener más información sobre los conceptos de flujo de nodo XAML, vea [Understanding XAML Node Stream Structures y conceptos](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
### <a name="the-xamlservices-class"></a>XamlServices (clase)  
 No siempre es necesario ocuparse de un flujo de nodo XAML. Si desea que una ruta de acceso de carga básica o ruta de acceso básico, puede usar las API en el <xref:System.Xaml.XamlServices> clase.  
  
-   Varias firmas de <xref:System.Xaml.XamlServices.Load%2A> implementar una ruta de acceso de carga. Puede cargar un archivo o secuencia, o puede cargar una <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> o <xref:System.Xaml.XamlReader> que ajuste a la entrada XAML, cargue las API de ese lector.  
  
-   Varias firmas de <xref:System.Xaml.XamlServices.Save%2A> guardar un gráfico de objetos y generan el resultado como una secuencia, archivo, o <xref:System.Xml.XmlWriter> / <xref:System.IO.TextWriter> instancia.  
  
-   <xref:System.Xaml.XamlServices.Transform%2A>Convierte XAML vinculando una ruta de acceso de carga y otra de guardado como una única operación. Podría usarse un contexto de esquema o el sistema de tipos de respaldo diferentes para <xref:System.Xaml.XamlReader> y <xref:System.Xaml.XamlWriter>, que es lo que afecta a cómo se transforma el XAML resultante.  
  
 Para obtener más información sobre cómo usar <xref:System.Xaml.XamlServices>, consulte [clase XAMLServices y Basic de XAML de lectura o escritura](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## <a name="xaml-type-system"></a>Sistema de tipos XAML  
 El sistema de tipos XAML proporciona las API necesarias para trabajar con un determinado nodo individual de un flujo de nodo XAML.  
  
 <xref:System.Xaml.XamlType>es la representación en forma de un objeto: lo que se está procesando entre un nodo de objeto de inicio y un nodo de objeto final.  
  
 <xref:System.Xaml.XamlMember>es la representación para un miembro de un objeto: lo que se está procesando entre un nodo de miembro de inicio y un nodo de miembro final.  
  
 Las API como <xref:System.Xaml.XamlType.GetAllMembers%2A> y <xref:System.Xaml.XamlType.GetMember%2A> y <xref:System.Xaml.XamlMember.DeclaringType%2A> notifican las relaciones entre un <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>.  
  
 El comportamiento predeterminado del sistema de tipos XAML tal como está implementado por los servicios XAML de .NET Framework se basa en el common language runtime (CLR) y el análisis estático de tipos CLR en ensamblados mediante reflexión. Por lo tanto, para un tipo específico de CLR, la implementación predeterminada del sistema de tipos XAML puede exponer el esquema XAML de ese tipo y sus miembros y notificarlo en términos de sistema de tipos XAML. En el sistema de tipos XAML de forma predeterminada, el concepto de capacidad de asignación de tipos se asigna a la herencia de CLR y los conceptos de instancias, tipos de valor y así sucesivamente también se asignan a los comportamientos de compatibilidad y características de CLR.  
  
## <a name="reference-for-xaml-language-features"></a>Referencia de características del lenguaje XAML  
 Para admitir XAML, servicios XAML de .NET Framework proporcionan una implementación concreta de los conceptos del lenguaje XAML como se define para el espacio de nombres XAML de lenguaje XAML. Estos se documentan como páginas de referencia específica. Las características del lenguaje se documentan desde la perspectiva de cómo se comportan estas características del lenguaje cuando se procesan mediante un lector XAML o sistema de escritura XAML que se define por los servicios XAML de .NET Framework. Para obtener más información, consulta [XAML Namespace (x:) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).
