---
title: x:Class (Directiva)
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: 5f7b072e90e92070dd7fda2f0ad44814009268b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199458"
---
# <a name="xclass-directive"></a>x:Class (Directiva)
Configura la compilación de marcado XAML para unirse a las clases parciales entre el marcado y código subyacente. La clase parcial del código se define en un archivo de código independiente en un [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] lenguaje, mientras que la clase parcial de marcado se suelen crear mediante generación de código durante la compilación de XAML.  
  
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
|`classname`|Obligatorio. Especifica el [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] nombre de la clase parcial que conecta el XAML cargado y el código subyacente para esa XAML.|  
  
## <a name="dependencies"></a>Dependencias  
 `x:Class` solo puede especificarse en el elemento raíz de una producción de XAML. `x:Class` no es válido en cualquier objeto que tiene un elemento primario en la producción de XAML. Para obtener más información, consulte [ \[MS-XAML\] sección 4.3.1.6](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Comentarios  
 El `namespace` valor puede contener puntos adicionales para organizar los espacios de nombres relacionados en las jerarquías del nombre, que es una técnica común en la programación de .NET Framework. Solo el último punto en una cadena de `x:Class` se interpreta los valores para separar `namespace` y `classname.` la clase que se usa como `x:Class` no puede ser una clase anidada. No se permiten clases anidadas porque determinar el significado de puntos para `x:Class` cadenas es ambiguo si se permiten clases anidadas.  
  
 Existente de programación los modelos que utilizan `x:Class`, `x:Class` es opcional en el sentido de que es completamente válido que haya una página XAML que no tenga ningún código subyacente. Sin embargo, esa funcionalidad interactúa con las acciones de compilación tal como está implementado por marcos que utilizan XAML. `x:Class` capacidad también se ve influida por las funciones que diversas clasificaciones de contenido específico de XAML tienen un modelo de aplicación y acciones de compilación en las correspondientes. Si su XAML declara los valores de atributo de control de eventos, o crea una instancia de los elementos personalizados donde son las clases de definición de la clase de código subyacente, tendrá que proporcionar el `x:Class` referencia de la directiva (o [x: Subclass](x-subclass-directive.md)) a la clase adecuada para el código subyacente.  
  
 El valor de la `x:Class` directiva debe ser una cadena que especifica el nombre completo de una clase sin ninguna información de ensamblado (equivalente a la <xref:System.Type.FullName%2A?displayProperty=nameWithType>). Para aplicaciones simples, puede omitir la información del espacio de nombres CLR si el código subyacente también está estructurado de esa manera (código de definición comienza en el nivel de clase).  
  
 Debe ser el archivo de código subyacente para una definición de aplicación o página dentro de un archivo de código que se incluye como parte del proyecto que genera una aplicación compilada e implica la compilación de marcado. Debe seguir las reglas de nombres para las clases CLR. Para obtener más información, consulte [instrucciones de diseño de Framework](../../standard/design-guidelines/index.md). De forma predeterminada, la clase de código subyacente debe ser `public`; sin embargo, puede definir en un nivel de acceso diferente mediante la [x: ClassModifier Directive](x-classmodifier-directive.md).  
  
 Esta interpretación de los `x:Class` atributo solo se aplica a una implementación de XAML basado en CLR, en particular para los servicios XAML de .NET Framework. Otras implementaciones de XAML que no se basan en CLR y que no use los servicios XAML de .NET Framework podrían utilizar una fórmula de una resolución distinta para conectar el marcado XAML y código de tiempo de ejecución de respaldo. Para obtener más información acerca de interpretaciones más generales de `x:Class`, consulte [ \[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
 En un cierto nivel de arquitectura, el significado de `x:Class` no está definida en los servicios XAML de .NET Framework. Esto es porque los servicios XAML de .NET Framework no especifica el modelo de programación por qué XAML marcado y código de respaldo están conectados. Usos adicionales de la `x:Class` directiva podría implementarse mediante marcos concretos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML y código subyacente basado en CLR. Cada marco de trabajo puede tener sus propias acciones de compilación que permiten algunos componentes específicos que deben incluirse en el entorno de compilación o comportamiento. Dentro de un marco, las acciones de compilación también pueden variar dependiendo del lenguaje específico de CLR que se usa para el código subyacente.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>x: Class en el modelo de programación de WPF  
 En las aplicaciones de WPF y el modelo de aplicación WPF, `x:Class` se pueden declarar como un atributo para cualquier elemento que es la raíz de un archivo XAML y se está compilando (donde se incluye el XAML en un proyecto de aplicación de WPF con `Page` acción de compilación), o para el < C4 > <xref:System.Windows.Application>  raíz en la definición de aplicación de una aplicación de WPF compilada. Declarar `x:Class` en un elemento que no sea una raíz de la página o la raíz de la aplicación, o en un archivo de WPF XAML que no se compila, se produce un error de tiempo de compilación en el [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] y [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] compilador WPF XAML. Para obtener información sobre otros aspectos de `x:Class` control en WPF, vea [código subyacente y XAML en WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>x: Class para Windows Workflow Foundation  
 Para Windows Workflow Foundation, `x:Class` nombra la clase de una actividad personalizada compuesta completamente en XAML o nombres de la clase parcial de la página XAML para un diseñador de actividad con código subyacente.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Class` para Silverlight se documenta por separado. Para obtener más información, consulte [XAML Namespace (x:) Características del lenguaje (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vea también

- [x:Subclass (Directiva)](x-subclass-directive.md)
- [Clases XAML y personalizadas para WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier (Directiva)](x-classmodifier-directive.md)
- [Tipos migrados de WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
