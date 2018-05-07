---
title: Contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 9ec161c3af3c2555e04e479fec85c48f90830a87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF
Un contexto de esquema XAML es una entidad conceptual que califica cómo una producción de XAML que usa un vocabulario XAML determinado interactúa con el objeto de escritura de comportamiento, incluido cómo resuelve asignación de tipos, cómo se cargan los ensamblados, cómo ciertos lector y escritor se interpreta la configuración. En este tema se describe las características de los servicios XAML de .NET Framework y el contexto de esquema XAML predeterminado asociado, que se basa en el sistema de tipos CLR. Este tema también describe el contexto de esquema XAML que se usa para WPF.  
  
## <a name="default-xaml-schema-context"></a>Contexto de esquema XAML predeterminado  
 Los servicios XAML de .NET framework implementa y utiliza un contexto de esquema XAML predeterminado. El comportamiento predeterminado del contexto de esquema XAML no siempre es totalmente visible en la API de la <xref:System.Xaml.XamlSchemaContext> clase. Sin embargo, en muchos casos, el comportamiento que influye en el contexto de esquema XAML predeterminado es observable a través de API comunes del sistema de tipos XAML, como los miembros de <xref:System.Xaml.XamlMember> o <xref:System.Xaml.XamlType>, o a través de las API expuestas en los lectores y escritores XAML que están usando el contexto de esquema XAML predeterminado.  
  
 Puede crear un <xref:System.Xaml.XamlSchemaContext> que encapsule el comportamiento predeterminado mediante una llamada a la <xref:System.Xaml.XamlSchemaContext> constructor. Esto crea explícitamente el contexto de esquema XAML predeterminado. El mismo contexto de esquema XAML de forma predeterminada se crea implícitamente, si inicializa un lector XAML o el escritor de XAML mediante las API que no toman explícitamente un <xref:System.Xaml.XamlSchemaContext> parámetro de entrada.  
  
 El contexto de esquema XAML predeterminado se basa en la reflexión de CLR de su comportamiento de asignación de tipo. Esto incluye Examinar definición CLR <xref:System.Type>y relacionados <xref:System.Reflection.PropertyInfo> o <xref:System.Reflection.MethodInfo>. Además, atribución de CLR en tipos o miembros se utiliza para rellenar los detalles de tipo XAML o información de miembro XAML que utiliza el tipo de respaldo de CLR. El contexto de esquema XAML predeterminado no requiere técnicas de extensión de sistema de tipos, como la `Invoker` de patrón, porque la información necesaria está disponible desde el sistema de tipos CLR.  
  
 Para la lógica de carga de ensamblados, el contexto de esquema XAML predeterminado se basa principalmente en los valores de ensamblado que se proporcionen en asignaciones de espacio de nombres XAML. Además, <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> puede sugerencia un ensamblado que se va a cargar, para escenarios como la carga de los tipos internos.  
  
## <a name="wpf-xaml-schema-context"></a>Contexto de esquema XAML de WPF  
 El contexto de esquema XAML de WPF se describe en este tema porque la implementación de WPF proporciona una ilustración interesante de los tipos de características que pueden producirse al implementar un contexto de esquema XAML no predeterminado. Además, el concepto de contexto de esquema XAML no se explica mucho en la documentación de WPF que dirige a XAML de WPF; el comportamiento que permite que el contexto de esquema XAML solo puede ser totalmente comprender si integrado con una explicación de cómo funciona el contexto de esquema XAML predeterminado. El contexto de esquema XAML de WPF implementa el comportamiento siguiente.  
  
 **Invalidaciones de búsqueda:** WPF tiene algunos modelos de contenido para XAML donde hay propiedades de contenido de XAML que funcionan sin necesidad de ser <xref:System.Windows.Markup.ContentPropertyAttribute> con atributos. <xref:System.Xaml.XamlType.LookupContentProperty%2A> invalidaciones de WPF implementan este comportamiento.  
  
 **Aplazamiento para las expresiones de WPF:** WPF incluye varias clases de expresiones que aplazan un valor hasta que esté disponible un contexto de tiempo de ejecución. Además, la expansión de la plantilla es un comportamiento en tiempo de ejecución que se basa en las técnicas de aplazamiento.  
  
 **Escriba las optimizaciones de búsqueda del sistema:** WPF tiene un amplio modelo de vocabulario y el objeto XAML, incluidas las definiciones de miembro de clase base que heredan a literalmente cientos de clases de WPF. Además, WPF propio se reparte entre varios ensamblados. WPF optimiza su búsqueda de tipos con tablas de búsqueda y otras técnicas. Esto proporciona mejoras de rendimiento sobre el contexto de esquema XAML predeterminado y la búsqueda de tipos basado en CLR. En casos donde los tipos no existen en una tabla de búsqueda, el comportamiento usa técnicas de contexto de esquema XAML que son similares en el contexto de esquema XAML predeterminado.  
  
 **Extensión XamlType y XamlMember:** WPF amplía los conceptos de propiedad con las propiedades de dependencia y conceptos de eventos con los eventos enrutan. Para obtener estos conceptos una mayor visibilidad para las operaciones de procesamiento de XAML, WPF amplía <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>y agrega las propiedades internas que informan de la propiedad de dependencia y enrutan las características del evento.  
  
