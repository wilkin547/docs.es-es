---
title: Contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 2e92372de61230a98a02282cc28fc3f479cd94eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433083"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF
Un contexto de esquema XAML es una entidad conceptual que califica cómo una producción XAML que usa un vocabulario XAML determinado interactúa con el comportamiento de escritura de objetos, incluida la forma en que se resuelve la asignación de tipos, cómo se cargan los ensamblados, cómo se interpretan determinadas configuraciones de lector y escritor. En este tema se describen las características de los servicios XAML de .NET y el contexto de esquema XAML predeterminado asociado, que se basa en el sistema de tipos CLR. En este tema también se describe el contexto de esquema XAML que se usa para WPFWPF.

## <a name="default-xaml-schema-context"></a>Contexto de esquema XAML predeterminado

Los servicios XAML de .NET implementan y usan un contexto de esquema XAML predeterminado. El comportamiento de contexto de esquema XAML predeterminado <xref:System.Xaml.XamlSchemaContext> no siempre es totalmente visible en la API de la clase. Sin embargo, en muchos casos, el comportamiento que influye en el contexto de esquema <xref:System.Xaml.XamlMember> <xref:System.Xaml.XamlType>XAML predeterminado se puede observar a través de la API común del sistema de tipos XAML, como los miembros de o , o a través de las API expuestas en los lectores XAML y escritores XAML que usan el contexto de esquema XAML predeterminado.

Puede crear <xref:System.Xaml.XamlSchemaContext> un que encapsula el comportamiento <xref:System.Xaml.XamlSchemaContext> predeterminado mediante una llamada al constructor. Esto crea explícitamente el contexto de esquema XAML predeterminado. El mismo contexto de esquema XAML predeterminado se crea implícitamente, si inicializa un lector <xref:System.Xaml.XamlSchemaContext> XAML o un escritor XAML mediante API que no toman explícitamente un parámetro de entrada.

El contexto de esquema XAML predeterminado se basa en la reflexión CLR para su comportamiento de asignación de tipos. Esto incluye examinar la <xref:System.Type>definición <xref:System.Reflection.PropertyInfo> de <xref:System.Reflection.MethodInfo>CLR y relacionada o . Además, la atribución de CLR en tipos o miembros se usa para rellenar los detalles del tipo XAML o la información de miembro XAML que usa el tipo de respaldo de CLR. El contexto de esquema XAML predeterminado no requiere `Invoker` técnicas de extensión del sistema de tipos, como el patrón, porque la información necesaria está disponible en el sistema de tipos CLR.

Para la lógica de carga de ensamblados, el contexto de esquema XAML predeterminado se basa principalmente en los valores de ensamblado proporcionados en las asignaciones de espacio de nombres XAML. Además, <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> puede sugerir un ensamblado que se va a cargar, para escenarios como la carga de tipos internos.

## <a name="wpf-xaml-schema-context"></a>Contexto de esquema XAML de WPF

El contexto de esquema XAML de WPF se describe en este tema porque la implementación de WPFWPF proporciona una ilustración interesante de los tipos de características que se pueden introducir mediante la implementación de un contexto de esquema XAML no predeterminado. Además, el concepto de contexto de esquema XAML no se describe mucho en la documentación de WPF que aborda XAML de WPF; el comportamiento que habilita el contexto de esquema XAML solo puede ser totalmente comprensible si se integra con una explicación de cómo funciona el contexto de esquema XAML predeterminado. El contexto de esquema XAML de WPF implementa el siguiente comportamiento.

**Anulaciones de búsqueda:** WPFWPF tiene algunos modelos de contenido para XAML donde <xref:System.Windows.Markup.ContentPropertyAttribute> hay propiedades de contenido XAML que funcionan sin que se atribuyan. <xref:System.Xaml.XamlType.LookupContentProperty%2A>Invalidaciones para WPFWPF implementan este comportamiento.

**Aplazamiento para expresiones WPF:** WPFWPF cuenta con varias clases de expresión que aplazan un valor hasta que un contexto en tiempo de ejecución está disponible. Además, la expansión de plantillas es un comportamiento en tiempo de ejecución que se basa en técnicas de aplazamiento.

Tipo de **optimizaciones de búsqueda del sistema:** WPFWPF tiene un amplio vocabulario XAML y modelo de objetos, incluidas las definiciones de miembro de clase base que heredan literalmente cientos de clases definidas por WPFWPF. Además, WPFWPF se distribuye entre varios ensamblados. WPFWPF optimiza su búsqueda de tipos mediante tablas de búsqueda y otras técnicas. Esto proporciona mejoras de rendimiento en el contexto de esquema XAML predeterminado y su búsqueda de tipos basada en CLR. En los casos en que los tipos no existen en una tabla de búsqueda, el comportamiento usa técnicas de contexto de esquema XAML que son similares al contexto de esquema XAML predeterminado.

**XamlType y XamlMember extensión:** WPFWPF extiende los conceptos de propiedad con propiedades de dependencia y los conceptos de eventos con eventos enrutados. Para dar a estos conceptos una mayor <xref:System.Xaml.XamlType> visibilidad para las operaciones de procesamiento XAML, WPFWPF extiende y <xref:System.Xaml.XamlMember>, y agrega propiedades internas que notifican las características de propiedad de dependencia y eventos enrutados.

### <a name="accessing-the-wpf-xaml-schema-context"></a>Acceso al contexto de esquema XAML de WPF

