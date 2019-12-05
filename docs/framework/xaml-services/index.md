---
title: Servicios XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: 8e1e8dc9a1410d05c19e4dd1bccb30c65d7c5e66
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837290"
---
# <a name="xaml-services"></a>Servicios XAML
En este tema se describen las capacidades de un conjunto de tecnología conocido como .NET Framework servicios XAML. La mayoría de los servicios y las API que se describen se encuentran en el ensamblado System. XAML, que es un ensamblado incluido en el .NET Framework 4 conjunto de ensamblados de .NET Core. Entre los servicios se incluyen lectores y escritores, clases de esquema y compatibilidad con esquemas, generadores, atribución de clases, compatibilidad intrínseca del lenguaje XAML y otras características del lenguaje XAML.  
  
## <a name="about-this-documentation"></a>Acerca de esta documentación  
 La documentación conceptual de los servicios de .NET Framework XAML supone que tiene experiencia previa con el lenguaje XAML y cómo se puede aplicar a un marco concreto, por ejemplo [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] o Windows Workflow Foundation, o un área de características de tecnología específica, por ejemplo, las características de personalización de compilación en <xref:Microsoft.Build.Framework.XamlTypes>. En esta documentación no se tratan los conceptos básicos de XAML como lenguaje de marcado, terminología de sintaxis de XAML u otro material introductorio. En su lugar, esta documentación se centra específicamente en el uso de los servicios de .NET Framework XAML que están habilitados en la biblioteca de ensamblados System. Xaml. La mayoría de estas API son para escenarios de integración y extensibilidad del lenguaje XAML. Esto podría incluir cualquiera de los siguientes:  
  
- Extender las capacidades de los lectores XAML base o escritores XAML (procesar el flujo de nodo XAML directamente; derivar su propio lector XAML o escritor XAML).  
  
- Definir tipos personalizados que se pueden usar en XAML y que no tienen dependencias de marco de trabajo específicas y atribuir los tipos para transmitir sus características del sistema de tipos XAML a .NET Framework servicios XAML.  
  
- Hospedar lectores XAML o escritores de XAML como un componente de una aplicación, como un diseñador visual o un editor interactivo para orígenes de marcado XAML.  
  
- Escritura de convertidores de valores XAML (extensiones de marcado; convertidores de tipos para tipos personalizados).  
  
- Definir un contexto de esquema XAML personalizado (mediante técnicas alternativas de carga de ensamblados para la copia de seguridad de los orígenes de tipos; usar técnicas de búsqueda de tipos conocidos en lugar de reflejar siempre los ensamblados; usar los conceptos de ensamblado cargados que no usan el `AppDomain` CLR y su modelo de seguridad asociado).  
  
- Extender el sistema de tipos XAML base.  
  
