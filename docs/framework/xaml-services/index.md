---
title: "XAML Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "XAML [XAML Services], System.Xaml concepts"
  - "XAML Services in WPF [XAML Services]"
  - "System.Xaml [XAML Services], conceptual documentation"
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
caps.latest.revision: 13
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 13
---
# XAML Services
En este tema se describen las capacidades de un conjunto de tecnologías conocido como servicios XAML de .NET Framework.  La mayoría de los servicios y las API descritos se encuentran en el ensamblado System.Xaml, que es un ensamblado presentado con el conjunto [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] de ensamblados básicos de .NET.  Los servicios incluyen lectores y sistemas de escritura, clases de esquema y compatibilidad de esquema, generadores, atributos de clases, compatibilidad intrínseca con el lenguaje XAML y otras características del lenguaje XAML.  
  
## Acerca de esta documentación  
 En la documentación conceptual para los servicios XAML de .NET Framework se supone que ya tiene experiencia con el lenguaje XAML y en la forma de aplicarlo a un marco concreto, por ejemplo [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] o [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)], o a un área de característica tecnológica concreta, por ejemplo las características de personalización de compilación de <xref:Microsoft.Build.Framework.XamlTypes>.  En esta documentación no se intenta explicar los fundamentos de XAML como un lenguaje de marcado, la terminología de la sintaxis XAML ni ningún otro material preliminar.  En su lugar, esta documentación se centra en usar específicamente los Servicios XAML de .NET Framework que están habilitados en la biblioteca de ensamblados System.Xaml.  La mayoría de estas API son para los escenarios de integración y extensibilidad del lenguaje XAML.  Esto podría incluir cualquiera de los siguientes:  
  
-   Ampliar la funcionalidad de los sistemas de lectura o escritura de XAML básicos \(procesar el flujo de los nodos XAML directamente; derivar un sistema de lectura o escritura de XAML propio\).  
  
-   Definir tipos personalizados utilizables por XAML que no tienen dependencias del marco concretas y atribuir los tipos para llevar las características del sistema de tipos XAML a los Servicios XAML de .NET Framework.  
  
-   Hospedar lectores de XAML o sistemas de escritura de XAML como un componente de una aplicación, como un diseñador visual o un editor interactivo para los orígenes del marcado XAML.  
  
-   Escribir los convertidores de valores de XAML \(extensiones de marcado; convertidores de tipos para los tipos personalizados\).  
  
-   Definir un contexto de esquema XAML personalizado \(mediante técnicas alternativas de carga de ensamblados para orígenes de tipos de respaldo; mediante técnicas de búsqueda de tipos conocidos en lugar de reflejar siempre los ensamblados; mediante conceptos de ensamblado cargados que no utilizan CLR `AppDomain` y su modelo de seguridad asociado\).  
  
-   Extender el sistema de tipos XAML base.  
  