Si usa técnicas XAML basadas <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> en <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>WPF o , el contexto de esquema XAML de WPF ya está en uso en esas implementaciones de lector XAML y escritor XAML.

Si usa otras implementaciones de lector XAML o escritor XAML que no se inicializan con el contexto <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>de esquema XAML de WPF, es posible que pueda obtener un contexto de esquema XAML de WPF en funcionamiento de . A continuación, puede usar este valor como <xref:System.Xaml.XamlSchemaContext>inicialización para otra API que use un archivo . Por ejemplo, podría <xref:System.Xaml.XamlXmlReader.%23ctor%2A> llamar a la inicialización y pasar el contexto de esquema XAML de WPF. O bien, podría usar el contexto de esquema XAML de WPF para las operaciones del sistema de tipos XAML. Esto puede incluir la <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlMember>inicialización <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>de construcción de un o , o llamar a .

Tenga en cuenta que si tiene acceso a ciertos aspectos de XAML de WPF desde una perspectiva de flujo de nodo XAML puro, es posible que algunas de las capacidades del marco de WPF aún no hayan actuado. Por ejemplo, las plantillas de WPFWPF para controles aún no se aplican. Por lo tanto, si tiene acceso a una propiedad que en tiempo de ejecución se puede rellenar con un árbol visual completo, es posible que solo vea un valor de propiedad que haga referencia a una plantilla. El contexto de servicio proporcionado para las extensiones de marcado WPFWPF también puede no ser preciso si se proporciona desde una situación que no es de tiempo de ejecución y puede dar lugar a excepciones al intentar escribir un gráfico de objetos.

## <a name="xaml-and-assembly-loading"></a>XAML y carga de ensamblajes

La carga de ensamblados para los servicios XAML de <xref:System.AppDomain>XAML y .NET se integra con el concepto definido por CLR de . Un contexto de esquema XAML interpreta cómo cargar ensamblados o buscar tipos en <xref:System.AppDomain> tiempo de ejecución o en tiempo de diseño, en función del uso y otros factores. La lógica es ligeramente diferente en función de si el XAML es XAML `XamlBuildTask`suelto para un lector XAML, `PresentationBuildTask`XAML compilado en un archivo DLL por , o es BAML generado por WPFWPF .

El contexto de esquema XAML para WPFWPF se integra <xref:System.AppDomain> con el modelo de aplicación WPFWPF, que a su vez usa, así como otros factores que son detalles de implementación de WPFWPF.

#### <a name="xaml-reader-input-loose-xaml"></a>Entrada de lector XAML (XAML suelto)

01. El contexto de esquema XAML <xref:System.AppDomain> recorre en iteración el de la aplicación, buscando un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando por el ensamblado cargado más recientemente. Si se encuentra una coincidencia, ese ensamblado se utiliza para la resolución.

02. De lo contrario, se utiliza <xref:System.Reflection.Assembly> una de las siguientes técnicas basadas en la API de CLR para cargar un ensamblado:

    - Si el nombre está calificado <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> en la asignación, llame al nombre completo.

    - Si se produce un error en el paso anterior, utilice <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>el nombre corto (y el token de clave pública si está presente) para llamar a .

    - Si el nombre no está calificado <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>en la asignación, llame a .

#### <a name="xamlbuildtask"></a>XamlBuildTask

`XamlBuildTask`se utiliza para Windows Communication Foundation (WCF) y Windows Workflow Foundation.

Tenga en cuenta `XamlBuildTask` que las referencias de ensamblado a través siempre están totalmente calificadas.

1. Llame <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> al nombre completo.

2. Si se produce un error en el paso anterior, utilice <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>el nombre corto (y el token de clave pública si está presente) para llamar a .

#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)

Hay dos aspectos en la carga de ensamblados para BAML: cargar el ensamblado inicial que contiene el BAML como componente y cargar los ensamblados de respaldo de tipos para los tipos a los que hace referencia la producción de BAML.

##### <a name="assembly-load-for-initial-markup"></a>Carga de ensamblado para el marcado inicial:

La referencia al ensamblado desde el que se va a cargar el marcado siempre no está calificada.

1. El contexto de esquema XAML <xref:System.AppDomain> de WPF recorre en iteración la aplicación WPFWPF, buscando un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando por el ensamblado cargado más recientemente. Si se encuentra una coincidencia, ese ensamblado se utiliza para la resolución.

2. Si se produce un error en el paso anterior, utilice <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>el nombre corto (y el token de clave pública si está presente) para llamar a .

##### <a name="assembly-references-by-baml-types"></a>Referencias de ensamblado por tipos BAML:

Las referencias de ensamblado para los tipos utilizados en la producción de BAML siempre están totalmente calificadas, como salida de la tarea de compilación.

01. El contexto de esquema XAML <xref:System.AppDomain> de WPF recorre en iteración la aplicación WPFWPF, buscando un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando por el ensamblado cargado más recientemente. Si se encuentra una coincidencia, ese ensamblado se utiliza para la resolución.

02. De lo contrario, se utiliza una de las siguientes técnicas para cargar un ensamblado:

    - Llame <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> al nombre completo.
  
    - Si un nombre corto + combinación de token de clave pública coincide con el ensamblado desde el que se cargó el BAML, use ese ensamblado.

    - Use el nombre corto + <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>token de clave pública para llamar a .

## <a name="see-also"></a>Consulte también

- [Introducción a las estructuras y conceptos de secuencias de nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
