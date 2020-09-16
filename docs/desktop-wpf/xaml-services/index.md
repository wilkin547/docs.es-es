---
title: Servicios XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: 313cb46813d8c0cfa9f1f317a65d2e21298ecff9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552855"
---
# <a name="xaml-services"></a>Servicios XAML

En este tema se describen las capacidades de un conjunto de tecnología conocido como Servicios XAML de .NET. La mayoría de los servicios y las API que se describen se encuentran en el ensamblado `System.Xaml`. Los servicios incluyen lectores y escritores, clases de esquema y compatibilidad con esquemas, generadores, atribución de clases, compatibilidad intrínseca del lenguaje XAML y otras características del lenguaje XAML.

## <a name="about-this-documentation"></a>Acerca de esta documentación

La documentación conceptual de los Servicios XAML de .NET presupone que tiene experiencia previa con el lenguaje XAML y cómo se puede aplicar a un marco concreto, por ejemplo Windows Presentation Foundation (WPF) o Windows Workflow Foundation, o un área de características de tecnología específica, por ejemplo, las características de personalización de compilación de <xref:Microsoft.Build.Framework.XamlTypes>. En esta documentación no se intentan explicar los aspectos básicos de XAML como lenguaje de marcado, la terminología de la sintaxis XAML ni otro material introductorio, sino que se centra en el uso específico de los Servicios XAML de .NET que están habilitados en la biblioteca del ensamblado System.Xaml. La mayoría de estas API son para escenarios de integración y extensibilidad del lenguaje XAML. Esto puede incluir cualquiera de los siguientes escenarios:

- Extensión de las capacidades de los lectores o escritores XAML base (procesamiento directo de la secuencia de nodo XAML; derivación del lector o escritor XAML propio).

- Definición de tipos personalizados que se pueden usar en XAML y que no tienen dependencias de marco específicas y atribución de los tipos para transmitir sus características del sistema de tipos XAML a los Servicios XAML de .NET.

- Hospedaje de lectores o escritores XAML como componente de una aplicación, como un diseñador visual o un editor interactivo para orígenes de marcado XAML.

- Escritura de convertidores de valores XAML (extensiones de marcado; convertidores de tipos para tipos personalizados).

- Definición de un contexto de esquema XAML personalizado (mediante técnicas alternativas de carga de ensamblados para orígenes de tipo de respaldo; uso de técnicas de búsqueda de tipos conocidos en lugar de reflejar siempre los ensamblados; uso de conceptos de ensamblados cargados que no usan el Common Language Runtime (CLR) `AppDomain` y su modelo de seguridad asociado).

- Extensión del sistema de tipos XAML base.

- Uso de las técnicas `Lookup` o `Invoker` para influir en el sistema de tipos XAML y en el modo en que se evalúan los respaldos de tipos.

