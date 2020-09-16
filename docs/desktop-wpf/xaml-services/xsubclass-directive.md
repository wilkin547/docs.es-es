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
ms.openlocfilehash: b888ef73d1678fd37c984e4bb223f24e5b65d2cc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540724"
---
# <a name="xsubclass-directive"></a>x:Subclass (Directiva)

Modifica el comportamiento de compilación del marcado XAML cuando `x:Class` también se proporciona. En lugar de crear una clase parcial basada en `x:Class` , el proporcionado `x:Class` se crea como una clase intermedia y, a continuación, se espera que la clase derivada proporcionada se base en `x:Class` .

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`namespace`|Opcional. Especifica un espacio de nombres CLR que contiene `classname` . Si `namespace` se especifica, un punto (.) separa `namespace` y `classname` .|
|`classname`|Obligatorio. Especifica el nombre de CLR de la clase parcial que conecta el XAML cargado y el código subyacente para ese XAML. Vea la sección Comentarios.|
|`subclassNamespace`|Opcional. Puede ser diferente de `namespace` si cada espacio de nombres puede resolver el otro. Especifica un espacio de nombres CLR que contiene `subclassName` . Si `subclassName` se especifica, un punto (.) separa `subclassNamespace` y `subclassName` .|
|`subclassName`|Obligatorio. Especifica el nombre de CLR de la subclase.|

## <a name="dependencies"></a>Dependencias

la [Directiva x:Class](xclass-directive.md) también debe proporcionarse en el mismo objeto y ese objeto debe ser el elemento raíz de la producción XAML.

## <a name="remarks"></a>Comentarios

`x:Subclass` el uso está pensado principalmente para los lenguajes que no admiten declaraciones de clase parcial.

La clase utilizada como `x:Subclass` no puede ser una clase anidada y `x:Subclass` debe hacer referencia al objeto raíz, tal como se explica en la sección "dependencias".

De lo contrario, el significado conceptual de `x:Subclass` no está definido por una implementación de servicios XAML de .net. Esto se debe a que el comportamiento de los servicios XAML de .NET no especifica el modelo de programación general por el que se conecta el marcado XAML y el código de respaldo. Las implementaciones de más conceptos relacionados con `x:Class` y `x:Subclass` se realizan mediante marcos específicos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML, el marcado compilado y el código subyacente basado en CLR. Cada marco de trabajo puede tener sus propias acciones de compilación que habilitan parte del comportamiento o componentes específicos que se deben incluir en el entorno de compilación. Dentro de un marco de trabajo, las acciones de compilación también pueden variar en función del lenguaje CLR específico que se usa para el código subyacente.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

`x:Subclass` puede estar en la raíz de una página o en la <xref:System.Windows.Application> raíz de la definición de la aplicación, que ya tiene `x:Class` . Al declarar `x:Subclass` en cualquier elemento que no sea una raíz de página o aplicación, o especificarlo donde no `x:Class` existe, se produce un error en tiempo de compilación.

La creación de clases derivadas que funcionan correctamente para el `x:Subclass` escenario es bastante compleja. Es posible que tenga que examinar los archivos intermedios (los archivos. g producidos en la carpeta obj del proyecto por la compilación de marcado, con los nombres que incorporan los nombres de archivo. xaml). Estos archivos intermedios pueden ayudarle a determinar el origen de ciertas construcciones de programación en las clases parciales Unidas en la aplicación compilada.

Los controladores de eventos de la clase derivada deben ser `internal override` ( `Friend Overrides` en Microsoft Visual Basic) para invalidar el código auxiliar de los controladores creados en la clase intermedia durante la compilación. De lo contrario, las implementaciones de la clase derivada ocultan (prevalecen) la implementación de la clase intermedia y no se invocan los controladores de clase intermedios.

Al definir `x:Class` y `x:Subclass` , no es necesario proporcionar ninguna implementación para la clase a la que hace referencia `x:Class` . Solo tiene que asignarle un nombre a través del `x:Class` atributo para que el compilador tenga alguna orientación para la clase que crea en los archivos intermedios (el compilador no selecciona un nombre predeterminado en este caso). Puede asignar `x:Class` una implementación a la clase; sin embargo, este no es el escenario típico para usar `x:Class` y `x:Subclass` .

## <a name="see-also"></a>Vea también

- [x:Class (Directiva)](xclass-directive.md)
- [Clases XAML y personalizadas para WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
