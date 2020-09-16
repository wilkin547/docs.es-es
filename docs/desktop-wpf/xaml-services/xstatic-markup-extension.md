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
ms.openlocfilehash: 634a480b4d7446ed09708f6c91276d1c2f61d4a9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551616"
---
# <a name="xstatic-markup-extension"></a>Extensiones de marcado x:Static

Hace referencia a cualquier entidad de código estática por valor que se define en una manera compatible con Common Language Specification (CLS). La propiedad estática a la que se hace referencia se puede usar para proporcionar el valor de una propiedad en XAML.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a>Valores XAML

| | |
|-|-|
|`prefix`|Opcional. Prefijo que hace referencia a un espacio de nombres XAML asignado y no predeterminado. `prefix` se muestra explícitamente en el uso porque rara vez hace referencia a propiedades estáticas que proceden de un espacio de nombres XAML predeterminado. Vea la sección Comentarios.|
|`typeName`|Obligatorio. Nombre del tipo que define el miembro estático deseado.|
|`staticMemberName`|Obligatorio. Nombre del miembro de valor estático deseado (una constante, una propiedad estática, un campo o un valor de enumeración).|

## <a name="remarks"></a>Comentarios

La entidad de código a la que se hace referencia debe ser una de las siguientes:

- Una constante
- Una propiedad estática
- Un campo
- Un valor de enumeración

Si se especifica cualquier otra entidad de código, como una propiedad no estática, se producirá un error en tiempo de compilación si se compila el marcado XAML o una excepción de análisis en tiempo de carga XAML.

Puede hacer `x:Static` referencias a propiedades o campos estáticos que no están en el espacio de nombres XAML predeterminado del documento XAML actual; sin embargo, esto requiere una asignación de prefijo. Los espacios de nombres XAML casi siempre se definen en el elemento raíz del documento XAML.

Las operaciones de búsqueda de propiedades estáticas pueden realizarse mediante los servicios XAML de .NET y sus lectores y escritores de XAML, cuando se ejecutan con el contexto de esquema XAML predeterminado. Este contexto de esquema XAML puede utilizar la reflexión de CLR para proporcionar los valores estáticos necesarios para la construcción del gráfico de objetos. El `typeName` que especifique es en realidad un nombre de tipo XAML, no un nombre de tipo de CLR, aunque son esencialmente el mismo nombre cuando se usa el contexto de esquema XAML predeterminado o cuando se usan todos los marcos de implementación de XAML basados en CLR existentes.

Tenga cuidado al hacer `x:Static` referencias que no son directamente el tipo del valor de una propiedad. En la secuencia de procesamiento de XAML, los valores proporcionados por una extensión de marcado no invocan la conversión de valores adicionales. Esto es así incluso si la `x:Static` referencia crea una cadena de texto, y una conversión de valor para los valores de atributo basados en la cadena de texto suele producirse para ese miembro específico o para cualquier valor de miembro del tipo de valor devuelto.

La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `x:Static` se asigna como valor de <xref:System.Windows.Markup.StaticExtension.Member%2A> de la clase de extensión <xref:System.Windows.Markup.StaticExtension> subyacente.

Hay otros dos usos de XAML que son técnicamente posibles. Sin embargo, estos usos son menos comunes porque son innecesariamente detallados:

01. Sintaxis de elemento de objeto.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. Sintaxis de atributo con propiedad de miembro explícita para la cadena de inicialización.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

En la implementación de servicios XAML de .NET, el control de esta extensión de marcado se define mediante la <xref:System.Windows.Markup.StaticExtension> clase.

`x:Static` es una extensión de marcado. Todas las extensiones de marcado de XAML usan los `{` `}` caracteres y en su sintaxis de atributo, que es la Convención por la que un procesador XAML reconoce que una extensión de marcado debe proporcionar un valor. Para más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](markup-extensions-overview.md).

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

El espacio de nombres XAML predeterminado que se usa para la programación de WPF no contiene muchas propiedades estáticas útiles, y la mayoría de las propiedades estáticas útiles tienen compatibilidad, como convertidores de tipos que facilitan el uso sin requerir `{x:Static}` . En el caso de las propiedades estáticas, debe asignar un prefijo para un espacio de nombres XAML si se cumple alguna de las siguientes condiciones:

- Se hace referencia a un tipo que existe en WPF pero que no forma parte del espacio de nombres XAML predeterminado para WPF ( `http://schemas.microsoft.com/winfx/2006/xaml/presentation` ). Este es un escenario bastante común para usar `x:Static` . Por ejemplo, puede usar una `x:Static` referencia con una asignación de espacio de nombres XAML para el <xref:System> espacio de nombres CLR y el ensamblado mscorlib con el fin de hacer referencia a las propiedades estáticas de la <xref:System.Environment> clase.

- Hace referencia a un tipo de un ensamblado personalizado.

- Está haciendo referencia a un tipo que existe en un ensamblado de WPF, pero ese tipo está dentro de un espacio de nombres CLR que no estaba asignado para formar parte del espacio de nombres XAML predeterminado de WPF. La asignación de espacios de nombres CLR en el espacio de nombres XAML predeterminado para WPF se realiza mediante definiciones en los diversos ensamblados de WPF (para obtener más información sobre este concepto, vea espacios de nombres [y asignación de espacios de nombres XAML para WPF](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml)). Los espacios de nombres CLR no asignados pueden existir si ese espacio de nombres CLR se compone principalmente de definiciones de clase que normalmente no están destinadas a XAML, como <xref:System.Windows.Threading> .

Para obtener más información sobre cómo usar prefijos y espacios de nombres XAML para WPF, vea espacios de nombres [y asignación de espacios de nombres XAML para WPF](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml).

## <a name="see-also"></a>Vea también

- [x:Type (Extensión de marcado)](xtype-markup-extension.md)
- [Tipos migrados de WPF a System.Xaml](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
