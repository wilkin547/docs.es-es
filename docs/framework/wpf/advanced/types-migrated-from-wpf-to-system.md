---
title: Tipos migrados de WPF a System.Xaml
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 5aa2d8a39be47d9affb97c3b60e53c4722c63cce
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249817"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>Tipos migrados de WPF a System.Xaml

En .NET Framework 3.5 y .NET Framework 3.0, Windows Presentation Foundation (WPF) y Windows Workflow Foundation incluían una implementación de lenguaje XAML. Muchos de los tipos públicos que proporcionaban extensibilidad para la implementación XAML de WPF existían en los ensamblados de WindowsBase, PresentationCore y PresentationFramework. Del mismo modo, los tipos públicos que proporcionaban extensibilidad para XAML de Windows Workflow Foundation existían en el ensamblado System.Workflow.ComponentModel. En .NET Framework 4, algunos de los tipos relacionados con XAML se migraron al ensamblado System.Xaml. Una implementación común de .NET Framework de servicios de lenguaje XAML permite muchos escenarios de extensibilidad XAML que se definieron originalmente por la implementación XAML de un marco de trabajo específico, pero que ahora forman parte de la compatibilidad general con el lenguaje XAML de .NET Framework 4. En este artículo se enumeran los tipos que se migraron y se describen los problemas relacionados con la migración.

## <a name="assemblies-and-namespaces"></a>Nombres de ensamblados y espacios de nombres

En .NET Framework 3.5 y .NET Framework 3.0, los tipos que <xref:System.Windows.Markup> WPF implementó para admitir XAML estaban generalmente en el espacio de nombres. La mayoría de estos tipos estaban en el ensamblado WindowsBase.

En .NET Framework 4, <xref:System.Xaml> hay un nuevo espacio de nombres y un nuevo ensamblado System.Xaml. Muchos de los tipos que se implementaron originalmente para XAML de WPF se proporcionan ahora como puntos o servicios de extensibilidad para cualquier implementación de XAML. Para contribuir a que estén disponibles para escenarios más generales, los tipos se reenvían desde su ensamblado WPF original al ensamblado System.Xaml. Esto habilita escenarios de extensibilidad XAML sin tener que incluir los ensamblados de otros marcos (como WPFWPF y Windows Workflow Foundation).

En cuanto a los tipos migrados, la mayoría de los tipos permanece en el espacio de nombres <xref:System.Windows.Markup> . En parte, esto se hizo para evitar interrumpir las asignaciones de espacio de nombres de CLR en las implementaciones existentes archivo por archivo. Como resultado, <xref:System.Windows.Markup> el espacio de nombres de .NET Framework 4 contiene una mezcla de tipos de compatibilidad con lenguaje XAML general (del ensamblado System.Xaml) y tipos que son específicos de la implementación XAML de WPF (de WindowsBase y otros ensamblados WPF). Todo tipo que se ha migrado a System.Xaml, pero existía anteriormente en un ensamblado de WPF, tiene compatibilidad de reenvío de tipos en la versión 4 del ensamblado de WPF.

### <a name="workflow-xaml-support-types"></a>Tipos de soporte de XAML en Workflow

Windows Workflow Foundation también proporcionatipos de compatibilidad con XAML y, en muchos casos, tenían nombres cortos idénticos a un equivalente de WPF. A continuación se muestra una lista de tipos de compatibilidad XAML de Windows Workflow Foundation:

- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>

Estos tipos de compatibilidad todavía existen en los ensamblados de Windows Workflow Foundation para .NET Framework 4 y todavía se pueden usar para aplicaciones específicas de Windows Workflow Foundation; sin embargo, no se debe hacer referencia a ellos por aplicaciones o marcos que no usan Windows Workflow Foundation.

## <a name="markupextension"></a>MarkupExtension

En .NET Framework 3.5 y .NET Framework <xref:System.Windows.Markup.MarkupExtension> 3.0, la clase para WPF estaba en el ensamblado de WindowsBase. Una clase paralela para <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>Windows Workflow Foundation, , existía en el System.Workflow.ComponentModel ensamblado. En .NET Framework 4, la <xref:System.Windows.Markup.MarkupExtension> clase se migra al ensamblado System.Xaml. En .NET Framework <xref:System.Windows.Markup.MarkupExtension> 4, está pensado para cualquier escenario de extensibilidad XAML que use servicios XAML de .NET, no solo para aquellos que se basan en marcos específicos. Siempre que sea posible, los marcos específicos y el código de usuario del marco deben compilarse también en la clase <xref:System.Windows.Markup.MarkupExtension> para la extensión XAML.

## <a name="markupextension-supporting-service-classes"></a>Clases de servicio de soporte de MarkupExtension

.NET Framework 3.5 y .NET Framework 3.0 para <xref:System.Windows.Markup.MarkupExtension> WPF proporcionaban varios servicios que estaban disponibles para los implementadores e <xref:System.ComponentModel.TypeConverter> implementaciones para admitir el uso de tipos y propiedades en XAML. Estos servicios son los siguientes:

- <xref:System.Windows.Markup.IProvideValueTarget>

- <xref:System.Windows.Markup.IUriContext>

- <xref:System.Windows.Markup.IXamlTypeResolver>