Si busca material introductorio sobre XAML como lenguaje, puede probar [Información general sobre XAML (WPF)](../fundamentals/xaml.md). En ese tema se habla de XAML para una audiencia sin experiencia en Windows Presentation Foundation (WPF) ni en el uso de marcado XAML y características del lenguaje XAML. Otro documento útil es el material introductorio de la [especificación del lenguaje XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="net-xaml-services-and-systemxaml-in-the-net-architecture"></a>Servicios XAML de .NET y `System.Xaml` en la arquitectura .NET

Los Servicios XAML de .NET y el ensamblado `System.Xaml` definen gran parte de lo que se necesita para admitir características del lenguaje XAML. Esto incluye las clases base para los lectores y los escritores XAML. La característica más importante que se ha agregado a los Servicios XAML de .NET y que no estaba presente en ninguna de las implementaciones de XAML específicas del marco es una representación del sistema de tipos para XAML. La representación del sistema de tipos presenta XAML de una manera orientada a objetos que se centra en las capacidades de XAML sin tomar dependencias en capacidades específicas de los marcos.

El sistema de tipos XAML no está limitado por el formulario de marcado ni los detalles de tiempo de ejecución del origen XAML; tampoco está limitado por ningún sistema de tipos de respaldo específico. El sistema de tipos XAML incluye representaciones de objetos para tipos, miembros, contextos de esquema XAML, conceptos de nivel XML y otros conceptos del lenguaje XAML o intrínsecos de XAML. El uso o la extensión del sistema de tipos XAML permite derivar de clases como lectores y escritores XAML, y extender la funcionalidad de las representaciones XAML a características específicas habilitadas por un marco, una tecnología o una aplicación que usa o emite XAML. El concepto de contexto de esquema XAML habilita operaciones prácticas de escritura de gráfico de objetos a partir de la combinación de una implementación del escritor de objetos XAML, el sistema de tipos de respaldo de una tecnología según la comunicación por medio de la información de ensamblado en el contexto y el origen del nodo XAML. Para obtener más información sobre el concepto de esquema XAML, vea [Contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF](default-schema-context.md).

## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>Secuencias de nodo XAML, lectores XAML y escritores XAML

Para entender el rol que desempeñan los Servicios XAML de .NET en la relación entre el lenguaje XAML y tecnologías específicas que usan XAML como lenguaje, es útil comprender el concepto de secuencia de nodo XAML y cómo ese concepto conforma la API y la terminología. La secuencia de nodo XAML es un intermedio conceptual entre una representación del lenguaje XAML y el gráfico de objetos que XAML representa o define.

- Un lector XAML es una entidad que procesa XAML de alguna forma y genera una secuencia de nodo XAML. En la API, la clase base <xref:System.Xaml.XamlReader> representa un lector XAML.

- Un escritor XAML es una entidad que procesa una secuencia de nodo XAML y genera otra cosa. En la API, la clase base <xref:System.Xaml.XamlWriter> representa un escritor XAML.

  Los dos escenarios más comunes de XAML son la carga de XAML para crear una instancia de un gráfico de objetos y el guardado de un gráfico de objetos de una aplicación o herramienta y la generación de una representación XAML (normalmente en formato de marcado guardado como archivo de texto). La carga de XAML y la creación de un gráfico de objetos a veces se mencionan en esta documentación como la ruta de carga. El guardado o la serialización de un gráfico de objetos existente en XAML a veces se menciona en esta documentación como la ruta de guardado.

  El tipo más común de ruta de carga se puede describir de la siguiente manera:

- Comience con una representación XAML en formato XML con codificación UTF y guardada como un archivo de texto.

- Cargue ese XAML en <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader> es una subclase de <xref:System.Xaml.XamlReader>.

- El resultado es una secuencia de nodo XAML. Puede acceder a nodos individuales de la secuencia de nodo XAML mediante la API <xref:System.Xaml.XamlXmlReader> / <xref:System.Xaml.XamlReader>. La operación más típica consiste en avanzar por la secuencia de nodo XAML y procesar cada nodo mediante una metáfora de "registro actual".

- Pase los nodos resultantes de la secuencia de nodo XAML a una API <xref:System.Xaml.XamlObjectWriter>. <xref:System.Xaml.XamlObjectWriter> es una subclase de <xref:System.Xaml.XamlWriter>.

- <xref:System.Xaml.XamlObjectWriter> escribe un gráfico de objetos, objeto a objeto, de acuerdo con el progreso a través de la secuencia de nodo XAML de origen. La escritura de objetos se realiza con la ayuda de un contexto de esquema XAML y una implementación que puede acceder a los ensamblados y tipos de un sistema de tipos de respaldo y un marco.

- Llame a <xref:System.Xaml.XamlObjectWriter.Result%2A> al final de la secuencia de nodo XAML para obtener el objeto raíz del gráfico de objetos.

  El tipo más común de ruta de guardado se puede describir de la siguiente manera:

- Comience con el gráfico de objetos de un entorno de ejecución de aplicación completo, el contenido y el estado de la interfaz de usuario de un entorno de ejecución, o un segmento más pequeño de la representación de objeto de una aplicación global en tiempo de ejecución.

- En un objeto de inicio lógico, como una raíz de aplicación o una raíz de documento, cargue los objetos en <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader> es una subclase de <xref:System.Xaml.XamlReader>.

- El resultado es una secuencia de nodo XAML. Puede acceder a nodos individuales de la secuencia de nodo XAML mediante la API <xref:System.Xaml.XamlObjectReader> y <xref:System.Xaml.XamlReader>. La operación más típica consiste en avanzar por la secuencia de nodo XAML y procesar cada nodo mediante una metáfora de "registro actual".

- Pase los nodos resultantes de la secuencia de nodo XAML a una API <xref:System.Xaml.XamlXmlWriter>. <xref:System.Xaml.XamlXmlWriter> es una subclase de <xref:System.Xaml.XamlWriter>.

- <xref:System.Xaml.XamlXmlWriter> escribe XAML en una codificación UTF de XML. Puede guardarlo como un archivo de texto, como una secuencia o en otros formatos.

- Llame a <xref:System.Xaml.XamlXmlWriter.Flush%2A> para obtener el resultado final.

Para obtener más información sobre conceptos de la secuencia de nodo XAML, vea [Introducción a las estructuras y conceptos de secuencia de nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md).

### <a name="the-xamlservices-class"></a>Clase XamlServices

No siempre es necesario tratar con una secuencia de nodo XAML. Si quiere una ruta de carga básica o una ruta de guardado básica, puede usar API de la clase <xref:System.Xaml.XamlServices>.

- Varias firmas de <xref:System.Xaml.XamlServices.Load%2A> implementan una ruta de carga. Para cargar un archivo o una secuencia o para cargar un elemento <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> o <xref:System.Xaml.XamlReader> que encapsule la entrada XAML, cargue con las API de ese lector.

- Varias firmas de <xref:System.Xaml.XamlServices.Save%2A> guardan un gráfico de objetos y generan el resultado como una secuencia, un archivo o una instancia <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter>.

- <xref:System.Xaml.XamlServices.Transform%2A> convierte XAML al vincular una ruta de carga y otra de guardado como una única operación. Puede usarse un contexto de esquema o un sistema de tipos de respaldo diferente para <xref:System.Xaml.XamlReader> y <xref:System.Xaml.XamlWriter>, lo que influye en cómo se transforma el XAML resultante.

Para obtener más información sobre cómo usar <xref:System.Xaml.XamlServices>, vea [Clase XAMLServices y lectura o escritura XAML básica](basic-reading-writing.md).

## <a name="xaml-type-system"></a>Sistema de tipos XAML

El sistema de tipos XAML proporciona las API necesarias para trabajar con un nodo individual determinado de una secuencia de nodo XAML.

<xref:System.Xaml.XamlType> es la representación de un objeto, lo que se está procesando entre un nodo de objeto de inicio y un nodo de objeto final.

<xref:System.Xaml.XamlMember> es la representación de un miembro de un objeto, lo que se está procesando entre un nodo de miembro de inicio y un nodo de miembro final.

API como <xref:System.Xaml.XamlType.GetAllMembers%2A>, <xref:System.Xaml.XamlType.GetMember%2A> y <xref:System.Xaml.XamlMember.DeclaringType%2A> comunican las relaciones entre <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>.

El comportamiento predeterminado del sistema de tipos XAML según la implementación de los Servicios XAML de .NET se basa en Common Language Runtime (CLR) y el análisis estático de tipos CLR de los ensamblados mediante la reflexión. Por consiguiente, en un tipo CLR concreto, la implementación predeterminada del sistema de tipos XAML puede exponer el esquema XAML de ese tipo y sus miembros y notificarlo en términos del sistema de tipos XAML. En el sistema de tipos XAML predeterminado, el concepto de transferibilidad de tipos se asigna a la herencia de CLR, y los conceptos de instancias, tipos de valor, etc. también se asignan a los comportamientos y características de compatibilidad de CLR.

## <a name="reference-for-xaml-language-features"></a>Referencia de las características del lenguaje XAML

Para admitir XAML, los Servicios XAML de .NET proporcionan una implementación específica de conceptos del lenguaje XAML según la definición del espacio de nombres XAML del lenguaje XAML. Estos se documentan como páginas de referencia específicas. Las características del lenguaje se documentan desde la perspectiva de cómo se comportan estas características del lenguaje cuando las procesa un lector XAML o un escritor XAML definido por los Servicios XAML de .NET. Para obtener más información, vea [Espacio de nombres de XAML (x:) del espacio de nombres de XAML (x:)](namespace-language-features.md).
