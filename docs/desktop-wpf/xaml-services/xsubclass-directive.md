---
title: x:Subclass (Directiva)
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: e85e0fb5a0e1a865ed84a93767f8152a115bbe5f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432645"
---
# <a name="xsubclass-directive"></a>x:Subclass (Directiva)

Modifica el comportamiento de `x:Class` compilación de marcado XAML cuando también se proporciona. En lugar de crear una `x:Class`clase parcial `x:Class` basada en , la proporcionada se crea como una clase `x:Class`intermedia y, a continuación, se espera que la clase derivada proporcionada se base en .

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`namespace`|Opcional. Especifica un espacio de `classname`nombres CLR que contiene . Si `namespace` se especifica, un punto (.) separa `namespace` y `classname`.|
|`classname`|Necesario. Especifica el nombre CLR de la clase parcial que conecta el XAML cargado y el código subyacente para ese XAML. Vea la sección Comentarios.|
|`subclassNamespace`|Opcional. Puede ser `namespace` diferente de si cada espacio de nombres puede resolver el otro. Especifica un espacio de `subclassName`nombres CLR que contiene . Si `subclassName` se especifica, un punto (.) separa `subclassNamespace` y `subclassName`.|
|`subclassName`|Necesario. Especifica el nombre CLR de la subclase.|

## <a name="dependencies"></a>Dependencias

[x:Class Directive](xclass-directive.md) también debe proporcionarse en el mismo objeto y ese objeto debe ser el elemento raíz de la producción XAML.

## <a name="remarks"></a>Observaciones

`x:Subclass`el uso está pensado principalmente para lenguajes que no admiten declaraciones de clase parciales.

La clase utilizada `x:Subclass` como no puede `x:Subclass` ser una clase anidada y debe hacer referencia al objeto raíz como se explica en la sección "Dependencias".

De lo contrario, `x:Subclass` el significado conceptual de es indefinido por una implementación de servicios XAML de .NET. Esto se debe a que el comportamiento de los servicios XAML de .NET no especifica el modelo de programación general por el que se conectan el marcado XAML y el código de respaldo. Implementaciones de otros `x:Class` conceptos relacionados con y `x:Subclass` se realizan mediante marcos específicos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML, el marcado compilado y el código subyacente basado en CLR. Cada marco de trabajo puede tener sus propias acciones de compilación que habilitan parte del comportamiento o componentes específicos que se deben incluir en el entorno de compilación. Dentro de un marco de trabajo, las acciones de compilación también pueden variar en función del lenguaje CLR específico que se usa para el código subyacente.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

`x:Subclass`puede estar en una raíz <xref:System.Windows.Application> de página o en `x:Class`la raíz en la definición de la aplicación, que ya tiene . Declarar `x:Subclass` en cualquier elemento que no sea una página o `x:Class` raíz de aplicación, o especificarlo donde no existe, produce un error en tiempo de compilación.

Crear clases derivadas que `x:Subclass` funcionan correctamente para el escenario es bastante complejo. Es posible que deba examinar los archivos intermedios (los archivos .g generados en la carpeta obj del proyecto mediante la compilación de marcado, con nombres que incorporan los nombres de archivo .xaml). Estos archivos intermedios pueden ayudarle a determinar el origen de determinadas construcciones de programación en las clases parciales unidas en la aplicación compilada.

Controladores de eventos en la `internal override` `Friend Overrides` clase derivada deben ser ( en Microsoft Visual Basic) para invalidar los códigos auxiliares para los controladores como se creó en la clase intermedia durante la compilación. De lo contrario, las implementaciones de clase derivada ocultan (sombra) la implementación de la clase intermedia y no se invocan los controladores de clase intermedios.

Al definir `x:Class` ambos `x:Subclass`y , no es necesario proporcionar ninguna implementación para la clase a la que `x:Class`hace referencia . Solo necesita asignarle un nombre `x:Class` a través del atributo para que el compilador tenga alguna sindicación para la clase que crea en los archivos intermedios (el compilador no selecciona un nombre predeterminado en este caso). Puede dar `x:Class` a la clase una implementación; sin embargo, este no es `x:Class` `x:Subclass`el escenario típico para usar ambos y .

## <a name="see-also"></a>Consulte también

- [x:Class (Directiva)](xclass-directive.md)
- [Clases XAML y personalizadas para WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
