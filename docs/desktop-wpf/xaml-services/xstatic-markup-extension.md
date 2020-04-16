---
title: Extensiones de marcado x:Static
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433269"
---
# <a name="xstatic-markup-extension"></a>Extensiones de marcado x:Static

Hace referencia a cualquier entidad de código estático por valor que se define de forma compatible con Common Language Specification (CLS). La propiedad estática a la que se hace referencia se puede usar para proporcionar el valor de una propiedad en XAML.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a>Valores XAML

| | |
|-|-|
|`prefix`|Opcional. Prefijo que hace referencia a un espacio de nombres XAML asignado y no predeterminado. `prefix`se muestra explícitamente en el uso porque rara vez se hace referencia a propiedades estáticas que proceden de un espacio de nombres XAML predeterminado. Vea la sección Comentarios.|
|`typeName`|Necesario. El nombre del tipo que define el miembro estático deseado.|
|`staticMemberName`|Necesario. El nombre del miembro de valor estático deseado (una constante, una propiedad estática, un campo o un valor de enumeración).|

## <a name="remarks"></a>Observaciones

La entidad de código a la que se hace referencia debe ser una de las siguientes:

- Una constante
- Una propiedad estática
- Un campo
- Un valor de enumeración

Especificar cualquier otra entidad de código, como una propiedad no estática, produce un error en tiempo de compilación si el XAML está compilado de marcado o una excepción de análisis en tiempo de carga XAML.

Puede hacer `x:Static` referencias a campos estáticos o propiedades que no están en el espacio de nombres XAML predeterminado para el documento XAML actual; sin embargo, esto requiere una asignación de prefijo. Los espacios de nombres XAML casi siempre se definen en el elemento raíz del documento XAML.

Las operaciones de búsqueda de propiedades estáticas las pueden realizar los servicios XAML de .NET y sus lectores XAML y escritores XAML, cuando se ejecutan con el contexto de esquema XAML predeterminado. Este contexto de esquema XAML puede usar la reflexión CLR para proporcionar los valores estáticos necesarios para la construcción de gráficos de objetos. El `typeName` especificar es en realidad un nombre de tipo XAML, no un nombre de tipo CLR, aunque estos son esencialmente el mismo nombre cuando se usa el contexto de esquema XAML predeterminado o cuando se usan todos los marcos de implementación XAML basados en CLR existentes.

Tenga cuidado al `x:Static` crear referencias que no son directamente el tipo del valor de una propiedad. En la secuencia de procesamiento XAML, los valores proporcionados de una extensión de marcado no invocan la conversión de valores adicionales. Esto es cierto `x:Static` incluso si la referencia crea una cadena de texto y una conversión de valor para los valores de atributo basados en la cadena de texto normalmente se produce para ese miembro específico o para cualquier valor de miembro del tipo de valor devuelto.

La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `x:Static` se asigna como valor de <xref:System.Windows.Markup.StaticExtension.Member%2A> de la clase de extensión <xref:System.Windows.Markup.StaticExtension> subyacente.

Hay otros dos usos XAML que son técnicamente posibles. Sin embargo, estos usos son menos comunes porque son innecesariamente detallados:

01. Sintaxis de elemento de objeto.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. Sintaxis de atributo con propiedad Member explícita para la cadena de inicialización.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

En la implementación de servicios XAML de .NET, la <xref:System.Windows.Markup.StaticExtension> clase define el control de esta extensión de marcado.

`x:Static` es una extensión de marcado. Todas las extensiones `{` de `}` marcado en XAML usan los caracteres y en su sintaxis de atributo, que es la convención por la que un procesador XAML reconoce que una extensión de marcado debe proporcionar un valor. Para más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](markup-extensions-overview.md).

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

El espacio de nombres XAML predeterminado que se usa para la programación WPFWPF no contiene muchas propiedades estáticas `{x:Static}` útiles y la mayoría de las propiedades estáticas útiles tienen compatibilidad, como convertidores de tipos que facilitan el uso sin necesidad de . Para las propiedades estáticas, debe asignar un prefijo para un espacio de nombres XAML si se cumple una de las siguientes condiciones:

- Hace referencia a un tipo que existe en WPFWPF pero no`http://schemas.microsoft.com/winfx/2006/xaml/presentation`forma parte del espacio de nombres XAML predeterminado para WPF ( ). Este es un escenario `x:Static`bastante común para usar . Por ejemplo, puede `x:Static` usar una referencia con <xref:System> una asignación de espacio de nombres XAML al <xref:System.Environment> espacio de nombres CLR y al ensamblado mscorlib para hacer referencia a las propiedades estáticas de la clase.

- Hace referencia a un tipo de un ensamblado personalizado.

- Hace referencia a un tipo que existe en un ensamblado WPFWPF, pero ese tipo está dentro de un espacio de nombres CLR que no se asignó para formar parte del espacio de nombres XAML predeterminado de WPF. La asignación de espacios de nombres CLR en el espacio de nombres XAML predeterminado para WPFWPF se realiza mediante definiciones en los distintos ensamblados de WPF (para obtener más información acerca de este concepto, vea [Espacios de nombres XAML y Asignación](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)de espacios de nombres para XAML de WPF). Los espacios de nombres CLR no asignados pueden existir si ese espacio de nombres CLR <xref:System.Windows.Threading>se compone principalmente de definiciones de clase que normalmente no están destinadas a XAML, como .

Para obtener más información sobre cómo usar prefijos y espacios de nombres XAML para WPF, vea [Espacios de nombres XAML y Asignación](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)de espacios de nombres para XAML de WPF .

## <a name="see-also"></a>Consulte también

- [x:Type (Extensión de marcado)](xtype-markup-extension.md)
- [Tipos migrados de WPF a System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
