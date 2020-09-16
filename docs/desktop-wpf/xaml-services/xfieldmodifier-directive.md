---
title: x:FieldModifier (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 4e67a6dac49b8d6a7d316526f99a1519b08fd68b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554480"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier (Directiva)
Modifica el comportamiento de la compilación de XAML para que los campos de las referencias a objetos con nombre se definan con <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> acceso en lugar del <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> comportamiento predeterminado.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|*Pública*|La cadena exacta que se pasa para especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> frente a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varía en función del lenguaje de programación de código subyacente que se use. Vea la sección Comentarios.|

## <a name="dependencies"></a>Dependencias

 Si una producción de XAML utiliza `x:FieldModifier` en cualquier parte, el elemento raíz de esa producción de XAML debe declarar una [Directiva x:Class](xclass-directive.md).

## <a name="remarks"></a>Comentarios

`x:FieldModifier` no es relevante para declarar el nivel de acceso general de una clase o sus miembros. Solo es pertinente para el comportamiento de procesamiento de XAML cuando se procesa un objeto XAML determinado que forma parte de una producción de XAML y se convierte en un objeto al que se puede tener acceso en el gráfico de objetos de una aplicación. De forma predeterminada, la referencia de campo para este tipo de objeto se mantiene privada, lo que evita que los consumidores del control modifiquen el gráfico de objetos directamente. En su lugar, se espera que los consumidores de control modifiquen el gráfico de objetos mediante patrones estándar habilitados por los modelos de programación, por ejemplo, obteniendo la raíz del diseño, las colecciones de elementos secundarios, las propiedades públicas dedicadas, etc.

El valor del `x:FieldModifier` atributo varía según el lenguaje de programación y su finalidad puede variar en marcos de trabajo específicos. La cadena que se va a usar depende de cómo cada lenguaje implementa su <xref:System.CodeDom.Compiler.CodeDomProvider> y los convertidores de tipos que devuelve para definir los significados para <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> y <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , y si ese idioma distingue entre mayúsculas y minúsculas.

- En C#, la cadena que se va a pasar a designar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> es `public` .

- Para Microsoft Visual Basic .NET, la cadena que se va a pasar a Design <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> es `Public` .

- En el caso de C++/CLI, no existe ningún destino para XAML actualmente; por lo tanto, la cadena que se va a pasar no está definida.

También puede especificar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ( `internal` en C#, `Friend` en Visual Basic), pero especificar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es inusual porque `NotPublic` ya es el comportamiento predeterminado.

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es el comportamiento predeterminado porque es poco frecuente que el código fuera del ensamblado que compiló el XAML necesite tener acceso a un elemento creado en XAML. La arquitectura de seguridad de WPF junto con el comportamiento de la compilación de XAML no declarará los campos que almacenan las instancias de elemento como públicas, a menos que establezca específicamente `x:FieldModifier` para permitir el acceso público.

`x:FieldModifier` solo es pertinente para los elementos con una [Directiva x:Name](xname-directive.md) porque ese nombre se usa para hacer referencia al campo después de ser público.

De forma predeterminada, la clase parcial para el elemento raíz es pública; sin embargo, puede hacer que sea no público mediante la [Directiva x:ClassModifier (](xclassmodifier-directive.md). La [Directiva x:ClassModifier (](xclassmodifier-directive.md) también afecta al nivel de acceso de la instancia de la clase de elemento raíz. Puede colocar `x:Name` y `x:FieldModifier` en el elemento raíz, pero esto solo crea una copia de campo pública del elemento raíz, con el nivel de acceso de la clase de elemento raíz verdadero controlado por la [Directiva x:ClassModifier (](xclassmodifier-directive.md).

## <a name="see-also"></a>Vea también

- [Clases XAML y personalizadas para WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
- [Código subyacente y XAML en WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [x:Name (Directiva)](xname-directive.md)
- [Compilar una aplicación de WPF (WPF)](/dotnet/desktop/wpf/app-development/building-a-wpf-application-wpf)
- [x:ClassModifier (Directiva)](xclassmodifier-directive.md)
