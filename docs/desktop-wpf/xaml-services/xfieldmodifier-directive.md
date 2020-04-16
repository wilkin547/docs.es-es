---
title: x:FieldModifier (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 3e104b4c464d545e048f29901701c1c3dbb68229
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432783"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier (Directiva)
Modifica el comportamiento de compilación XAML para que <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> los campos <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> de las referencias de objeto con nombre se definan con acceso en lugar del comportamiento predeterminado.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|*Pública*|La cadena exacta que <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> pasa para especificar y varíe, dependiendo del lenguaje de programación de código subyacente que se utilice. Vea la sección Comentarios.|

## <a name="dependencies"></a>Dependencias

 Si una producción `x:FieldModifier` XAML usa cualquier lugar, el elemento raíz de esa producción XAML debe declarar una [directiva x:Class](xclass-directive.md).

## <a name="remarks"></a>Observaciones

`x:FieldModifier`no es relevante para declarar el nivel de acceso general de una clase o sus miembros. Solo es relevante para el comportamiento de procesamiento XAML cuando se procesa un objeto XAML determinado que forma parte de una producción XAML y se convierte en un objeto que es potencialmente accesible en el gráfico de objetos de una aplicación. De forma predeterminada, la referencia de campo para un objeto de este tipo se mantiene privada, lo que impide que los consumidores de control modifiquen el gráfico de objetos directamente. En su lugar, se espera que los consumidores de control modifiquen el gráfico de objetos mediante patrones estándar habilitados mediante modelos de programación, como la obtención de la raíz de diseño, las colecciones de elementos secundarios, las propiedades públicas dedicadas, etc.

El valor `x:FieldModifier` del atributo varía según el lenguaje de programación y su propósito puede variar en marcos específicos. La cadena que se va a <xref:System.CodeDom.Compiler.CodeDomProvider> usar depende de cómo cada lenguaje implementa <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>su y los convertidores de tipos que devuelve para definir los significados para y , y si ese lenguaje distingue mayúsculas de minúsculas.

- Para C- , la cadena <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `public`que se va a pasar para designar es .

- Para Microsoft Visual Basic .NET, la <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public`cadena que se va a pasar para designar es .

- Para C++/CLI, actualmente no existen destinos para XAML; por lo tanto, la cadena que se va a pasar es indefinida.

También puede <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> especificar`internal` (en `Friend` C-, en Visual <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Basic) `NotPublic` pero especificar es inusual porque como el comportamiento ya es el valor predeterminado.

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>es el comportamiento predeterminado porque es poco frecuente que el código fuera del ensamblado que compiló el XAML necesita acceso a un elemento creado por XAML. La arquitectura de seguridad de WPF junto con el comportamiento de compilación XAML `x:FieldModifier` no declarará los campos que almacenan las instancias de elemento como públicos, a menos que establezca específicamente el para permitir el acceso público.

`x:FieldModifier`sólo es relevante para los elementos con una [directiva x:Name](xname-directive.md) porque ese nombre se utiliza para hacer referencia al campo después de que sea público.

De forma predeterminada, la clase parcial para el elemento raíz es public; sin embargo, puede hacerlo no público mediante la [directiva x:ClassModifier](xclassmodifier-directive.md). La [directiva x:ClassModifier](xclassmodifier-directive.md) también afecta al nivel de acceso de la instancia de la clase de elemento raíz. Puede colocar `x:Name` ambos `x:FieldModifier` y en el elemento raíz, pero esto solo hace una copia de campo público del elemento raíz, con el nivel de acceso de clase de elemento raíz verdadero todavía controlado por [x:ClassModifier Directive](xclassmodifier-directive.md).

## <a name="see-also"></a>Consulte también

- [Clases XAML y personalizadas para WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Código subyacente y XAML en WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:Name (Directiva)](xname-directive.md)
- [Creación de una aplicación WPF (WPF)](../../framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [x:ClassModifier (Directiva)](xclassmodifier-directive.md)