- Usar las técnicas `Lookup` o `Invoker` para influir en el sistema de tipos XAML y el modo en que se evalúan las copias de seguridad de tipos.  
  
 Si busca material introductorio en XAML como lenguaje, puede probar [información general sobre XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md). En este tema se describe XAML para una audiencia que es nueva para [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] y también para usar las características de marcado XAML y lenguaje XAML. Otro documento útil es el material introductorio en la [especificación del lenguaje XAML](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET Framework servicios XAML y System. XAML en la arquitectura de .NET  
 En versiones anteriores de Microsoft .NET Framework, la compatibilidad con las características del lenguaje XAML se implementaba mediante marcos que se basaban en Microsoft .NET Framework ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Windows Workflow Foundation y Windows Communication Foundation (WCF)) y, por lo tanto, se modificó en su comportamiento y la API usada en función del marco de trabajo específico que se usaba. Esto incluía el analizador XAML y su mecanismo de creación de gráficos de objetos, los intrínsecos del lenguaje XAML, la compatibilidad con la serialización, etc.  
  
 En .NET Framework 4, .NET Framework los servicios XAML y el ensamblado System. Xaml definen gran parte de lo que se necesita para admitir características del lenguaje XAML. Esto incluye las clases base para los lectores XAML y los sistemas de escritura XAML. La característica más importante agregada a .NET Framework servicios XAML que no estaba presente en ninguna de las implementaciones de XAML específicas del marco es una representación del sistema de tipos para XAML. La representación del sistema de tipos presenta XAML de una manera orientada a objetos que se centra en las funcionalidades XAML sin tener que tomar dependencias de las capacidades específicas de los marcos de trabajo.  
  
 El sistema de tipos XAML no está limitado por el formulario de marcado o los detalles de tiempo de ejecución del origen XAML. tampoco está limitado por ningún sistema de tipos de respaldo específico. El sistema de tipos XAML incluye representaciones de objeto para tipos, miembros, contextos de esquema XAML, conceptos de nivel XML y otros conceptos del lenguaje XAML o intrínsecos de XAML. El uso o la extensión del sistema de tipos XAML permite derivar de clases como lectores XAML y escritores de XAML, y ampliar la funcionalidad de las representaciones XAML en características específicas habilitadas por un marco, una tecnología o una aplicación que consume o emite XAML. El concepto de contexto de esquema XAML permite operaciones prácticas de escritura del gráfico de objetos a partir de la combinación de una implementación del escritor de objetos XAML, el sistema de tipos de respaldo de una tecnología como se comunica a través de la información de ensamblado en el contexto y el nodo XAML. fuentes. Para obtener más información sobre el concepto de esquema XAML. vea [contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF](default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>Secuencias de nodo XAML, lectores XAML y escritores de XAML  
 Para comprender el rol que .NET Framework los servicios XAML se reproducen en la relación entre el lenguaje XAML y las tecnologías específicas que usan XAML como lenguaje, resulta útil comprender el concepto de un flujo de nodo XAML y el concepto de la API. terminología. El flujo de nodo XAML es un conceptual intermedio entre una representación del lenguaje XAML y el gráfico de objetos que el XAML representa o define.  
  
- Un lector XAML es una entidad que procesa XAML de alguna forma y genera un flujo de nodo XAML. En la API, la clase base <xref:System.Xaml.XamlReader>representa un lector XAML.  
  
- Un escritor de XAML es una entidad que procesa un flujo de nodo XAML y produce otra cosa. En la API, la clase base <xref:System.Xaml.XamlWriter>representa un escritor XAML.  
  
 Los dos escenarios más comunes que implican XAML son la carga de XAML para crear una instancia de un gráfico de objetos y guardar un gráfico de objetos de una aplicación o herramienta y generar una representación XAML (normalmente en formato de marcado guardado como archivo de texto). La carga de XAML y la creación de un gráfico de objetos a menudo se conoce en esta documentación como la ruta de acceso de carga. El guardado o la serialización de un gráfico de objetos existente en XAML a menudo se conoce en esta documentación como la ruta de acceso de guardado.  
  
 El tipo más común de ruta de acceso de carga se puede describir de la siguiente manera:  
  
- Comienza con una representación XAML, en formato XML con codificación UTF y guardada como un archivo de texto.  
  
- Cargue ese XAML en <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader> es una subclase de <xref:System.Xaml.XamlReader>.  
  
- El resultado es un flujo de nodo XAML. Puede tener acceso a nodos individuales del flujo de nodo XAML mediante <xref:System.Xaml.XamlXmlReader>API de <xref:System.Xaml.XamlReader>  / . La operación más típica consiste en avanzar por el flujo de nodo XAML y procesar cada nodo mediante una metáfora "registro actual".  
  
- Pase los nodos resultantes del flujo de nodo XAML a una API de <xref:System.Xaml.XamlObjectWriter>. <xref:System.Xaml.XamlObjectWriter> es una subclase de <xref:System.Xaml.XamlWriter>.  
  
- El <xref:System.Xaml.XamlObjectWriter> escribe un gráfico de objetos, un objeto cada vez, de acuerdo con el progreso del flujo de nodo XAML de origen. Esto se hace con la ayuda de un contexto de esquema XAML y una implementación de que puede tener acceso a los ensamblados y tipos de un sistema de tipos de respaldo y un marco de trabajo.  
  
- Llame a <xref:System.Xaml.XamlObjectWriter.Result%2A> al final del flujo de nodo XAML para obtener el objeto raíz del gráfico de objetos.  
  
 El tipo más común de ruta de acceso de guardado se puede describir de la siguiente manera:  
  
- Comience con el gráfico de objetos de un tiempo de ejecución de la aplicación completo, el contenido de la interfaz de usuario y el estado de un tiempo de ejecución, o un segmento más pequeño de la representación de objeto de una aplicación global en tiempo de ejecución.  
  
- En un objeto de inicio lógico, como una raíz de la aplicación o una raíz del documento, cargue los objetos en <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader> es una subclase de <xref:System.Xaml.XamlReader>.  
  
- El resultado es un flujo de nodo XAML. Puede tener acceso a nodos individuales del flujo de nodo XAML mediante <xref:System.Xaml.XamlObjectReader> y <xref:System.Xaml.XamlReader> API. La operación más típica consiste en avanzar por el flujo de nodo XAML y procesar cada nodo mediante una metáfora "registro actual".  
  
- Pase los nodos resultantes del flujo de nodo XAML a una API de <xref:System.Xaml.XamlXmlWriter>. <xref:System.Xaml.XamlXmlWriter> es una subclase de <xref:System.Xaml.XamlWriter>.  
  
- El <xref:System.Xaml.XamlXmlWriter> escribe XAML en una codificación UTF de XML. Puede guardarlo como un archivo de texto, como una secuencia o en otros formatos.  
  
- Llame a <xref:System.Xaml.XamlXmlWriter.Flush%2A> para obtener el resultado final.  
  
 Para obtener más información sobre los conceptos de flujo de nodo XAML, vea [Descripción de las estructuras y conceptos de flujo de nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md).  
  
### <a name="the-xamlservices-class"></a>La clase XamlServices  
 No siempre es necesario tratar con un flujo de nodo XAML. Si desea una ruta de acceso de carga básica o una ruta de acceso de guardado básica, puede usar las API de la clase <xref:System.Xaml.XamlServices>.  
  
- Varias firmas de <xref:System.Xaml.XamlServices.Load%2A> implementan una ruta de acceso de carga. Puede cargar un archivo o una secuencia, o puede cargar un <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> o <xref:System.Xaml.XamlReader> que encapsulan la entrada XAML mediante la carga de las API del lector.  
  
- Varias firmas de <xref:System.Xaml.XamlServices.Save%2A> guardar un gráfico de objetos y generar la salida como una secuencia, un archivo o una <xref:System.Xml.XmlWriter>/instancia de <xref:System.IO.TextWriter>.  
  
- <xref:System.Xaml.XamlServices.Transform%2A> convierte XAML vinculando una ruta de acceso de carga y una ruta de acceso de guardado como una sola operación. Puede usarse un contexto de esquema diferente o un sistema de tipos de respaldo diferente para <xref:System.Xaml.XamlReader> y <xref:System.Xaml.XamlWriter>, que es lo que influye en cómo se transforma el XAML resultante.  
  
 Para obtener más información sobre cómo usar <xref:System.Xaml.XamlServices>, consulte la [clase XAMLServices y la lectura o escritura de XAML básica](xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## <a name="xaml-type-system"></a>Sistema de tipos XAML  
 El sistema de tipos XAML proporciona las API necesarias para trabajar con un nodo individual determinado de un flujo de nodo XAML.  
  
 <xref:System.Xaml.XamlType> es la representación de un objeto, lo que se está procesando entre un nodo de objeto de inicio y un nodo de objeto final.  
  
 <xref:System.Xaml.XamlMember> es la representación de un miembro de un objeto, lo que se está procesando entre un nodo de miembro de inicio y un nodo de miembro final.  
  
 Las API como <xref:System.Xaml.XamlType.GetAllMembers%2A> y <xref:System.Xaml.XamlType.GetMember%2A> y <xref:System.Xaml.XamlMember.DeclaringType%2A> notifican las relaciones entre un <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>.  
  
 El comportamiento predeterminado del sistema de tipos XAML tal como lo implementa .NET Framework servicios XAML se basa en el Common Language Runtime (CLR) y el análisis estático de tipos CLR en los ensamblados mediante la reflexión. Por consiguiente, para un tipo CLR concreto, la implementación predeterminada del sistema de tipos XAML puede exponer el esquema XAML de ese tipo y sus miembros y notificarlo en términos del sistema de tipos XAML. En el sistema de tipos XAML predeterminado, el concepto de asignación de tipos se asigna a la herencia de CLR y los conceptos de las instancias, los tipos de valor, etc., también se asignan a los comportamientos y características compatibles de CLR.  
  
## <a name="reference-for-xaml-language-features"></a>Referencia de las características del lenguaje XAML  
 Para admitir XAML, .NET Framework servicios XAML proporciona una implementación específica de conceptos del lenguaje XAML, tal y como se define para el espacio de nombres XAML del lenguaje XAML. Estos se documentan como páginas de referencia específicas. Las características del lenguaje se documentan desde la perspectiva de cómo se comportan estas características de lenguaje cuando las procesa un lector XAML o un escritor XAML definido por .NET Framework los servicios XAML. Para obtener más información, consulta [XAML Namespace (x:) Language Features](xaml-namespace-x-language-features.md).
