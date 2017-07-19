---
title: "Default XAML Schema Context and WPF XAML Schema Context | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# Default XAML Schema Context and WPF XAML Schema Context
Un contexto de esquema XAML es una entidad conceptual que califica cómo la producción de XAML que utiliza un vocabulario XAML determinado interactúa con el comportamiento de escritura de objetos, como la forma en que se resuelve la asignación de tipos, cómo se cargan los ensamblados, y cómo se interpretan determinadas configuraciones de lector y escritor.  En este tema se describen las características de los servicios XAML de .NET Framework y el contexto de esquema XAML predeterminado asociado, que se basa en el sistema de tipos de CLR.  En este tema también se describe el contexto de esquema XAML que se utiliza para WPF.  
  
## Contexto de esquema XAML predeterminado  
 Los servicios XAML de .NET Framework implementan y utilizan un contexto de esquema XAML predeterminado.  El comportamiento del contexto de esquema XAML predeterminado no siempre es totalmente visible en la API de la clase <xref:System.Xaml.XamlSchemaContext>.  Sin embargo, en muchos casos, el comportamiento en el que influye el contexto de esquema XAML predeterminado es observable a través de la API común del sistema de tipos de XAML, como los miembros de <xref:System.Xaml.XamlMember> o <xref:System.Xaml.XamlType>, o a través de las API expuestas en los lectores y escritores de XAML que están utilizando el contexto de esquema XAML predeterminado.  
  
 Puede crear <xref:System.Xaml.XamlSchemaContext> que encapsule el comportamiento predeterminado mediante una llamada al constructor de <xref:System.Xaml.XamlSchemaContext>.  Esto crea explícitamente el contexto de esquema XAML predeterminado.  El mismo contexto de esquema XAML predeterminado se crea implícitamente si se inicializa un lector de XAML o un sistema de escritura XAML mediante API que no toman un parámetro de entrada <xref:System.Xaml.XamlSchemaContext> explícitamente.  
  
 El contexto de esquema XAML predeterminado depende de la reflexión de CLR para su comportamiento de asignación de tipos.  Esto incluye examinar el elemento <xref:System.Reflection.PropertyInfo> de definición de CLR y los objetos <xref:System.Type> y <xref:System.Reflection.MethodInfo> relacionados.  Asimismo, se usa la atribución de CLR en tipos o miembros para completar los requisitos específicos de la información de los tipos XAML o miembros XAML que utilizan el tipo de respaldo de CLR.  El contexto de esquema XAML predeterminado no requiere técnicas de extensión del sistema de tipos, como el modelo de `Invoker`, porque la información necesaria está disponible en el sistema de tipos de CLR.  
  
 Para la lógica de carga de ensamblados, el contexto de esquema XAML predeterminado se basa principalmente en cualquier valor del ensamblado especificado en las asignaciones de espacio de nombres XAML.  Además, <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> puede sugerir un ensamblado para la carga, para escenarios como el de carga de tipos internos.  
  
## Contexto de esquema XAML de WPF  
 El contexto de esquema XAML de WPF se describe en este tema porque la implementación WPF sirve para ilustrar las clases de características que pueden presentarse mediante la implementación de un contexto de esquema XAML no predeterminado.  Además, el concepto de contexto de esquema XAML no se analiza con demasiado detalle en la documentación de WPF destinada al XAML de WPF; el comportamiento que permite el contexto de esquema XAML sólo se puede comprender totalmente si se integra con una descripción del funcionamiento del contexto de esquema XAML predeterminado.  El contexto de esquema XAML de WPF implementa el comportamiento siguiente.  
  
 **Invalidaciones de búsqueda:** WPF tiene algunos modelos de contenido para XAML donde hay propiedades de contenido de XAML que funcionan sin tener atribuido  <xref:System.Windows.Markup.ContentPropertyAttribute>.  Las invalidaciones de <xref:System.Xaml.XamlType.LookupContentProperty%2A> para WPF implementan este comportamiento.  
  
 **Aplazamiento de expresiones de WPF:** WPF incluye varias clases de expresiones que aplazan un valor hasta que esté disponible un contexto en tiempo de ejecución.  Asimismo, la expansión de la plantilla es un comportamiento en tiempo de ejecución que se basa en técnicas de aplazamiento.  
  
 **Optimizaciones de búsqueda del sistema de tipos:** WPF tiene un vocabulario y un modelo de objetos XAML muy completos, e incluye definiciones de miembros de clases base que se heredan literalmente en cientos de clases definidas en WPF.  Asimismo, WPF se expande por sí mismo en varios ensamblados.  WPF optimiza la búsqueda de tipos mediante tablas de búsqueda y otras técnicas.  Esto ofrece mejoras de rendimiento con respecto al contexto de esquema XAML predeterminado y la búsqueda de tipos basada en CLR.  Cuando los tipos no existen en una tabla de búsqueda, el comportamiento utiliza técnicas de contexto de esquema XAML que son similares al contexto de esquema XAML predeterminado.  
  
 **Extensión de XamlType y XamlMember:** WPF extiende los conceptos de propiedades con propiedades de dependencia y los conceptos de evento con eventos enrutados.  Para proporcionar a estos conceptos mayor visibilidad para las operaciones de procesamiento de XAML, WPF extiende <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>, y agrega propiedades internas que informan de las características de las propiedades de dependencia y eventos enrutados.  
  
