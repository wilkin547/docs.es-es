---
title: x:TypeArguments (Directiva)
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 69da9329f140121b66c71d4cf2e99e9d14a1b207
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432633"
---
# <a name="xtypearguments-directive"></a>x:TypeArguments (Directiva)

Pasa los argumentos de tipo de restricción de un genérico al constructor del tipo genérico.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`object`|Una declaración de elemento de objeto de un tipo XAML, que está respaldada por un tipo genérico CLR. Si `object` hace referencia a un tipo XAML que `object` no es del espacio de `object` nombres XAML predeterminado, requiere un prefijo para indicar el espacio de nombres XAML donde existe.|
|`typeString`|Cadena que declara uno o varios nombres de tipo XAML como cadenas, que proporciona los argumentos de tipo para el tipo genérico CLR. Consulte Comentarios para obtener notas de sintaxis adicionales.|

## <a name="remarks"></a>Observaciones

En la mayoría de los casos, los tipos `typeString` XAML que se usan como elemento de información en una cadena tienen el prefijo. Los tipos típicos de restricciones <xref:System.Int32> <xref:System.String>genéricas de CLR (por ejemplo, y ) proceden de bibliotecas de clases base de CLR. Esas bibliotecas no se asignan a espacios de nombres XAML predeterminados típicos específicos del marco de trabajo y, por lo tanto, requieren una asignación de prefijo para el uso de XAML.

Puede especificar más de un nombre de tipo XAML mediante un delimitador de comas.

Si las propias restricciones genéricas utilizan tipos genéricos, los argumentos de tipo de restricción anidados pueden estar contenidos entre paréntesis ().

Tenga en cuenta `x:TypeArguments` que esta definición de es específica de los servicios XAML de .NET y el uso de respaldo de CLR. Puede encontrar una definición de nivel de lenguaje en [ \[MS-XAML\] Sección 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="usage-examples"></a>Ejemplos de uso

En estos ejemplos, supongamos que se declaran las siguientes definiciones de espacio de nombres XAML:

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>>\<de cadena de lista

`<scg:List x:TypeArguments="sys:String" ...>`crea una <xref:System.Collections.Generic.List%601> instancia <xref:System.String> de un nuevo con un argumento de tipo.

### <a name="dictionarystringstring"></a>Cadena\<de diccionario,>

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`crea una <xref:System.Collections.Generic.Dictionary%602> instancia <xref:System.String> de un nuevo con dos argumentos de tipo.

### <a name="queuekeyvaluepairstringstring"></a>Cola<KeyValuePair\<String,String>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`crea una <xref:System.Collections.Generic.Queue%601> instancia de una <xref:System.Collections.Generic.KeyValuePair%602> nueva que tiene <xref:System.String> una <xref:System.String>restricción de con los argumentos de tipo de restricción interna y .

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>Usos XAML genéricos de XAML y XAML de XAML de XAML 2006 y WPF

Para el uso de XAML 2006 y XAML que se `x:TypeArguments` usa para aplicaciones WPF, existen las siguientes restricciones para y usos de tipos genéricos de XAML en general:

- Solo el elemento raíz de un archivo XAML puede admitir un uso XAML genérico que haga referencia a un tipo genérico.

- El elemento raíz debe asignarse a un tipo genérico con al menos un argumento de tipo. Un ejemplo es <xref:System.Windows.Navigation.PageFunction%601>. Las funciones de página son el escenario principal para la compatibilidad de uso genérico XAML en WPFWPF.

- El elemento de objeto XAML del elemento raíz `x:Class`para el genérico también debe declarar una clase parcial mediante . Esto es cierto incluso si se define una acción de compilación wpfWPF.

- `x:TypeArguments`no puede hacer referencia a restricciones genéricas anidadas.

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 o XAML 2006 con no WPF 3.0 o WPF 3.5 Dependencia

En los servicios XAML de .NET para XAML 2006 o XAML 2009, se relajan las restricciones relacionadas con WPF en el uso de XAML genérico. Puede crear instancias de un elemento de objeto genérico en cualquier posición en el marcado XAML que el sistema de tipos de respaldo y el modelo de objetos pueden admitir.

Si usa XAML 2009 en lugar de asignar los tipos base de CLR para obtener tipos XAML para primitivas de `typeString`lenguaje común, puede usar [tipos integrados para primitivas](types-for-primitives.md) de lenguaje XAML comunes como elementos de información en un archivo . Por ejemplo, podría declarar lo siguiente (no se muestran las asignaciones de prefijo, pero x es el espacio de nombres XAML del lenguaje XAML para XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

En WPF y al tener como destino .NET Framework 4 o .NET Core 3.0 `x:TypeArguments` (o posterior), puede usar las características de XAML 2009 junto con, pero solo para XAML suelto (XAML que no está compilado por marcado). XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009. Si necesita scodificar el XAML, debe operar bajo las restricciones indicadas en la sección Usos XAML genéricos de XAML de [XAML 2006 y WPF.](#xaml-2006-and-wpf-generic-xaml-usages) BAML solo se admite en .NET Framework.

## <a name="see-also"></a>Consulte también

- [x:Class (Directiva)](xclass-directive.md)
- [x:Type (Extensión de marcado)](xtype-markup-extension.md)
- [Tipos integrados para primitivas comunes en el lenguaje XAML](types-for-primitives.md)
- [Elementos genéricos en XAML](generics.md)
