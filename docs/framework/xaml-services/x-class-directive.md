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
ms.openlocfilehash: d6baa6d8eb3a6d3520fb1549e2182f27ca52c36a
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837251"
---
# <a name="xclass-directive"></a>x:Class (Directiva)
Configura la compilación de marcado XAML para combinar clases parciales entre el marcado y el código subyacente. La clase parcial de código se define en un archivo de código independiente en un lenguaje Common Language Specification (CLS), mientras que la clase parcial de marcado normalmente se crea mediante la generación de código durante la compilación de XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`namespace`|Opcional. Especifica un espacio de nombres CLR que contiene la clase parcial identificada por `classname`. Si se especifica `namespace`, un punto (.) separa `namespace` y `classname`. Vea la sección Comentarios.|  
|`classname`|Obligatoria. Especifica el nombre de CLR de la clase parcial que conecta el XAML cargado y el código subyacente para ese XAML.|  
  
## <a name="dependencies"></a>Dependencias  
 `x:Class` solo se puede especificar en el elemento raíz de una producción de XAML. `x:Class` no es válido en ningún objeto que tenga un elemento primario en la producción XAML. Para obtener más información, vea [\[sección de\] MS-XAML 4.3.1.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="remarks"></a>Notas  
 El valor `namespace` puede contener puntos adicionales para organizar los espacios de nombres relacionados en jerarquías de nombres, que es una técnica común en la programación de .NET Framework. Solo el último punto de una cadena de valores de `x:Class` se interpreta como un `namespace` independiente y `classname.` la clase que se utiliza como `x:Class` no puede ser una clase anidada. No se permiten clases anidadas porque la determinación del significado de los puntos de las cadenas `x:Class` es ambigua si se permiten clases anidadas.  
  
 En los modelos de programación existentes que usan `x:Class`, `x:Class` es opcional en el sentido de que es totalmente válido tener una página XAML sin código subyacente. Sin embargo, esa funcionalidad interactúa con las acciones de compilación tal y como las implementan los marcos de trabajo que usan XAML. `x:Class` capacidad también se ve influenciada por los roles que tienen varias clasificaciones de contenido especificado por XAML en un modelo de aplicación y en las acciones de compilación correspondientes. Si el XAML declara los valores de atributo de control de eventos o crea instancias de los elementos personalizados en los que las clases de definición se encuentran en la clase de código subyacente, debe proporcionar la `x:Class` referencia de la Directiva (o [x:Subclass](x-subclass-directive.md)) a la clase adecuada para el código subyacente.  
  
 El valor de la Directiva `x:Class` debe ser una cadena que especifique el nombre completo de una clase, pero sin información de ensamblado (equivalente a la <xref:System.Type.FullName%2A?displayProperty=nameWithType>). En el caso de las aplicaciones sencillas, puede omitir la información del espacio de nombres CLR si el código subyacente también está estructurado de esa manera (la definición de código se inicia en el nivel de clase).  
  
 El archivo de código subyacente para una definición de página o aplicación debe estar dentro de un archivo de código incluido como parte del proyecto que genera una aplicación compilada e implica la compilación del marcado. Debe seguir las reglas de nombre para las clases CLR. Para obtener más información, vea [directrices de diseño de marco](../../standard/design-guidelines/index.md). De forma predeterminada, la clase de código subyacente debe estar `public`; sin embargo, puede definirlo en un nivel de acceso diferente mediante la [Directiva x:ClassModifier (](x-classmodifier-directive.md).  
  
 Esta interpretación del atributo `x:Class` solo se aplica a una implementación XAML basada en CLR, en particular para .NET Framework servicios XAML. Otras implementaciones de XAML que no se basan en CLR y que no usan .NET Framework servicios XAML podrían usar una fórmula de resolución diferente para conectar el marcado XAML y el código en tiempo de ejecución de respaldo. Para obtener más información sobre las interpretaciones más generales de `x:Class`, vea [\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
 En un cierto nivel de arquitectura, el significado de `x:Class` es indefinido en .NET Framework servicios XAML. Esto se debe a que .NET Framework servicios XAML no especifica el modelo de programación por el que se conecta el marcado XAML y el código de respaldo. Los usos adicionales de la Directiva `x:Class` podrían ser implementados por Marcos específicos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML y el código subyacente basado en CLR. Cada marco de trabajo puede tener sus propias acciones de compilación que habilitan parte del comportamiento o componentes específicos que se deben incluir en el entorno de compilación. Dentro de un marco de trabajo, las acciones de compilación también pueden variar en función del lenguaje CLR específico que se usa para el código subyacente.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>x:Class en el modelo de programación de WPF  
 En las aplicaciones de WPF y el modelo de aplicación de WPF, `x:Class` se pueden declarar como un atributo para cualquier elemento que sea la raíz de un archivo XAML y se esté compilando (donde el XAML se incluye en un proyecto de aplicación de WPF con `Page` acción de compilación) o para la raíz <xref:System.Windows.Application> en la definición de la aplicación de una aplicación WPF compilada. La declaración de `x:Class` en un elemento que no sea una raíz de página o una raíz de la aplicación, o en un archivo XAML de WPF que no esté compilado, produce un error en tiempo de compilación en el compilador XAML de WPF .NET Framework 3,0 y .NET Framework 3,5. Para obtener información sobre otros aspectos del control de `x:Class` en WPF, vea [código subyacente y XAML en WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>x:Class para Windows Workflow Foundation  
 Por Windows Workflow Foundation, `x:Class` nombra la clase de una actividad personalizada compuesta completamente en XAML o nombra la clase parcial de la página XAML de un diseñador de actividad con código subyacente.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Class` para Silverlight se documenta por separado. Para obtener más información, vea [espacio de nombres XAML (x:) Características del lenguaje (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>Vea también

- [x:Subclass (Directiva)](x-subclass-directive.md)
- [Clases XAML y personalizadas para WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier (Directiva)](x-classmodifier-directive.md)
- [Tipos migrados de WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
