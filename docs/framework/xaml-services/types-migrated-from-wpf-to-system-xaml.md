---
title: Tipos migrados de WPF a System.Xaml
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 943cdb2a21cbf2f95ef7fe2feefe6c0e71f57be4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939682"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>Tipos migrados de WPF a System.Xaml
En .NET Framework 3,5 y .NET Framework 3,0, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] y Windows Workflow Foundation incluyen una implementación del lenguaje XAML. Muchos de los tipos públicos que proporcionaban extensibilidad para la implementación XAML de WPF existían en los ensamblados de WindowsBase, PresentationCore y PresentationFramework. Del mismo modo, los tipos públicos que proporcionaban extensibilidad para Windows Workflow Foundation XAML existían en el ensamblado System. Workflow. ComponentModel. En el .NET Framework 4, algunos de los tipos relacionados con XAML se migran al ensamblado System. Xaml. Una implementación .NET Framework común de los servicios de lenguaje XAML habilita muchos escenarios de extensibilidad de XAML que se definieron originalmente en la implementación XAML de un marco concreto, pero ahora forman parte de la compatibilidad con el lenguaje XAML de .NET Framework 4. En este tema se enumeran los tipos que se han migrado y se describen los problemas relacionados con la migración.  
  
<a name="assemblies_and_namespaces"></a>   
## <a name="assemblies-and-namespaces"></a>Nombres de ensamblados y espacios de nombres  
 En .NET Framework 3,5 y .NET Framework 3,0, los tipos que WPF implementaba para admitir XAML estaban generalmente en <xref:System.Windows.Markup> el espacio de nombres. La mayoría de estos tipos estaban en el ensamblado WindowsBase.  
  
 En .NET Framework 4, hay un nuevo <xref:System.Xaml> espacio de nombres y un nuevo ensamblado System. Xaml. Muchos de los tipos que se implementaron originalmente para XAML de WPF se proporcionan ahora como puntos o servicios de extensibilidad para cualquier implementación de XAML. Para contribuir a que estén disponibles para escenarios más generales, los tipos se reenvían desde su ensamblado WPF original al ensamblado System.Xaml. Esto permite escenarios de extensibilidad de XAML sin tener que incluir los ensamblados de otros marcos (como WPF y Windows Workflow Foundation).  
  
 En cuanto a los tipos migrados, la mayoría de los tipos permanece en el espacio de nombres <xref:System.Windows.Markup> . En parte, esto se hizo para evitar interrumpir las asignaciones de espacio de nombres de CLR en las implementaciones existentes archivo por archivo. Como resultado, el <xref:System.Windows.Markup> espacio de nombres de .NET Framework 4 contiene una mezcla de tipos de soporte de lenguaje XAML generales (del ensamblado System. xaml) y tipos que son específicos de la implementación XAML de WPF (de WindowsBase y otros ensamblados de WPF). Todo tipo que se ha migrado a System.Xaml, pero existía anteriormente en un ensamblado de WPF, tiene compatibilidad de reenvío de tipos en la versión 4 del ensamblado de WPF.  
  
### <a name="workflow-xaml-support-types"></a>Tipos de soporte de XAML en Workflow  
 Windows Workflow Foundation también proporcionan tipos de compatibilidad con XAML y, en muchos casos, tenían nombres cortos idénticos a un equivalente de WPF. A continuación se muestra una lista de los tipos de compatibilidad con XAML Windows Workflow Foundation:  
  
- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>  
  
 Estos tipos de soporte siguen existiendo en los ensamblados de Windows Workflow Foundation para .NET Framework 4 y todavía se pueden usar para aplicaciones Windows Workflow Foundation específicas; sin embargo, las aplicaciones o marcos que no usan Windows Workflow Foundation no deben hacer referencia a ellos.  
  
