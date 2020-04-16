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
ms.openlocfilehash: f589fa70c2ee1c56544fa0f0152990478aa3761f
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433281"
---
# <a name="xclass-directive"></a>x:Class (Directiva)
Configura la compilación de marcado XAML para unir clases parciales entre el marcado y el código subyacente. La clase parcial de código se define en un archivo de código independiente en un lenguaje de especificación de lenguaje común (CLS), mientras que la clase parcial de marcado se crea normalmente mediante la generación de código durante la compilación XAML.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`namespace`|Opcional. Especifica un espacio de nombres CLR `classname`que contiene la clase parcial identificada por . Si `namespace` se especifica, un punto (.) separa `namespace` y `classname`. Vea la sección Comentarios.|
|`classname`|Necesario. Especifica el nombre CLR de la clase parcial que conecta el XAML cargado y el código subyacente para ese XAML.|

## <a name="dependencies"></a>Dependencias

`x:Class`solo se puede especificar en el elemento raíz de una producción XAML. `x:Class`no es válido en ningún objeto que tenga un elemento primario en la producción XAML. Para obtener más información, consulte [ \[MS-XAML\] Sección 4.3.1.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Observaciones

El `namespace` valor puede contener puntos adicionales para organizar espacios de nombres relacionados en jerarquías de nombres, que es una técnica común en la programación de .NET. Solo el último punto `x:Class` de una cadena `namespace` de `classname.` valores se interpreta `x:Class` para separar y la clase que se utiliza como no puede ser una clase anidada. Las clases anidadas no están permitidas `x:Class` porque determinar el significado de los puntos para las cadenas es ambiguo si se permiten las clases anidadas.

En los modelos `x:Class`de `x:Class` programación existentes que usan , es opcional en el sentido de que es totalmente válido tener una página XAML que no tiene código subyacente. Sin embargo, esa capacidad interactúa con las acciones de compilación implementadas por marcos que usan XAML. `x:Class`la funcionalidad también está influenciada por los roles que varias clasificaciones de contenido especificado por XAML tienen en un modelo de aplicación y en las acciones de compilación correspondientes. Si el XAML declara valores de atributo de control de eventos o crea instancias de elementos `x:Class` personalizados donde las clases de definición están en la clase de código subyacente, debe proporcionar la referencia de directiva (o [x:Subclass](xsubclass-directive.md)) a la clase adecuada para el código subyacente.

El valor `x:Class` de la directiva debe ser una cadena que especifique el nombre completo <xref:System.Type.FullName%2A?displayProperty=nameWithType>de una clase pero sin ninguna información de ensamblado (equivalente a la ). Para aplicaciones sencillas, puede omitir la información del espacio de nombres CLR si el código subyacente también está estructurado de esa manera (la definición de código comienza en el nivel de clase).

El archivo de código subyacente para una definición de página o aplicación debe estar dentro de un archivo de código que se incluye como parte del proyecto que genera una aplicación compilada e implica la compilación de marcado. Debe seguir las reglas de nombre para las clases CLR. Para obtener más información, consulte [Directrices](../../../api/index.md)de diseño de marco . De forma predeterminada, la clase `public`de código subyacente debe ser ; sin embargo, puede definirlo en un nivel de acceso diferente mediante la [directiva x:ClassModifier](xclassmodifier-directive.md).

Esta interpretación `x:Class` del atributo solo se aplica a una implementación XAML basada en CLR, en particular a los servicios XAML de .NET. Otras implementaciones XAML que no se basan en CLR y que no usan servicios XAML de .NET podrían usar una fórmula de resolución diferente para conectar el marcado XAML y respaldar el código en tiempo de ejecución. Para obtener más información acerca `x:Class`de las interpretaciones más generales de , vea [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

En un cierto nivel de `x:Class` arquitectura, el significado de es indefinido en los servicios XAML de .NET. Esto se debe a que los servicios XAML de .NET no especifican el modelo de programación por el que se conectan el código de marcado y respaldo XAML. Los usos `x:Class` adicionales de la directiva pueden implementarse mediante marcos específicos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML y el código subyacente basado en CLR. Cada marco de trabajo puede tener sus propias acciones de compilación que habilitan algunos de los componentes específicos o de comportamiento que se deben incluir en el entorno de compilación. Dentro de un marco de trabajo, las acciones de compilación también pueden variar en función del lenguaje CLR específico que se usa para el código subyacente.

## <a name="xclass-in-the-wpf-programming-model"></a>x:Clase en el modelo de programación WPF

En las aplicaciones WPFWPF `x:Class` y el modelo de aplicación WPFWPF, se puede declarar como un atributo para cualquier elemento que `Page` es la raíz <xref:System.Windows.Application> de un archivo XAML y se está compilando (donde el XAML se incluye en un proyecto de aplicación WPF WPF con acción de compilación) o para la raíz en la definición de aplicación de una aplicación WPF compilada. Declarar `x:Class` en un elemento que no sea una raíz de página o raíz de aplicación, o en un archivo XAML de WPF que no se compila, produce un error en tiempo de compilación en el compilador XAML de .NET Framework 3.0 y .NET Framework 3.5 WPF. Para obtener información acerca `x:Class` de otros aspectos del control en WPFWPF, vea [Código subyacente y XAML en WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

## <a name="xclass-for-windows-workflow-foundation"></a>x:Class for Windows Workflow Foundation
Para Windows Workflow `x:Class` Foundation, asigna un nombre a la clase de una actividad personalizada compuesta por completo en XAML o la clase parcial de la página XAML para un diseñador de actividades con código subyacente.

## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight

`x:Class`para Silverlight se documenta por separado. Para obtener más información, vea [Espacio de nombres XAML (x:) Características del idioma (Silverlight).](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95))

## <a name="see-also"></a>Consulte también

- [x:Subclass (Directiva)](xsubclass-directive.md)
- [Clases XAML y personalizadas para WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier (Directiva)](xclassmodifier-directive.md)
- [Tipos migrados de WPF a System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
