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
ms.openlocfilehash: 9fa9e51e66af6df4d1a6b1ec94c5010651bbb21d
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401501"
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
|`prefix`|Opcional. Prefijo que hace referencia a un espacio de nombres XAML asignado y no predeterminado. `prefix`se muestra explícitamente en el uso porque rara vez hace referencia a propiedades estáticas que proceden de un espacio de nombres XAML predeterminado. Vea la sección Comentarios.|  
|`typeName`|Necesario. Nombre del tipo que define el miembro estático deseado.|  
|`staticMemberName`|Necesario. Nombre del miembro de valor estático deseado (una constante, una propiedad estática, un campo o un valor de enumeración).|  
  
## <a name="remarks"></a>Comentarios  

La entidad de código a la que se hace referencia debe ser una de las siguientes:  
  
- Una constante  
- Una propiedad estática  
- Un campo  
- Un valor de enumeración

Si se especifica cualquier otra entidad de código, como una propiedad no estática, se producirá un error en tiempo de compilación si se compila el marcado XAML o una excepción de análisis en tiempo de carga XAML.  

Puede hacer `x:Static` referencias a propiedades o campos estáticos que no están en el espacio de nombres XAML predeterminado del documento XAML actual; sin embargo, esto requiere una asignación de prefijo. Los espacios de nombres XAML casi siempre se definen en el elemento raíz del documento XAML.  

Las operaciones de búsqueda de propiedades estáticas se pueden realizar mediante .NET Framework servicios XAML y sus lectores XAML y escritores de XAML, cuando se ejecutan con el contexto de esquema XAML predeterminado. Este contexto de esquema XAML puede utilizar la reflexión de CLR para proporcionar los valores estáticos necesarios para la construcción del gráfico de objetos. El `typeName` que especifique es en realidad un nombre de tipo XAML, no un nombre de tipo de CLR, aunque son esencialmente el mismo nombre cuando se usa el contexto de esquema XAML predeterminado o cuando se usan todos los marcos de implementación de XAML basados en CLR existentes.  

Tenga cuidado al hacer `x:Static` referencias que no son directamente el tipo del valor de una propiedad. En la secuencia de procesamiento de XAML, los valores proporcionados por una extensión de marcado no invocan la conversión de valores adicionales. Esto es así incluso si la `x:Static` referencia crea una cadena de texto, y una conversión de valor para los valores de atributo basados en la cadena de texto suele producirse para ese miembro específico o para cualquier valor de miembro del tipo de valor devuelto.  

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

En la implementación de los servicios de .NET Framework XAML, la <xref:System.Windows.Markup.StaticExtension> clase define el control para esta extensión de marcado.  

`x:Static` es una extensión de marcado. Todas las extensiones de marcado de XAML `{` usan `}` los caracteres y en su sintaxis de atributo, que es la Convención por la que un procesador XAML reconoce que una extensión de marcado debe proporcionar un valor. Para más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 El espacio de nombres XAML predeterminado que se usa para la programación de WPF no contiene muchas propiedades estáticas útiles, y la mayoría de las propiedades estáticas útiles tienen compatibilidad, como convertidores de `{x:Static}` tipos que facilitan el uso sin requerir. En el caso de las propiedades estáticas, debe asignar un prefijo para un espacio de nombres XAML si se cumple alguna de las siguientes condiciones:  
  
- Se hace referencia a un tipo que existe en WPF pero que no forma parte del espacio de nombres XAML predeterminado[!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]para WPF (). Este es un escenario bastante común para usar `x:Static`. Por ejemplo, puede usar una `x:Static` referencia con una asignación de espacio de nombres XAML para el espacio de nombres CLR y el <xref:System> ensamblado mscorlib con el fin <xref:System.Environment> de hacer referencia a las propiedades estáticas de la clase.  
  
- Hace referencia a un tipo de un ensamblado personalizado.  
  
- Está haciendo referencia a un tipo que existe en un ensamblado de WPF, pero ese tipo está dentro de un espacio de nombres CLR que no estaba asignado para formar parte del espacio de nombres XAML predeterminado de WPF. La asignación de espacios de nombres CLR en el espacio de nombres XAML predeterminado para WPF se realiza mediante definiciones en los diversos ensamblados de WPF (para obtener más información sobre este concepto, vea espacios de nombres [y asignación de espacios de nombres XAML para WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Los espacios de nombres CLR no asignados pueden existir si ese espacio de nombres CLR se compone principalmente de definiciones de clase que normalmente no están destinadas a XAML, como <xref:System.Windows.Threading>.  
  
 Para obtener más información sobre cómo usar prefijos y espacios de nombres XAML para WPF, vea espacios de nombres [y asignación de espacios de nombres XAML para WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también

- [x:Type (extensión de marcado)](x-type-markup-extension.md)
- [Tipos migrados de WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