<a name="markupextension"></a>   
## <a name="markupextension"></a>MarkupExtension  
 En el .NET Framework 3,5 y .NET Framework 3,0, la <xref:System.Windows.Markup.MarkupExtension> clase para WPF estaba en el ensamblado WindowsBase. Existe una clase paralela para Windows Workflow Foundation <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>,, en el ensamblado System. Workflow. ComponentModel. En el .NET Framework 4, la <xref:System.Windows.Markup.MarkupExtension> clase se migra al ensamblado System. Xaml. En el .NET Framework 4, <xref:System.Windows.Markup.MarkupExtension> está pensado para cualquier escenario de extensibilidad de XAML que use .NET Framework servicios XAML, no solo para los que se basan en marcos de trabajo específicos. Siempre que sea posible, los marcos específicos y el código de usuario del marco deben compilarse también en la clase <xref:System.Windows.Markup.MarkupExtension> para la extensión XAML.  
  
<a name="markupextension_supporting_service_classes"></a>   
## <a name="markupextension-supporting-service-classes"></a>Clases de servicio de soporte de MarkupExtension  
 .NET Framework 3,5 y .NET Framework 3,0 para WPF proporcionan varios servicios que estaban disponibles para <xref:System.Windows.Markup.MarkupExtension> los implementadores <xref:System.ComponentModel.TypeConverter> e implementaciones con el fin de admitir el uso de tipo y propiedad en XAML. Estos servicios son los siguientes:  
  
- <xref:System.Windows.Markup.IProvideValueTarget>  
  
- <xref:System.Windows.Markup.IUriContext>  
  
- <xref:System.Windows.Markup.IXamlTypeResolver>  
  
> [!NOTE]
> Otro servicio de .NET Framework 3,5 relacionado con las extensiones de marcado es la <xref:System.Windows.Markup.IReceiveMarkupExtension> interfaz. <xref:System.Windows.Markup.IReceiveMarkupExtension>no se migró y está marcado `[Obsolete]` para .NET Framework 4. Los escenarios que usaban <xref:System.Windows.Markup.IReceiveMarkupExtension> deben usar devoluciones de llamada con atributos <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> en su lugar. <xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> también está marcado como `[Obsolete]`.  
  
<a name="xaml_language_features"></a>   
## <a name="xaml-language-features"></a>Características del lenguaje XAML  
 Varias características del lenguaje XAML y componentes para WPF existían ya en el ensamblado PresentationFramework. Se implementaban como una subclase <xref:System.Windows.Markup.MarkupExtension> para exponer los usos de la extensión de marcado en el marcado XAML. En .NET Framework 4, existen en el ensamblado System. XAML para que los proyectos que no incluyen ensamblados de WPF puedan utilizar estas características de nivel de lenguaje XAML. WPF utiliza estas mismas implementaciones para las aplicaciones de .NET Framework 4. Como en los otros casos que se enumeran en este tema, los tipos de soporte continúan existiendo en el espacio de nombres <xref:System.Windows.Markup> para evitar interrumpir las referencias anteriores.  
  
 La tabla siguiente contiene una lista de las clases de compatibilidad de características XAML que se definen en System.Xaml.  
  
|Característica del lenguaje XAML|Uso|  
|---------------------------|-----------|  
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|  
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|  
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|  
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|  
  
 Aunque System.Xaml no tenga clases específicas de soporte, la lógica general para procesar las características del lenguaje XAML reside ahora en System.Xaml y en sus lectores XAML y sistemas de escritura XAML implementados. Por ejemplo, `x:TypeArguments` es un atributo que es procesado por los lectores y sistemas de escritura XAML de las implementaciones de System.Xaml; se puede tener en cuenta en el flujo de nodo XAML, tiene el control en el contexto de esquema XAML predeterminado (basado en CLR), tiene una representación del sistema de tipos XAML, etc. En consecuencia, la documentación de referencia para todas las características de nivel de lenguaje XAML es un subtema de [XAML Services](index.md) y de esa área general del conjunto de documentación de .NET Framework, en lugar de formar parte de la documentación de WPF como un subtema de [Advanced (Windows Presentation Foundation)](../wpf/advanced/index.md) (como sigue ocurriendo con los conjuntos de documentación 3.5).  
  
