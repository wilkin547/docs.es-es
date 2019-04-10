---
title: Contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 0d6a0aa80d8490c509fa9036f88d4f6863ff040c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295606"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Contexto de esquema XAML predeterminado y contexto de esquema XAML de WPF
Un contexto de esquema XAML es una entidad conceptual que califica cómo interactúa una producción de XAML que usa un vocabulario XAML concreto con el objeto de escritura de comportamiento, incluido cómo resuelve la asignación de tipos, cómo se cargan los ensamblados, cómo ciertos lector y escritor se interpreta la configuración. En este tema se describe las características de los servicios XAML de .NET Framework y el contexto de esquema XAML predeterminado asociado, que se basa en el sistema de tipos CLR. En este tema también se describe el contexto de esquema XAML que se usa para WPF.  
  
## <a name="default-xaml-schema-context"></a>Contexto de esquema XAML predeterminado  
 Servicios XAML de .NET framework implementa tanto usa un contexto de esquema XAML predeterminado. El comportamiento predeterminado del contexto de esquema XAML no siempre es totalmente visible en la API de la <xref:System.Xaml.XamlSchemaContext> clase. Sin embargo, en muchos casos, el comportamiento que influye en el contexto de esquema XAML predeterminado es observable a través de API comunes del sistema de tipos XAML, como los miembros de <xref:System.Xaml.XamlMember> o <xref:System.Xaml.XamlType>, o a través de las API expuestas en los lectores XAML y escritores XAML que están usando el contexto de esquema XAML predeterminado.  
  
 Puede crear un <xref:System.Xaml.XamlSchemaContext> que encapsula el comportamiento predeterminado mediante una llamada a la <xref:System.Xaml.XamlSchemaContext> constructor. Esto crea explícitamente el contexto de esquema XAML predeterminado. El mismo contexto de esquema XAML de forma predeterminada se crea implícitamente, si inicializa un lector XAML o sistema de escritura XAML mediante las API que no toman explícitamente un <xref:System.Xaml.XamlSchemaContext> parámetro de entrada.  
  
 El contexto de esquema XAML predeterminado se basa en la reflexión de CLR para el comportamiento de asignación de tipo. Esto incluye el examen de la definición de CLR <xref:System.Type>y relacionados <xref:System.Reflection.PropertyInfo> o <xref:System.Reflection.MethodInfo>. Además, se utiliza la atribución de CLR en tipos o miembros con el fin de rellenar los detalles específicos para el tipo XAML o información de miembros XAML que usa el tipo de respaldo de CLR. El contexto de esquema XAML predeterminado no requiere que las técnicas de extensión de sistema de tipos, como la `Invoker` de patrón, porque la información necesaria está disponible desde el sistema de tipos CLR.  
  
 Lógica de carga de ensamblados, el contexto de esquema XAML predeterminado se basa principalmente en los valores de ensamblado proporcionados en las asignaciones de espacio de nombres XAML. Además, <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> puede sugerir un ensamblado cargar, para escenarios como la carga de tipos internos.  
  
## <a name="wpf-xaml-schema-context"></a>Contexto de esquema XAML de WPF  
 El contexto de esquema de WPF XAML se describe en este tema porque la implementación de WPF proporciona una ilustración interesante de los tipos de características que se pueden introducir mediante la implementación de un contexto de esquema XAML no predeterminado. Además, el concepto de contexto de esquema XAML no se explica mucho en la documentación de WPF que se dirige WPF XAML; el comportamiento que permite que el contexto de esquema XAML solo puede ser totalmente comprensible si integrado con una explicación de cómo funciona el contexto de esquema XAML predeterminado. El contexto de esquema de WPF XAML implementa el comportamiento siguiente.  
  
 **Invalidaciones de búsqueda:** WPF tiene algunos modelos de contenido para XAML donde hay propiedades de contenido XAML que funcionan sin necesidad de ser <xref:System.Windows.Markup.ContentPropertyAttribute> con atributos. <xref:System.Xaml.XamlType.LookupContentProperty%2A> invalidaciones de WPF implementan este comportamiento.  
  
 **Aplazamiento de las expresiones de WPF:** WPF incluye varias clases de expresión que aplazan un valor hasta que esté disponible un contexto en tiempo de ejecución. Además, la expansión de la plantilla es un comportamiento en tiempo de ejecución que se basa en las técnicas de aplazamiento.  
  
 **Escriba las optimizaciones de búsqueda del sistema:** WPF tiene un amplio modelo de vocabulario y el objeto XAML, incluyendo definiciones de miembros de clase base que heredan a literalmente cientos de clases definidas en WPF. Además, WPF sí se reparte entre varios ensamblados. WPF optimiza su búsqueda del tipo de uso de tablas de búsqueda y otras técnicas. Esto proporciona mejoras de rendimiento sobre el contexto de esquema XAML predeterminado y su búsqueda de tipo basados en CLR. En casos donde los tipos no existen en una tabla de búsqueda, el comportamiento utiliza técnicas de contexto de esquema XAML que son similares al contexto de esquema XAML predeterminado.  
  
 **Extensión XamlType y XamlMember:** WPF amplía los conceptos de propiedad con las propiedades de dependencia y conceptos de eventos con eventos enrutados. Para dar mayor visibilidad de estos conceptos para las operaciones de procesamiento de XAML, WPF amplía <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>y agrega las propiedades internas que informan de la propiedad de dependencia y enrutan las características de eventos.  
  
