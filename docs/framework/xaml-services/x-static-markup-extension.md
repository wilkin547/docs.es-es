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
ms.openlocfilehash: bf94f1d61ee3080c9d3582e55e0695b269801c80
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733362"
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
|`typeName`|Requerido. Nombre del tipo que define el miembro estático deseado.|  
|`staticMemberName`|Requerido. Nombre del miembro de valor estático deseado (una constante, una propiedad estática, un campo o un valor de enumeración).|  
  
## <a name="remarks"></a>Comentarios  

La entidad de código a la que se hace referencia debe ser una de las siguientes:  
  
- Una constante  
- Una propiedad estática  
- Un campo  
- Un valor de enumeración

Si se especifica cualquier otra entidad de código, como una propiedad no estática, se producirá un error en tiempo de compilación si se compila el marcado XAML o una excepción de análisis en tiempo de carga XAML.  

Puede hacer referencias `x:Static` a campos o propiedades estáticos que no están en el espacio de nombres XAML predeterminado para el documento XAML actual. sin embargo, esto requiere una asignación de prefijo. Los espacios de nombres XAML casi siempre se definen en el elemento raíz del documento XAML.  

Las operaciones de búsqueda de propiedades estáticas se pueden realizar mediante .NET Framework servicios XAML y sus lectores XAML y escritores de XAML, cuando se ejecutan con el contexto de esquema XAML predeterminado. Este contexto de esquema XAML puede utilizar la reflexión de CLR para proporcionar los valores estáticos necesarios para la construcción del gráfico de objetos. El `typeName` que especifique es en realidad un nombre de tipo XAML, no un nombre de tipo de CLR, aunque son esencialmente el mismo nombre cuando se usa el contexto de esquema XAML predeterminado o cuando se usan todos los marcos de implementación de XAML basados en CLR existentes.  

Tenga cuidado al crear referencias `x:Static` que no son directamente el tipo del valor de una propiedad. En la secuencia de procesamiento de XAML, los valores proporcionados por una extensión de marcado no invocan la conversión de valores adicionales. Esto es así incluso si la referencia de `x:Static` crea una cadena de texto, y una conversión de valor para los valores de atributo basados en la cadena de texto suele producirse para ese miembro específico o para cualquier valor de miembro del tipo de valor devuelto.  

La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `x:Static` se asigna como valor de <xref:System.Windows.Markup.StaticExtension.Member%2A> de la clase de extensión <xref:System.Windows.Markup.StaticExtension> subyacente.  

Hay otros dos usos de XAML que son técnicamente posibles. Sin embargo, estos usos son menos comunes porque son innecesariamente detallados:  

1. Sintaxis de elemento de objeto.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. Sintaxis de atributo con propiedad de miembro explícita para la cadena de inicialización.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

En la implementación de los servicios de .NET Framework XAML, el control de esta extensión de marcado se define mediante la clase <xref:System.Windows.Markup.StaticExtension>.  

`x:Static` es una extensión de marcado. Todas las extensiones de marcado de XAML usan los caracteres `{` y `}` en su sintaxis de atributo, que es la Convención por la que un procesador XAML reconoce que una extensión de marcado debe proporcionar un valor. Para más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 El espacio de nombres XAML predeterminado que se usa para la programación de WPF no contiene muchas propiedades estáticas útiles, y la mayoría de las propiedades estáticas útiles tienen compatibilidad, como convertidores de tipos que facilitan el uso sin necesidad de `{x:Static}`. En el caso de las propiedades estáticas, debe asignar un prefijo para un espacio de nombres XAML si se cumple alguna de las siguientes condiciones:  
  
- Se hace referencia a un tipo que existe en WPF pero que no forma parte del espacio de nombres XAML predeterminado para WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`). Este es un escenario bastante común para usar `x:Static`. Por ejemplo, puede usar una referencia de `x:Static` con una asignación de espacio de nombres XAML para el espacio de nombres CLR <xref:System> y el ensamblado mscorlib con el fin de hacer referencia a las propiedades estáticas de la clase <xref:System.Environment>.  
  
- Hace referencia a un tipo de un ensamblado personalizado.  
  
- Está haciendo referencia a un tipo que existe en un ensamblado de WPF, pero ese tipo está dentro de un espacio de nombres CLR que no estaba asignado para formar parte del espacio de nombres XAML predeterminado de WPF. La asignación de espacios de nombres CLR en el espacio de nombres XAML predeterminado para WPF se realiza mediante definiciones en los diversos ensamblados de WPF (para obtener más información sobre este concepto, vea espacios de nombres [y asignación de espacios de nombres XAML para WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Los espacios de nombres CLR no asignados pueden existir si ese espacio de nombres CLR se compone principalmente de definiciones de clase que normalmente no están destinadas a XAML, como <xref:System.Windows.Threading>.  
  
 Para obtener más información sobre cómo usar prefijos y espacios de nombres XAML para WPF, vea espacios de nombres [y asignación de espacios de nombres XAML para WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también

- [x:Type (extensión de marcado)](x-type-markup-extension.md)
- [Tipos migrados de WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
