---
title: Servicios XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: c99e44c7d373d050113687753d4f18eca27e0de5
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457401"
---
# <a name="xaml-services"></a>Servicios XAML
En este tema se describe las funcionalidades de un conjunto de tecnologías servicios conocidos como XAML de .NET Framework. La mayoría de los servicios y las API descritas se encuentran en el ensamblado System.Xaml, que es un ensamblado que se introdujo con el conjunto de .NET Framework 4 de los ensamblados de .NET core. Los servicios incluyen lectores y escritores, clases de esquema y la compatibilidad con el esquema, fábricas, atribución de clases, compatibilidad intrínseca con el lenguaje XAML y otras características del lenguaje XAML.  
  
## <a name="about-this-documentation"></a>Acerca de esta documentación  
 Documentación conceptual para los servicios XAML de .NET Framework se da por supuesto que tiene experiencia previa con el lenguaje XAML y cómo es posible que se aplican a un marco concreto, por ejemplo [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] o Windows Workflow Foundation o una característica de tecnología específica área, por ejemplo la personalización de compilación las características en <xref:Microsoft.Build.Framework.XamlTypes>. Esta documentación no intenta explicar los conceptos básicos de XAML como un lenguaje de marcado, terminología de sintaxis XAML u otro material introductorio. En su lugar, esta documentación se centra en específicamente con los servicios XAML de .NET Framework que están habilitadas en la biblioteca de ensamblado System.Xaml. La mayoría de estas API son para escenarios de integración de lenguaje XAML y extensibilidad. Esto podría incluir cualquiera de las siguientes acciones:  
  
- Extender las capacidades de los lectores XAML bases o los escritores XAML (procesar el flujo de nodo XAML directamente; derivar su propio lector XAML o sistema de escritura XAML).  
  
- Definir tipos personalizados que pueda usar de XAML que no tienen dependencias de un marco concreto y atribución de los tipos para transmitir su XAML tipo de características del sistema para servicios XAML de .NET Framework.  
  
- Hospedaje de los lectores XAML o sistemas de escritura XAML como un componente de una aplicación, como un diseñador visual o un editor interactivo para los orígenes de marcado XAML.  
  
- Escritura de XAML convertidores de valores (extensiones de marcado; convertidores de tipos para los tipos personalizados).  
  
- Definir un contexto de esquema XAML personalizado (usar técnicas alternativas de carga de ensamblados para los orígenes de tipo de respaldo; mediante técnicas de búsqueda de tipos conocidos en lugar de siempre que refleja los ensamblados; el uso de los conceptos de ensamblado cargado que no usan CLR `AppDomain` y su modelo de seguridad asociadas).  
  
- Extender el sistema de tipos XAML base.  
  
