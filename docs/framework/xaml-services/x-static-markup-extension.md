---
title: Extensiones de marcado x:Static
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 647bfed7b321a949090f6da047f9b8105d335101
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xstatic-markup-extension"></a>Extensiones de marcado x:Static
Hace referencia a cualquier entidad de código por valor estático que se define en un [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]: modo compatible. La propiedad estática que se hace referencia puede usarse para proporcionar el valor de una propiedad en XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`prefix`|Opcional. Un prefijo que hace referencia a un espacio de nombres XAML asignado, no predeterminado. `prefix`se muestra explícitamente el uso de porque rara vez hacen referencia a propiedades estáticas que proceden de un espacio de nombres XAML predeterminado. Vea la sección Comentarios.|  
|`typeName`|Requerido. El nombre del tipo que define al miembro estático deseado.|  
|`staticMemberName`|Requerido. El nombre del miembro de valor estático deseado (una constante, una propiedad estática, un campo o un valor de enumeración).|  
  
## <a name="remarks"></a>Comentarios  
 La entidad de código que se hace referencia debe ser uno de los siguientes:  
  
-   Una constante  
  
-   Una propiedad estática  
  
-   Un campo  
  
-   Un valor de enumeración  
  
 Si se especifica cualquier otra entidad de código, por ejemplo, una propiedad no estática, provoca un error en tiempo de compilación si el XAML es compilado por marcado, o una excepción de análisis de tiempo de carga XAML.  
  
 Puede realizar `x:Static` referencias a campos estáticos o propiedades que no están en el espacio de nombres XAML predeterminado para el documento XAML actual; sin embargo, esto requiere una asignación de prefijo. Espacios de nombres XAML casi siempre se definen en el elemento raíz del documento XAML.  
  
 Las operaciones de búsqueda para las propiedades estáticas pueden realizarse mediante los servicios XAML de .NET Framework y sus lectores XAML y escritores XAML, cuando se están ejecutando con el contexto de esquema XAML predeterminado. Este contexto de esquema XAML puede usar la reflexión de CLR para proporcionar los valores estáticos necesarios para la construcción del gráfico de objeto. El `typeName` especificar es realmente un nombre de tipo XAML, no un nombre de tipo CLR, aunque se trata básicamente el mismo nombre cuando se usa el contexto de esquema XAML predeterminado o al usar todos los marcos de trabajo existentes basado en CLR implementan XAML.  
  
 Tenga cuidado al realizar `x:Static` referencias que no son directamente el tipo del valor de una propiedad. En el código XAML procesar secuencia, proporcione los valores de una extensión de marcado no invocan conversión de valor adicional. Esto es cierto incluso si la `x:Static` referencia crea una cadena de texto y se produce una conversión de valor para los valores de atributo basados en cadena de texto normalmente para ese miembro concreto o para cualquier valor de miembro de tipo de valor devuelto.  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `x:Static` se asigna como valor de <xref:System.Windows.Markup.StaticExtension.Member%2A> de la clase de extensión <xref:System.Windows.Markup.StaticExtension> subyacente.  
  
 Hay dos otros usos XAML que son técnicamente posibles. Sin embargo, estos usos son menos común porque es innecesariamente detallados:  
  
 **Sintaxis de elemento de objeto:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName``" .../>`  
  
 **Sintaxis de atributo con propiedad Member explícita para la cadena de inicialización:** `<` `object`  ``  `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName``}" .../>`  
  
 En la implementación de servicios XAML de .NET Framework, el control para esta extensión de marcado se define mediante la <xref:System.Windows.Markup.StaticExtension> clase.  
  
 `x:Static` es una extensión de marcado. Todas las extensiones de marcado de XAML utilizan la `{` y `}` caracteres en su sintaxis de atributo, que es la convención que permite que un procesador XAML reconozca que una extensión de marcado debe proporcionar un valor. Para más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 El espacio de nombres XAML predeterminado usa para la programación de WPF no contiene muchas propiedades estáticas útiles, y la mayoría de las propiedades estáticas útiles tiene apoyo tales como los convertidores de tipos que facilitan el uso sin necesidad de `{x:Static}` . Para las propiedades estáticas, debe asignar un prefijo para un espacio de nombres XAML si se cumple alguna de las siguientes acciones:  
  
-   Hace referencia a un tipo que existe en WPF, pero no forma parte del espacio de nombres XAML predeterminado para WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]). Se trata de un escenario bastante común para utilizar `x:Static`. Por ejemplo, podría usar un `x:Static` referencia con una asignación de espacio de nombres XAML para la <xref:System> ensamblado mscorlib y de espacio de nombres CLR para hacer referencia a las propiedades estáticas de la <xref:System.Environment> clase.  
  
-   Hace referencia a un tipo de un ensamblado personalizado.  
  
-   Hace referencia a un tipo que existe en un ensamblado WPF, pero ese tipo se encuentra dentro de un espacio de nombres CLR que no se ha asignado para formar parte del espacio de nombres XAML de WPF predeterminado. La asignación de espacios de nombres CLR en el espacio de nombres XAML de WPF se realiza mediante las definiciones en varios ensamblados de WPF (para obtener más información sobre este concepto, vea [espacios de nombres XAML y asignación de Namespace para XAML de WPF](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Espacios de nombres CLR sin asignar pueden existir si ese espacio de nombres CLR está compuesta principalmente de definiciones de clases que no son suelen estar pensadas para XAML, como <xref:System.Windows.Threading>.  
  
 Para obtener más información sobre cómo usar los prefijos y espacios de nombres XAML de WPF, vea [XAML Namespaces and Namespace Mapping para XAML de WPF](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también  
 [x:Type (extensión de marcado)](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Tipos migrados de WPF a System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