### Acceso al contexto de esquema XAML de WPF  
 Si usa las técnicas de XAML basadas en WPF <xref:System.Windows.Markup.XamlReader?displayProperty=fullName> o <xref:System.Windows.Markup.XamlWriter?displayProperty=fullName>, ya se usa el contexto de esquema XAML de WPF en las implementaciones de lector y sistema de escritura XAML.  
  
 Si usa otras implementaciones de lector de XAML o sistema de escritura XAML que no se inicialicen con el contexto de esquema XAML de WPF, quizá pueda obtener un contexto de esquema XAML de WPF que funcione de <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=fullName>.  A continuación, se puede utilizar este valor como inicialización para otra API que use <xref:System.Xaml.XamlSchemaContext>.  Por ejemplo, podría llamar a <xref:System.Xaml.XamlXmlReader.%23ctor%2A> para la inicialización y pasar el contexto de esquema XAML de WPF.  O puede utilizar el contexto de esquema XAML de WPF para las operaciones del sistema de tipos XAML.  Esto podría incluir la construcción e inicialización de un <xref:System.Xaml.XamlType> o <xref:System.Xaml.XamlMember>, o una llamada a <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=fullName>.  
  
 Tenga en cuenta que, si tiene acceso a ciertos aspectos del XAML de WPF desde la mera perspectiva de un flujo de nodo XAML, es posible que no se hayan aplicado aún algunas de las características del marco de WPF.  Por ejemplo, todavía no se aplican las plantillas de WPF para los controles.  Así, si tiene acceso a una propiedad que en tiempo de ejecución se puede rellenar con un árbol visual completo, podría aparecer sólo un valor de propiedad que haga referencia a una plantilla.  Es posible que el contexto de servicio proporcionado para las extensiones de marcado de WPF tampoco sea preciso si no se proporciona en tiempo de ejecución, lo que puede dar lugar a excepciones al intentar escribir un gráfico de objetos.  
  
## XAML y carga de ensamblados  
 La carga de ensamblados para servicios XAML y XAML de .NET Framework se integra con el concepto de <xref:System.AppDomain> definido en CLR.  Un contexto de esquema XAML interpreta cómo cargar los ensamblados o buscar tipos en tiempo de ejecución o en tiempo de diseño, basándose en el uso de <xref:System.AppDomain> y otros factores.  La lógica es ligeramente diferente en función de si el XAML es XAML dinámico para un lector XAML, si es XAML compilado en una DLL por `XamlBuildTask` o si es BAML generado por `PresentationBuildTask` de WPF.  
  
 El contexto de esquema XAML para WPF se integra con el modelo de aplicaciones WPF que, a su vez, utiliza <xref:System.AppDomain> junto con otros factores que son detalles de implementación de WPF.  
  
#### Entrada del lector XAML \(XAML dinámico\)  
  
1.  El contexto de esquema XAML recorre en iteración el <xref:System.AppDomain> de la aplicación, en busca de un ensamblado ya cargado que coincida con todos los aspectos del nombre, a partir del último ensamblado cargado.  Si se encuentra una coincidencia, se utiliza dicho ensamblado para la resolución.  
  
2.  De lo contrario, se usa una de las técnicas siguientes basadas en la API <xref:System.Reflection.Assembly> de CLR para cargar un ensamblado:  
  
    -   Si el nombre se encuentra completo en la asignación, llame a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> por su nombre completo.  
  
    -   Si se produce un error del paso anterior, se utiliza el nombre corto \(y el token de clave pública, si existe\) para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>.  
  
    -   Si el nombre se encuentra incompleto en la asignación, llame a <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>.  
  
#### XamlBuildTask  
 `XamlBuildTask` se utiliza para [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)] y [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)].  
  
 Tenga en cuenta que las referencias de ensamblado con `XamlBuildTask` siempre son completas.  
  
1.  Llame a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> con su nombre completo.  
  
2.  Si se produce un error del paso anterior, se utiliza el nombre corto \(y el token de clave pública, si existe\) para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>.  
  
#### BAML \(PresentationBuildTask\)  
 Hay dos aspectos sobre la carga de ensamblados en lo relativo a BAML: cargar el ensamblado inicial que contiene el BAML como componente y cargar los ensamblados de respaldo para los tipos a los que se hace referencia en el BAML en producción.  
  
##### Carga de ensamblado para el marcado inicial:  
 La referencia al ensamblado desde el que se carga el marcado siempre es incompleta.  
  
1.  El contexto de esquema XAML de WPF recorre en iteración el <xref:System.AppDomain> de la aplicación WPF, en busca de un ensamblado ya cargado que coincida con todos los aspectos del nombre, a partir del último ensamblado cargado.  Si se encuentra una coincidencia, se utiliza dicho ensamblado para la resolución.  
  
2.  Si se produce un error del paso anterior, se utiliza el nombre corto \(y el token de clave pública, si existe\) para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>.  
  
##### Referencias de ensamblado por parte de los tipos BAML:  
 Las referencias de ensamblado para los tipos utilizados en el BAML en producción siempre son completas, como resultado de la tarea de compilación.  
  
1.  El contexto de esquema XAML de WPF recorre en iteración el <xref:System.AppDomain> de la aplicación WPF, en busca de un ensamblado ya cargado que coincida con todos los aspectos del nombre, a partir del último ensamblado cargado.  Si se encuentra una coincidencia, se utiliza dicho ensamblado para la resolución.  
  
2.  De lo contrario, se usa una de las técnicas siguientes para cargar un ensamblado:  
  
    -   Llame a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> con su nombre completo.  
  
    -   Si una combinación de nombre corto y token de clave pública coincide con el ensamblado desde el que se cargó el BAML, utilice dicho ensamblado.  
  
    -   Utilice el nombre corto \+ el token de clave pública para llamar a <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>.  
  
## Vea también  
 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)