-   Usar las técnicas `Lookup` o `Invoker` para influir en el sistema de tipos XAML y en la forma en que se evalúan los respaldos de tipo.  
  
 Si busca el material preliminar sobre XAML como lenguaje, podría probar [Información general sobre XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  En ese tema se discute XAML para una audiencia que es nueva en [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], y también en el uso del marcado XAML y las características del lenguaje XAML.  Otro documento útil es el material de introducción de [XAML language specification](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## Servicios XAML de .NET Framework y System.Xaml en la arquitectura de .NET  
 En las versiones anteriores de [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)], los marcos compilados en [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] \([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] y [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)]\) implementaban la compatibilidad con las características del lenguaje XAML, que, por consiguiente, variaba en su comportamiento y en la API utilizada dependiendo de qué marco concreto se estaba usando.  Esto incluía el analizador de XAML y su mecanismo de creación de gráficos de objetos, las características intrínsecas del lenguaje XAML, la compatibilidad con la serialización, etc.  
  
 En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], los Servicios XAML de .NET Framework y el ensamblado System.Xaml definen muchos de los elementos que se necesitan para la compatibilidad con las características del lenguaje XAML.  Esto incluye las clases base para los lectores y escritores de XAML.  La característica más importante agregada a los Servicios XAML de .NET Framework que no estaba presente en ninguna de las implementaciones de XAML específicas del marco es una representación del sistema de tipos para XAML.  La representación del sistema de tipos presenta el XAML de una manera orientada a objetos que se centra en las capacidades de XAML sin incurrir en las dependencias de las capacidades concretas de marcos.  
  
 El sistema de tipos de XAML no está limitado por las características del formulario de marcado o en tiempo de ejecución del origen XAML, ni por ningún sistema de tipos de respaldo concreto.  El sistema de tipos XAML incluye las representaciones de objeto para los tipos, miembros, contextos de esquema XAML, conceptos del nivel XML y otros conceptos o características intrínsecas del lenguaje XAML.  El uso o extensión del sistema de tipos de XAML permite derivar clases como los lectores y escritores de XAML, y extender la funcionalidad de las representaciones de XAML a las características concretas habilitadas por un marco, una tecnología o una aplicación que usa o emite XAML.  El concepto de contexto de esquema XAML habilita las operaciones prácticas de escritura de gráficos de objetos a partir de la combinación de una implementación del sistema de escritura de objetos XAML, un respaldo del sistema de tipos de la tecnología, tal y como se comunica a través de la información del ensamblado en el contexto, y el origen del nodo XAML.  Para obtener más información sobre el concepto de esquema XAML,  vea [Default XAML Schema Context and WPF XAML Schema Context](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## Flujos de nodo XAML, lectores de XAML y escritores de XAML  
 Para entender el rol que los Servicios XAML de .NET Framework representan en la relación entre el lenguaje XAML y las tecnologías concretas que usan XAML como lenguaje, es útil entender el concepto de flujo de nodo XAML y cómo ese concepto da forma a la API y la terminología.  El flujo de nodo XAML es un concepto intermedio entre una representación del lenguaje XAML y el gráfico de objeto que el XAML representa o define.  
  
-   Un lector de XAML es una entidad que procesa XAML de alguna forma y genera un flujo de nodo XAML.  En la API, un lector de XAML se representa mediante la clase base <xref:System.Xaml.XamlReader>.  
  
-   Un escritor de XAML es una entidad que procesa un flujo de nodo XAML y genera algo más.  En la API, un sistema de escritura de XAML se representa mediante la clase base <xref:System.Xaml.XamlWriter>.  
  
 Los dos escenarios más comunes que implican XAML consisten en cargar XAML para crear instancias de un gráfico de objeto, y guardar un gráfico de objeto desde una aplicación o herramienta y generar una representación de XAML \(normalmente en el formulario de marcado guardado como archivo de texto\).  En esta documentación, se hace referencia a menudo a la carga de XAML y la creación de un gráfico de objeto como la ruta de acceso de la carga.  En esta documentación, se hace referencia a menudo a guardar o serializar un gráfico de objeto existente para XAML como la ruta de acceso de guardar.  
  
 El tipo más común de ruta de acceso de carga se puede describir como sigue:  
  
-   Comience con una representación de XAML, en formato XML codificado por UTF y guardado como un archivo de texto.  
  
-   Cargue ese XAML en <xref:System.Xaml.XamlXmlReader>.  <xref:System.Xaml.XamlXmlReader> es una subclase <xref:System.Xaml.XamlReader>.  
  
-   El resultado es un flujo de nodo XAML.  Puede obtener acceso a los nodos individuales del flujo de nodo XAML mediante la API de <xref:System.Xaml.XamlXmlReader> \/ <xref:System.Xaml.XamlReader>.  La operación más típica aquí es el avance a través del flujo de nodo XAML, procesando cada nodo mediante una metáfora del "registro actual".  
  
-   Pase los nodos resultantes del flujo de nodo XAML a la API de <xref:System.Xaml.XamlObjectWriter>.  <xref:System.Xaml.XamlObjectWriter> es una subclase <xref:System.Xaml.XamlWriter>.  
  
-   <xref:System.Xaml.XamlObjectWriter> escribe un gráfico de objetos, un objeto a la vez, de acuerdo con el progreso a través del flujo de nodo XAML de origen.  Esto se hace con la ayuda de un contexto de esquema XAML y una implementación que pueden obtener acceso a los ensamblados y tipos de un sistema de tipos de respaldo y un marco.  
  
-   Llame a <xref:System.Xaml.XamlObjectWriter.Result%2A> al final del flujo del nodo XAML para obtener el objeto raíz del gráfico de objetos.  
  
 El tipo más común de ruta de acceso de guardar se puede describir como sigue:  
  
-   Comience con el gráfico de objeto de un tiempo de ejecución de toda la aplicación, el contenido de la interfaz de usuario y el estado de un tiempo de ejecución o un segmento más pequeño de una representación de objeto de una aplicación general en tiempo de ejecución.  
  
-   Cargue los objetos en <xref:System.Xaml.XamlObjectReader> desde algún objeto de inicio lógico, como la raíz de la aplicación o la raíz del documento.  <xref:System.Xaml.XamlObjectReader> es una subclase <xref:System.Xaml.XamlReader>.  
  
-   El resultado es un flujo de nodo XAML.  Puede obtener acceso a los nodos individuales del flujo de nodo XAML mediante la API de <xref:System.Xaml.XamlObjectReader> y <xref:System.Xaml.XamlReader>.  La operación más típica aquí es el avance a través del flujo de nodo XAML, procesando cada nodo mediante una metáfora del "registro actual".  
  
-   Pase los nodos resultantes del flujo de nodo XAML a la API de <xref:System.Xaml.XamlXmlWriter>.  <xref:System.Xaml.XamlXmlWriter> es una subclase <xref:System.Xaml.XamlWriter>.  
  
-   <xref:System.Xaml.XamlXmlWriter> escribe XAML en una codificación UTF de XML.  Puede guardar esto como un archivo de texto, como una secuencia o en otros formularios.  
  
-   Llame a <xref:System.Xaml.XamlXmlWriter.Flush%2A> para obtener el resultado final.  
  
 Para obtener más información sobre los conceptos de flujo de nodo XAML, vea [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
### Clase XamlServices  
 No siempre es necesario tratar con un flujo de nodo XAML.  Si desea una ruta de acceso de carga básica o una ruta de acceso de guardar básica, puede usar la API de la clase <xref:System.Xaml.XamlServices>.  
  
-   Varias firmas de <xref:System.Xaml.XamlServices.Load%2A> implementan una ruta de acceso de carga.  Puede cargar un archivo o flujo, o puede cargar un objeto <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> o <xref:System.Xaml.XamlReader> que ajustan su entrada XAML cargándose con las API de ese lector.  
  
-   Varias firmas de <xref:System.Xaml.XamlServices.Save%2A> guardan un gráfico de objeto y generan el resultado como un flujo, archivo o instancia de <xref:System.Xml.XmlWriter>\/<xref:System.IO.TextWriter>.  
  
-   <xref:System.Xaml.XamlServices.Transform%2A> convierte XAML vinculando una ruta de acceso de carga y una ruta de acceso de guardar como una sola operación.  Se podría usar un contexto de esquema diferente o un sistema de tipos de respaldo diferente para <xref:System.Xaml.XamlReader> y <xref:System.Xaml.XamlWriter>, que son lo que afecta a cómo se transforma el XAML resultante.  
  
 Para obtener más información acerca de cómo se usa <xref:System.Xaml.XamlServices>, vea [XAMLServices Class and Basic XAML Reading or Writing](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## Sistema de tipos XAML  
 El sistema de tipos XAML proporciona las API que se necesitan para trabajar con un nodo individual determinado de un flujo de nodo XAML.  
  
 <xref:System.Xaml.XamlType> es la representación para un objeto: lo que se está procesando entre un nodo de objeto de inicio y un nodo de objeto de fin.  
  
 <xref:System.Xaml.XamlMember> es la representación para un miembro de un objeto: lo que se está procesando entre un nodo de miembro de inicio y un nodo de miembro de fin.  
  
 Las API como <xref:System.Xaml.XamlType.GetAllMembers%2A>, <xref:System.Xaml.XamlType.GetMember%2A> y <xref:System.Xaml.XamlMember.DeclaringType%2A> notifican las relaciones entre <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>.  
  
 El comportamiento predeterminado del sistema de tipos XAML, tal y como se implementa mediante los Servicios XAML de .NET Framework, está basado en Common Language Runtime \(CLR\) y el análisis estático de los tipos CLR de los ensamblados mediante la reflexión.  En consecuencia, para un tipo CLR determinado, la implementación predeterminada del sistema de tipos de XAML puede exponer el esquema XAML de ese tipo y sus miembros y notificarlo en términos del sistema de tipos XAML.  En el sistema de tipos XAML predeterminado, el concepto de posibilidad de asignación de tipos se refiere a la herencia de CLR, y los conceptos de instancias, tipos de valor, etc. se refieren a los comportamientos de compatibilidad y las características de CLR.  
  
## Referencia de las características del lenguaje XAML  
 Para admitir XAML, los Servicios XAML de .NET Framework proporcionan una implementación concreta de los conceptos del lenguaje XAML, tal y como se definen para el espacio de nombres XAML del lenguaje XAML.  Estos se documentan como páginas de referencia concretas.  Las características del lenguaje se documentan desde la perspectiva de cómo se comportan cuando las procesa un lector de XAML o un sistema de escritura de XAML definido mediante los Servicios XAML de .NET Framework.  Para obtener más información, vea [XAML Namespace \(x:\) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).