<a name="valueserializer_and_supporting_classes"></a>   
## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer y clases compatibles  
 La clase <xref:System.Windows.Markup.ValueSerializer> admite la conversión de tipo a una cadena, especialmente para los casos de serialización de XAML en los que la serialización puede requerir varios modos o nodos en el resultado. En .NET Framework 3,5 y .NET Framework 3,0, <xref:System.Windows.Markup.ValueSerializer> para WPF estaba en el ensamblado WindowsBase. En el .NET Framework 4, la <xref:System.Windows.Markup.ValueSerializer> clase está en System. XAML y está pensada para cualquier escenario de extensibilidad XAML, no solo para los que se basan en WPF. <xref:System.Windows.Markup.IValueSerializerContext> (un servicio de soporte) y <xref:System.Windows.Markup.DateTimeValueSerializer> (una subclase concreta) también se migran a System.Xaml.  
  
<a name="xamlrelated_attributes"></a>   
## <a name="xaml-related-attributes"></a>Atributos relacionados con XAML  
 XAML de WPF incluía varios atributos que se pueden aplicar a los tipos CLR para indicar algo sobre su comportamiento XAML. A continuación se muestra una lista de los atributos que existían en los ensamblados de WPF en .NET Framework 3,5 y .NET Framework 3,0. Estos atributos se migran a System. XAML en .NET Framework 4.  
  
- <xref:System.Windows.Markup.AmbientAttribute>  
  
- <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
- <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
- <xref:System.Windows.Markup.DependsOnAttribute>  
  
- <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
- <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
- <xref:System.Windows.Markup.RootNamespaceAttribute>  
  
- <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
- <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
- <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
- <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
- <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
- <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
- <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
- <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
<a name="miscellaneous_classes"></a>   
## <a name="miscellaneous-classes"></a>Clases diversas  
 La <xref:System.Windows.Markup.IComponentConnector> interfaz existía en WindowsBase en el .NET Framework 3,5 y el .NET Framework 3,0, pero existe en System. XAML en .NET Framework 4. <xref:System.Windows.Markup.IComponentConnector> sirve principalmente para el soporte técnico de herramientas y los compiladores de marcado de XAML.  
  
 La <xref:System.Windows.Markup.INameScope> interfaz existía en WindowsBase en el .NET Framework 3,5 y el .NET Framework 3,0, pero existe en System. XAML en .NET Framework 4. <xref:System.Windows.Markup.INameScope> define las operaciones básicas de un ámbito de nombres de XAML.  
  
<a name="xamlrelated_classes_with_shared_names_that_exist_in_wpf_and_systemxaml"></a>   
## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>Clases relacionadas con XAML con nombres compartidos que existen en WPF y System.Xaml  
 Las clases siguientes existen tanto en los ensamblados de WPF como en el ensamblado System. Xaml del .NET Framework 4:  
  
 `XamlReader`  
  
 `XamlWriter`  
  
 `XamlParseException`  
  
 La implementación de WPF se encuentra en el espacio de nombres <xref:System.Windows.Markup> y el ensamblado PresentationFramework. La implementación de System.Xaml se encuentra en el espacio de nombres <xref:System.Xaml> . Si se utilizan tipos WPF o se hacen derivaciones de tipos WPF, normalmente debería usar las implementaciones de WPF de <xref:System.Windows.Markup.XamlReader> y <xref:System.Windows.Markup.XamlWriter> en lugar de las implementaciones de System.Xaml. Para más información, vea la sección Comentarios en <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> y <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.  
  
 Si va a incluir referencias a ensamblados de WPF y System.Xaml y también usa instrucciones `include` para los espacios de nombres tanto <xref:System.Windows.Markup> como <xref:System.Xaml> , puede que necesite completar las llamadas a estas API para resolver los tipos sin ambigüedad.  
  
## <a name="see-also"></a>Vea también

- [Servicios XAML](index.md)