### <a name="accessing-the-wpf-xaml-schema-context"></a>Obtener acceso al contexto de esquema XAML de WPF  
 Si está utilizando técnicas XAML que se basan en WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> o <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>, el contexto de esquema XAML de WPF ya está en uso en esos lector de XAML y las implementaciones de sistema de escritura XAML.  
  
 Si usas otro lector de XAML o las implementaciones de sistema de escritura XAML que no inicialicen con el contexto de esquema XAML de WPF, es posible que pueda obtener un trabajo de XAML de WPF en el contexto de esquema de <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>. A continuación, puede utilizar este valor como la inicialización de otra API que usan un <xref:System.Xaml.XamlSchemaContext>. Por ejemplo, podría llamar a <xref:System.Xaml.XamlXmlReader.%23ctor%2A> para inicialización y pase el contexto de esquema XAML de WPF. O bien, podría utilizar el contexto de esquema XAML de WPF para las operaciones de sistema de tipos XAML. Esto puede incluir la inicialización de la construcción de un <xref:System.Xaml.XamlType> o <xref:System.Xaml.XamlMember>, o llamar a <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>.  
  
 Tenga en cuenta que si tiene acceso a ciertos aspectos de XAML de WPF desde un perspectivas del flujo de nodo XAML puro, algunas de las capacidades de marco WPF que no haya actuado todavía. Por ejemplo, plantillas WPF para los controles no se han aplicado. Por lo tanto si tiene acceso a una propiedad que, en tiempo de ejecución, puede estar rellena con un árbol visual completa, solo verá un valor de propiedad que hace referencia a una plantilla. El contexto de servicio que se proporcionan para que las extensiones de marcado WPF no también podría ser preciso si proporcionada a partir de una situación no en tiempo de ejecución y puede producir excepciones cuando se intenta escribir un gráfico de objetos.  
  
## <a name="xaml-and-assembly-loading"></a>XAML y cargar ensamblados  
 Carga de XAML y servicios XAML de .NET Framework del ensamblado se integra con el concepto definido por el CLR de <xref:System.AppDomain>. Un contexto de esquema XAML interpreta cómo cargar ensamblados o buscar tipos en tiempo de ejecución o en tiempo de diseño, basándose en el uso de <xref:System.AppDomain> y otros factores. La lógica es ligeramente diferente dependiendo de si el XAML es XAML dinámico para un lector XAML, es XAML compilado en un archivo DLL por `XamlBuildTask`, o se ha generado BAML de WPF `PresentationBuildTask`.  
  
 El contexto de esquema XAML de WPF se integra con el modelo de aplicaciones de WPF, que a su vez usa <xref:System.AppDomain> , así como otros factores que se muestran los detalles de implementación de WPF.  
  
#### <a name="xaml-reader-input-loose-xaml"></a>Entrada de lector XAML (XAML dinámico)  
  
1.  El contexto de esquema XAML recorre en iteración la <xref:System.AppDomain> de la aplicación, busca un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando desde el más recientemente carga ensamblados. Si se encuentra una coincidencia, se usa para la resolución de dicho ensamblado.  
  
2.  En caso contrario, una de las técnicas siguientes se basa en CLR <xref:System.Reflection.Assembly> API se utilizan para cargar un ensamblado:  
  
    -   Si el nombre está calificado en la asignación, llame a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> en el nombre completo.  
  
    -   Si se produce un error en el paso anterior, use el nombre corto (y el token de clave pública, si está presente) para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
    -   Si el nombre es unqualified en la asignación, llame a <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
#### <a name="xamlbuildtask"></a>XamlBuildTask  
 `XamlBuildTask` se usa para Windows Communication Foundation (WCF) y Windows Workflow Foundation.  
  
 Tenga en cuenta que el ensamblado que hace referencia a través de `XamlBuildTask` siempre son nombres completos.  
  
1.  Llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> en el nombre completo.  
  
2.  Si se produce un error en el paso anterior, use el nombre corto (y el token de clave pública, si está presente) para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)  
 Hay dos aspectos para cargar ensamblados para BAML: cargar el ensamblado inicial que contiene el BAML como un componente y cargar los ensamblados de copias de seguridad de tipo para cualquier tipo al que hace referencia la producción BAML.  
  
##### <a name="assembly-load-for-initial-markup"></a>Carga de ensamblado para el marcado inicial:  
 La referencia al ensamblado que se va a cargar el marcado siempre es unqualified.  
  
1.  El contexto de esquema XAML de WPF recorre en iteración la <xref:System.AppDomain> de la aplicación de WPF, busca un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando desde el más recientemente carga ensamblados. Si se encuentra una coincidencia, se usa para la resolución de dicho ensamblado.  
  
2.  Si se produce un error en el paso anterior, use el nombre corto (y el token de clave pública, si está presente) para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
##### <a name="assembly-references-by-baml-types"></a>Referencias de ensamblado por tipos BAML:  
 Las referencias de ensamblado para los tipos utilizados en la producción de BAML siempre son nombres completos, como una salida de la tarea de compilación.  
  
1.  El contexto de esquema XAML de WPF recorre en iteración la <xref:System.AppDomain> de la aplicación de WPF, busca un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando desde el más recientemente carga ensamblados. Si se encuentra una coincidencia, se usa para la resolución de dicho ensamblado.  
  
2.  En caso contrario, una de las técnicas siguientes se usa para cargar un ensamblado:  
  
    -   Llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> en el nombre completo.  
  
    -   Si un nombre corto pública combinación + tecla token coincide con el ensamblado que se cargó el BAML de, utilice ese ensamblado.  
  
    -   Usar nombre corto + token de clave pública para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las estructuras y conceptos de secuencias de nodo XAML](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
