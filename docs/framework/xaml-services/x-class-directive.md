---
title: x:Class (Directiva)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b894a56caa3644bae140e7ec37cf5b55ab093a59
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xclass-directive"></a>x:Class (Directiva)
Configura la compilación de marcado XAML para unir clases parciales entre el marcado y código subyacente. La clase parcial de código se define en un archivo de código independiente en un [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] lenguaje, mientras que la clase parcial de marcado normalmente se crea mediante generación de código durante la compilación de XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`namespace`|Opcional. Especifica un [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] espacio de nombres que contiene la clase parcial identificada por `classname`. Si `namespace` se especifica un punto (.) separa `namespace` y `classname`. Vea la sección Comentarios.|  
|`classname`|Requerido. Especifica el [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] nombre de la clase parcial que conecta el XAML cargado y el código subyacente de ese código XAML.|  
  
## <a name="dependencies"></a>Dependencias  
 `x:Class`solo puede especificarse en el elemento raíz de una producción de XAML. `x:Class`no es válido en cualquier objeto que tiene un elemento primario en la producción de XAML. Para obtener más información, consulte [ \[MS-XAML\] sección 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Comentarios  
 El `namespace` valor puede contener puntos adicionales para organizar los espacios de nombres relacionados en las jerarquías del nombre, que es una técnica habitual en la programación de .NET Framework. Solo el último punto en una cadena de `x:Class` valores se interpretan para separar `namespace` y `classname.` la clase que se utiliza como `x:Class` no puede ser una clase anidada. No se permiten clases anidadas porque determinar el significado de puntos para `x:Class` cadenas es ambiguo si se permiten clases anidadas.  
  
 Existente programación modelos que utilizan `x:Class`, `x:Class` es opcional en el sentido de que es completamente válido que haya una página XAML que no tenga ningún código subyacente. Sin embargo, esa capacidad interactúa con las acciones de compilación como implementada por marcos que usan XAML. `x:Class`capacidad también se ve afectada por los roles que diversas clasificaciones de contenido especificado por XAML tienen en un modelo de aplicación y en las correspondientes acciones de compilación. Si su XAML declara los valores de atributo de control de eventos, o crea una instancia de los elementos personalizados que son las clases de definición de la clase de código subyacente, tendrá que proporcionar el `x:Class` referencia de la directiva (o [x: Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)) a la clase adecuada para el código subyacente.  
  
 El valor de la `x:Class` directiva debe ser una cadena que especifica el nombre completo de una clase pero sin ninguna información de ensamblado (equivalente a la <xref:System.Type.FullName%2A?displayProperty=nameWithType>). Para aplicaciones simples, puede omitir la información de espacio de nombres CLR si también se estructura el código subyacente de esa manera (código definición se inicia en el nivel de clase).  
  
 El archivo de código subyacente para una definición de página o la aplicación debe ser dentro de un archivo de código que se incluye como parte del proyecto que genera una aplicación compilada e implica la compilación de marcado. Debe seguir las reglas de nombres para las clases CLR. Para obtener más información, consulte [directrices de diseño de Framework](../../../docs/standard/design-guidelines/index.md). De forma predeterminada, la clase de código subyacente debe ser `public`; sin embargo, puede definir en un nivel de acceso diferente mediante la [x: ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
 Esta interpretación de los `x:Class` atributo solo se aplica a una implementación de XAML basado en CLR, en particular a los servicios XAML de .NET Framework. Otras implementaciones de XAML que no se basan en CLR y que no usan servicios XAML de .NET Framework podrían utilizar una fórmula de resolución diferente para conectar el marcado XAML y código de tiempo de ejecución de respaldo. Para obtener más información acerca de interpretaciones más generales de `x:Class`, consulte [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 En un cierto nivel de arquitectura, el significado de `x:Class` no está definida en los servicios XAML de .NET Framework. Esto es porque los servicios XAML de .NET Framework no especifica el modelo de programación que XAML marcado y código de respaldo están conectados. Usos adicionales de la `x:Class` directiva podría implementarse marcos concretos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML y código subyacente basado en CLR. Cada marco de trabajo puede tener sus propio acciones de compilación que habilitan algunos de los componentes específicos que deben incluirse en el entorno de compilación o comportamiento. Dentro de un marco de trabajo, las acciones de compilación también pueden variar según el lenguaje de CLR concreto que se utiliza para el código subyacente.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>x: Class en el modelo de programación de WPF  
 En las aplicaciones de WPF y el modelo de aplicaciones WPF, `x:Class` se pueden declarar como un atributo para cualquier elemento que es la raíz de un archivo XAML y se está compilando (donde se incluye el código XAML en un proyecto de aplicación de WPF con `Page` acción de compilación), o para el < C4 > <xref:System.Windows.Application>  raíz en la definición de aplicación de una aplicación de WPF compilada. Declarar `x:Class` en un elemento que no sea una raíz de la página o la raíz de la aplicación, o en un archivo XAML de WPF que no se compila, provoca un error en tiempo de compilación bajo la [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] y [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] compilador XAML de WPF. Para obtener información sobre otros aspectos de `x:Class` administrar en WPF, vea [código subyacente y XAML en WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>x: Class para Windows Workflow Foundation  
 Para Windows Workflow Foundation, `x:Class` un nombre a la clase de una actividad personalizada compuesta completamente en XAML o nombres de la clase parcial de la página XAML para un diseñador de actividades con código subyacente.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Class`para Silverlight se documenta por separado. Para obtener más información, vea [XAML Namespace (x:) Características del lenguaje (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vea también  
 [x:Subclass (Directiva)](../../../docs/framework/xaml-services/x-subclass-directive.md)  
 [Clases XAML y personalizadas para WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [x:ClassModifier (Directiva)](../../../docs/framework/xaml-services/x-classmodifier-directive.md)  
 [Tipos migrados de WPF a System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
