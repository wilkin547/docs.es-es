---
title: x:FieldModifier (Directiva)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ed50dd2aff1702543789f06939f7c2bc4b3dd83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier (Directiva)
Modifica el comportamiento de compilación de XAML para que se han definido campos para las referencias de objeto con nombre con <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> accesos en lugar de la <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> comportamiento predeterminado.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*Public*|La cadena exacta que se pasa para especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> frente a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varía según el lenguaje de programación de código subyacente que se utiliza. Vea la sección Comentarios.|  
  
## <a name="dependencies"></a>Dependencias  
 Si usa una producción de XAML `x:FieldModifier` en cualquier lugar, debe declarar el elemento raíz de esa producción XAML un [x: Class Directive](../../../docs/framework/xaml-services/x-class-directive.md).  
  
## <a name="remarks"></a>Comentarios  
 `x:FieldModifier`no es relevante para declarar el nivel de acceso general de una clase o a sus miembros. Es pertinente solo para el comportamiento del procesamiento XAML cuando se procesa un objeto XAML determinado que forma parte de una producción de XAML y se convierte en un objeto que es accesible en el gráfico de objetos de una aplicación. De forma predeterminada, la referencia del campo para este tipo de objeto es privada, lo que impide que los consumidores del control modifiquen el gráfico de objetos directamente. En su lugar, los consumidores del control se deben modificar el gráfico de objetos usando los modelos estándares que están habilitados en los modelos de programación, como al obtener la raíz del diseño, el elemento secundario de colecciones de elementos, las propiedades públicas dedicadas, y así sucesivamente.  
  
 El valor de la `x:FieldModifier` atributo varía según el lenguaje de programación y su finalidad puede variar en marcos concretos. La cadena que se va a utilizar depende de cómo cada lenguaje implementa su <xref:System.CodeDom.Compiler.CodeDomProvider> y los convertidores de tipos que devuelve para definir los significados de <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> y <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, y si ese idioma distingue mayúsculas de minúsculas.  
  
-   Para [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], la cadena para pasar para designar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> es `public`.  
  
-   Para [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], la cadena para pasar para designar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> es `Public`.  
  
-   Para [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], actualmente no existe ningún destino para XAML; por lo tanto, la cadena para pasar es indefinida.  
  
 También puede especificar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` en [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Friend` en [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]) pero especificando <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es poco común porque `NotPublic` como el comportamiento ya es el valor predeterminado.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>es el comportamiento predeterminado porque es infrecuente que código fuera del ensamblado que ha compilado XAML necesita tener acceso a un elemento XAML creado. Arquitectura de seguridad WPF junto con el comportamiento de compilación de XAML no declarar campos que almacenan instancias de elemento como public, a menos que se establezcan específicamente el `x:FieldModifier` para permitir el acceso público.  
  
 `x:FieldModifier`solo es pertinente para los elementos con un [Directiva x: Name](../../../docs/framework/xaml-services/x-name-directive.md) porque ese nombre se utiliza para hacer referencia al campo una vez es público.  
  
 De forma predeterminada, la clase parcial para el elemento raíz es pública; Sin embargo, puede hacer que no públicos mediante el uso de la [x: ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md). El [x: ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) también afecta al nivel de acceso de la instancia de la clase de elemento raíz. Puede colocar ambos `x:Name` y `x:FieldModifier` en la raíz del elemento, pero esto sólo realiza una copia de campo público del elemento raíz, con el nivel de acceso de raíz true elemento clase sigue siendo controlada por [x: ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
## <a name="see-also"></a>Vea también  
 [Clases XAML y personalizadas para WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [Código subyacente y XAML en WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [x:Name (Directiva)](../../../docs/framework/xaml-services/x-name-directive.md)  
 [Compilar una aplicación de WPF (WPF)](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [x:ClassModifier (Directiva)](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