> [!NOTE]
> Otro servicio de .NET Framework 3.5 relacionado <xref:System.Windows.Markup.IReceiveMarkupExtension> con extensiones de marcado es la interfaz. <xref:System.Windows.Markup.IReceiveMarkupExtension>no se migró `[Obsolete]` y está marcado para .NET Framework 4. Los escenarios que usaban <xref:System.Windows.Markup.IReceiveMarkupExtension> deben usar devoluciones de llamada con atributos <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> en su lugar. <xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> también está marcado como `[Obsolete]`.

## <a name="xaml-language-features"></a>Características del lenguaje XAML

Varias características del lenguaje XAML y componentes para WPF existían ya en el ensamblado PresentationFramework. Se implementaban como una subclase <xref:System.Windows.Markup.MarkupExtension> para exponer los usos de la extensión de marcado en el marcado XAML. En .NET Framework 4, existen en el ensamblado System.Xaml para que los proyectos que no incluyen ensamblados WPFWPF puedan usar estas características de nivel de lenguaje XAML. WPFWPF usa estas mismas implementaciones para aplicaciones de .NET Framework 4. Como en los otros casos que se enumeran en este tema, los tipos de soporte continúan existiendo en el espacio de nombres <xref:System.Windows.Markup> para evitar interrumpir las referencias anteriores.

La tabla siguiente contiene una lista de las clases de compatibilidad de características XAML que se definen en System.Xaml.

|Característica del lenguaje XAML|Uso|
|---------------------------|-----------|
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|

Aunque System.Xaml no tenga clases específicas de soporte, la lógica general para procesar las características del lenguaje XAML reside ahora en System.Xaml y en sus lectores XAML y sistemas de escritura XAML implementados. Por ejemplo, `x:TypeArguments` es un atributo que es procesado por los lectores y sistemas de escritura XAML de las implementaciones de System.Xaml; se puede tener en cuenta en el flujo de nodo XAML, tiene el control en el contexto de esquema XAML predeterminado (basado en CLR), tiene una representación del sistema de tipos XAML, etc. Como resultado, la documentación de referencia para todas las características de nivel de lenguaje XAML es un subtema para los [servicios XAML](../../../desktop-wpf/xaml-services/index.md) en la Guía de escritorio para Windows Presentation [Foundation (WPF).](../../../desktop-wpf/overview/index.md)

## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer y clases compatibles

La clase <xref:System.Windows.Markup.ValueSerializer> admite la conversión de tipo a una cadena, especialmente para los casos de serialización de XAML en los que la serialización puede requerir varios modos o nodos en el resultado. En .NET Framework 3.5 y .NET <xref:System.Windows.Markup.ValueSerializer> Framework 3.0, el para WPF estaba en el ensamblado de WindowsBase. En .NET Framework 4, la <xref:System.Windows.Markup.ValueSerializer> clase está en System.Xaml y está pensada para cualquier escenario de extensibilidad XAML, no solo para aquellos que se basan en WPFWPF. <xref:System.Windows.Markup.IValueSerializerContext> (un servicio de soporte) y <xref:System.Windows.Markup.DateTimeValueSerializer> (una subclase concreta) también se migran a System.Xaml.

## <a name="xaml-related-attributes"></a>Atributos relacionados con XAML

XAML de WPF incluía varios atributos que se pueden aplicar a los tipos CLR para indicar algo sobre su comportamiento XAML. A continuación se muestra una lista de los atributos que existían en los ensamblados WPF en .NET Framework 3.5 y .NET Framework 3.0. Estos atributos se migran a System.Xaml en .NET Framework 4.

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

## <a name="miscellaneous-classes"></a>Clases diversas

La <xref:System.Windows.Markup.IComponentConnector> interfaz existía en WindowsBase en .NET Framework 3.5 y .NET Framework 3.0, pero existe en System.Xaml en .NET Framework 4. <xref:System.Windows.Markup.IComponentConnector> sirve principalmente para el soporte técnico de herramientas y los compiladores de marcado de XAML.

La <xref:System.Windows.Markup.INameScope> interfaz existía en WindowsBase en .NET Framework 3.5 y .NET Framework 3.0, pero existe en System.Xaml en .NET Framework 4. <xref:System.Windows.Markup.INameScope> define las operaciones básicas de un ámbito de nombres de XAML.

## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>Clases relacionadas con XAML con nombres compartidos que existen en WPF y System.Xaml

Las clases siguientes existen tanto en los ensamblados WPFWPF como en el ensamblado System.Xaml en .NET Framework 4:

`XamlReader`

`XamlWriter`

`XamlParseException`

La implementación de WPF se encuentra en el espacio de nombres <xref:System.Windows.Markup> y el ensamblado PresentationFramework. La implementación de System.Xaml se encuentra en el espacio de nombres <xref:System.Xaml> . Si se utilizan tipos WPF o se hacen derivaciones de tipos WPF, normalmente debería usar las implementaciones de WPF de <xref:System.Windows.Markup.XamlReader> y <xref:System.Windows.Markup.XamlWriter> en lugar de las implementaciones de System.Xaml. Para más información, vea la sección Comentarios en <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> y <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.

Si va a incluir referencias a ensamblados de WPF y System.Xaml y también usa instrucciones `include` para los espacios de nombres tanto <xref:System.Windows.Markup> como <xref:System.Xaml> , puede que necesite completar las llamadas a estas API para resolver los tipos sin ambigüedad.