- Mediante el `Lookup` o `Invoker` técnicas para influir en el XAML tipo de sistema y cómo se evalúa los respaldos de tipo.  
  
 Si desea obtener material introductorio en XAML como lenguaje, podría intentar [información general sobre XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md). Ese tema discute XAML para una audiencia que es una novedad tanto a [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] y también al uso de marcado XAML y las características del lenguaje XAML. Otro documento útil es el material de introducción de la [especificación del lenguaje XAML](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>Servicios XAML de .NET framework y System.Xaml en la arquitectura de .NET  
 En versiones anteriores de Microsoft .NET Framework, la compatibilidad con los marcos de trabajo que se basan en Microsoft .NET Framework la implementó características del lenguaje XAML ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Windows Workflow Foundation y Windows Communication Foundation (WCF)) y, por tanto, varían en su comportamiento y la API usa dependiendo de qué marco concreto estaba usando. Esto incluye el XAML analizador y su objeto de gráfico de mecanismo de creación, intrínsecos del lenguaje XAML, compatibilidad con la serialización y así sucesivamente.  
  
 En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], los servicios XAML de .NET Framework y el ensamblado System.Xaml definen gran parte de lo necesario para admitir las características del lenguaje XAML. Esto incluye las clases base para los lectores XAML y escritores XAML. La característica más importante que se agregan a los servicios XAML de .NET Framework que no estaba presente en cualquiera de las implementaciones de XAML específicas del marco es una representación de sistema de tipos para XAML. La representación del tipo sistema presenta XAML de una manera orientada a objetos que se centra en las capacidades XAML sin tener dependencias en las capacidades específicas de marcos.  
  
 El sistema de tipos XAML no está limitado por el formulario de marcado o detalles de tiempo de ejecución del origen XAML; tampoco está limitado por cualquier sistema de tipos específicos de seguridad. El sistema de tipos XAML incluye las representaciones de objeto para los tipos, miembros, contextos de esquema XAML, los conceptos de nivel de XML y otros conceptos del lenguaje XAML o intrínsecos XAML. Usar o ampliar el sistema de tipos XAML hace posible derivar clases como lectores XAML y escritores XAML y extender la funcionalidad de representaciones XAML en las características específicas habilitadas por un marco de trabajo, una tecnología o una aplicación que consume o emite XAML. El concepto de un contexto de esquema XAML permite operaciones de escritura de gráfico de objeto práctico de la combinación de una implementación de sistema de escritura de objetos XAML, sistema de tipos de respaldo de una tecnología como comunica a través de la información de ensamblado en el contexto y el nodo XAML código fuente. Para obtener más información sobre el concepto de esquema XAML. consulte [el contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF](default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>Secuencias de nodo XAML, los lectores XAML y escritores XAML  
 Para comprender el papel que desempeña servicios XAML de .NET Framework en la relación entre el lenguaje XAML y las tecnologías concretas que usan XAML como lenguaje, es útil comprender el concepto de un flujo de nodo XAML y cómo ese concepto da forma a la API y terminología. El flujo de nodo XAML es un conceptual intermedio entre una representación del lenguaje XAML y el gráfico de objetos que representa el XAML o que define.  
  
- Un lector XAML es una entidad que procesa XAML en alguna forma y genera un flujo de nodo XAML. En la API, un lector XAML se representa mediante la clase base <xref:System.Xaml.XamlReader>.  
  
- Un escritor XAML es una entidad que procesa un flujo de nodo XAML y genera algo más. En la API, un escritor XAML se representa mediante la clase base <xref:System.Xaml.XamlWriter>.  
  
 Los dos escenarios más comunes que implican XAML se carga XAML para crear una instancia de un gráfico de objetos y guardar un gráfico de objetos de una aplicación o herramienta y generar una representación de XAML (normalmente en formato de marcado guardado como archivo de texto). Cargar XAML y crear un gráfico de objetos a menudo se conocen en esta documentación como la ruta de acceso de carga. Guardar o serializar un gráfico de objetos existentes en XAML se conoce a menudo en esta documentación como guardar ruta de acceso.  
  
 El tipo más común de ruta de acceso de carga puede describirse como sigue:  
  
- Comience con una representación de XAML, en formato XML codificado en UTF- y guarda como un archivo de texto.  
  
- Carga ese XAML en <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader> es un <xref:System.Xaml.XamlReader> subclase.  
  
- El resultado es un flujo de nodo XAML. Puede tener acceso a los nodos individuales de la secuencia de nodo XAML utilizando <xref:System.Xaml.XamlXmlReader>  /  <xref:System.Xaml.XamlReader> API. Aquí la operación más habitual consiste en avanzar por el flujo de nodo XAML, procesamiento de cada nodo mediante un "registro actual" metáfora.  
  
- Pase los nodos resultantes del flujo de nodo XAML a un <xref:System.Xaml.XamlObjectWriter> API. <xref:System.Xaml.XamlObjectWriter> es un <xref:System.Xaml.XamlWriter> subclase.  
  
- El <xref:System.Xaml.XamlObjectWriter> escribe un gráfico de objetos, un objeto a la vez, de acuerdo con el progreso a través de la secuencia de nodos XAML de origen. Esto se hace con la Ayuda de un contexto de esquema XAML y una implementación que puede tener acceso a los ensamblados y tipos de un sistema de tipos de respaldo y un marco.  
  
- Llamar a <xref:System.Xaml.XamlObjectWriter.Result%2A> al final del flujo de nodo XAML para obtener el objeto raíz del gráfico de objetos.  
  
 El tipo más común de ruta de acceso puede describirse como sigue:  
  
- Comience con el gráfico de objetos de un tiempo de ejecución de la aplicación completa, el contenido de la interfaz de usuario y el estado de un tiempo de ejecución, o un segmento más pequeño de representación de objeto de la aplicación general en tiempo de ejecución.  
  
- Desde un objeto de inicio lógico, como una raíz de la aplicación o la raíz del documento, cargar los objetos en <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader> es un <xref:System.Xaml.XamlReader> subclase.  
  
- El resultado es un flujo de nodo XAML. Puede tener acceso a los nodos individuales de la secuencia de nodo XAML utilizando <xref:System.Xaml.XamlObjectReader> y <xref:System.Xaml.XamlReader> API. Aquí la operación más habitual consiste en avanzar por el flujo de nodo XAML, procesamiento de cada nodo mediante un "registro actual" metáfora.  
  
- Pase los nodos resultantes del flujo de nodo XAML a un <xref:System.Xaml.XamlXmlWriter> API. <xref:System.Xaml.XamlXmlWriter> es un <xref:System.Xaml.XamlWriter> subclase.  
  
- El <xref:System.Xaml.XamlXmlWriter> escribe XAML en un XML de UTF codificación. Puede guardar esto como un archivo de texto, como una secuencia o en otras formas.  
  
- Llame a <xref:System.Xaml.XamlXmlWriter.Flush%2A> para obtener el resultado final.  
  
 Para obtener más información sobre los conceptos de flujo de nodo XAML, vea [Understanding XAML Node Stream Structures y conceptos](understanding-xaml-node-stream-structures-and-concepts.md).  
  
### <a name="the-xamlservices-class"></a>La clase XamlServices  
 No siempre es necesario tratar con un flujo de nodo XAML. Si desea que una ruta de acceso de carga básico o guardar la ruta de acceso básico, puede usar las API en el <xref:System.Xaml.XamlServices> clase.  
  
- Varias firmas de <xref:System.Xaml.XamlServices.Load%2A> implementar una ruta de acceso de carga. Puede cargar un archivo o secuencia, o puede cargar un <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> o <xref:System.Xaml.XamlReader> que encapsulan la entrada XAML mediante la carga con las API de ese lector.  
  
- Varias firmas de <xref:System.Xaml.XamlServices.Save%2A> guardar un gráfico de objetos y generan el resultado como una secuencia, archivo, o <xref:System.Xml.XmlWriter> / <xref:System.IO.TextWriter> instancia.  
  
- <xref:System.Xaml.XamlServices.Transform%2A> Convierte XAML vinculando una ruta de acceso de carga y una operación de guardar ruta de acceso como una sola operación. Un contexto de esquema o el sistema de tipos de respaldo diferentes podría usarse para <xref:System.Xaml.XamlReader> y <xref:System.Xaml.XamlWriter>, que es lo que afecta a cómo se transforma el XAML resultante.  
  
 Para obtener más información sobre cómo usar <xref:System.Xaml.XamlServices>, consulte [la clase XAMLServices y básicos de XAML de lectura o escritura](xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## <a name="xaml-type-system"></a>Sistema de tipos XAML  
 El sistema de tipos XAML proporciona las API que son necesarios para trabajar con un determinado nodo individual de un flujo de nodo XAML.  
  
 <xref:System.Xaml.XamlType> es la representación de un objeto - lo que se está procesando entre un nodo de objeto inicial y un nodo de objeto final.  
  
 <xref:System.Xaml.XamlMember> es la representación de un miembro de un objeto: lo que se está procesando entre un nodo de miembro inicial y un nodo de miembro final.  
  
 Las API como <xref:System.Xaml.XamlType.GetAllMembers%2A> y <xref:System.Xaml.XamlType.GetMember%2A> y <xref:System.Xaml.XamlMember.DeclaringType%2A> notificar las relaciones entre un <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>.  
  
 El comportamiento predeterminado del sistema de tipos XAML tal como se implementa servicios XAML de .NET Framework se basa en el common language runtime (CLR) y el análisis estático de tipos CLR en ensamblados mediante reflexión. Por lo tanto, para un tipo específico de CLR, la implementación predeterminada del sistema de tipos XAML puede exponer el esquema XAML de ese tipo y sus miembros y notificarlo en términos del sistema de tipos XAML. En el sistema de tipos XAML de forma predeterminada, el concepto de capacidad de asignación de tipos se asigna a la herencia de CLR y los conceptos de instancias, los tipos de valor y así sucesivamente también se asignan a los comportamientos de compatibilidad y las características de CLR.  
  
## <a name="reference-for-xaml-language-features"></a>Referencia de características del lenguaje XAML  
 Para admitir XAML, los servicios XAML de .NET Framework proporciona una implementación específica de los conceptos del lenguaje XAML definido para el espacio de nombres XAML de lenguaje XAML. Estos se documentan como páginas de referencia específica. Las características del lenguaje se documentan desde la perspectiva de cómo se comportan estas características del lenguaje cuando se procesan mediante un lector XAML o sistema de escritura XAML que se define por los servicios XAML de .NET Framework. Para obtener más información, consulte [XAML Namespace (x:) Características del lenguaje](xaml-namespace-x-language-features.md).