### <a name="accessing-the-wpf-xaml-schema-context"></a>Obtener acceso al contexto de esquema XAML de WPF  
 Si está usando las técnicas XAML que se basan en WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> o <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>, el contexto de esquema de WPF XAML ya está en uso en esos lector XAML y las implementaciones de sistema de escritura XAML.  
  
 Si usas otro lector XAML o implementaciones de sistema de escritura XAML que no inicializa con el contexto de esquema de WPF XAML, es posible que pueda obtener un funcionamiento WPF XAML desde el contexto de esquema <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>. A continuación, puede usar este valor como inicialización para otra API que usan un <xref:System.Xaml.XamlSchemaContext>. Por ejemplo, podría llamar a <xref:System.Xaml.XamlXmlReader.%23ctor%2A> para inicialización y pase el contexto de esquema de WPF XAML. O bien, puede utilizar el contexto de esquema de WPF XAML para las operaciones del sistema de tipo XAML. Esto podría incluir la inicialización de la construcción de un <xref:System.Xaml.XamlType> o <xref:System.Xaml.XamlMember>, o una llamada a <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>.  
  
 Tenga en cuenta que si tiene acceso a ciertos aspectos de WPF XAML desde una perspectivas del flujo de nodo XAML puro, algunas de las funcionalidades de marco WPF es posible que no haya actuado todavía. Por ejemplo, las plantillas WPF para los controles no se aplican aún. Por lo tanto si tiene acceso a una propiedad que, en tiempo de ejecución, se puede rellenar con un árbol visual completo, solo puede aparecer un valor de propiedad que hace referencia a una plantilla. El contexto de servicio proporcionado para las extensiones de marcado WPF no también podría ser preciso si facilitado una situación que no son de tiempo de ejecución y puede dar lugar a excepciones cuando se intenta escribir un gráfico de objetos.  
  
## <a name="xaml-and-assembly-loading"></a>XAML y carga de ensamblados  
 Carga de XAML y servicios XAML de .NET Framework del ensamblado se integra con el concepto definido por el CLR de <xref:System.AppDomain>. Un contexto de esquema XAML interpreta cómo cargar ensamblados o buscar tipos en tiempo de ejecución o en tiempo de diseño, según el uso de <xref:System.AppDomain> y otros factores. La lógica es ligeramente diferente dependiendo de si el XAML es dinámico XAML para un lector XAML, es el XAML compilado en un archivo DLL por `XamlBuildTask`, o se ha generado BAML de WPF `PresentationBuildTask`.  
  
 El contexto de esquema XAML para WPF se integra con el modelo de aplicación de WPF, que a su vez usa <xref:System.AppDomain> , así como otros factores que son los detalles de implementación de WPF.  
  
#### <a name="xaml-reader-input-loose-xaml"></a>Entrada de lector XAML (XAML flexible)  
  
1. El contexto de esquema XAML recorre la <xref:System.AppDomain> de la aplicación, busca un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando desde el más recientemente ensamblado cargado. Si se encuentra una coincidencia, se usa dicho ensamblado para la resolución.  
  
2. En caso contrario, una de las técnicas siguientes en función de CLR <xref:System.Reflection.Assembly> API se usan para cargar un ensamblado:  
  
    -   Si está calificado el nombre de la asignación, llame a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> en el nombre completo.  
  
    -   Si se produce un error en el paso anterior, use el nombre corto (y el token de clave pública si está presente) para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
    -   Si el nombre no completo en la asignación, llamar a <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
#### <a name="xamlbuildtask"></a>XamlBuildTask  
 `XamlBuildTask` se usa para Windows Communication Foundation (WCF) y Windows Workflow Foundation.  
  
 Tenga en cuenta que las referencias de ensamblado a través de `XamlBuildTask` siempre son nombres completos.  
  
1. Llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> en el nombre completo.  
  
2. Si se produce un error en el paso anterior, use el nombre corto (y el token de clave pública si está presente) para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)  
 Hay dos aspectos a la carga de ensamblados para BAML: cargar el ensamblado inicial que contiene el BAML como un componente y carga los ensamblados de respaldo de tipo para cualquier tipo al que hace referencia la producción de BAML.  
  
##### <a name="assembly-load-for-initial-markup"></a>Carga de ensamblado para el marcado inicial:  
 La referencia al ensamblado para cargar el marcado de siempre está incompleta.  
  
1. El contexto de esquema de WPF XAML recorre la <xref:System.AppDomain> de la aplicación de WPF, busca un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando desde el más recientemente ensamblado cargado. Si se encuentra una coincidencia, se usa dicho ensamblado para la resolución.  
  
2. Si se produce un error en el paso anterior, use el nombre corto (y el token de clave pública si está presente) para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
##### <a name="assembly-references-by-baml-types"></a>Referencias de ensamblado por tipos BAML:  
 Referencias de ensamblado para tipos que se usan en la producción de BAML siempre se completa, como una salida de la tarea de compilación.  
  
1. El contexto de esquema de WPF XAML recorre la <xref:System.AppDomain> de la aplicación de WPF, busca un ensamblado ya cargado que coincida con todos los aspectos del nombre, empezando desde el más recientemente ensamblado cargado. Si se encuentra una coincidencia, se usa dicho ensamblado para la resolución.  
  
2. En caso contrario, una de las técnicas siguientes se usa para cargar un ensamblado:  
  
    -   Llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> en el nombre completo.  
  
    -   Si un nombre corto + la combinación de tokens clave pública coinciden con el ensamblado que se cargó el BAML de, utilice ese ensamblado.  
  
    -   Use el nombre corto + el token de clave pública para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- [Introducción a las estructuras y conceptos de secuencias de nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
