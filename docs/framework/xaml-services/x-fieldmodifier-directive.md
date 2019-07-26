---
title: x:FieldModifier (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 646ad1ca99d83f9fb2994f3c394eca27a60c0eac
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484718"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier (Directiva)
Modifica el <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> comportamiento de la compilación de XAML para que los campos de las referencias a objetos con nombre se definan con acceso en lugar del comportamiento predeterminado.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*Public*|La cadena exacta que se pasa para <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> especificar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> frente a varía en función del lenguaje de programación de código subyacente que se use. Vea la sección Comentarios.|  
  
## <a name="dependencies"></a>Dependencias  
 Si una producción de XAML `x:FieldModifier` utiliza en cualquier parte, el elemento raíz de esa producción de XAML debe declarar una [Directiva x:Class](x-class-directive.md).  
  
## <a name="remarks"></a>Comentarios  
 `x:FieldModifier`no es relevante para declarar el nivel de acceso general de una clase o sus miembros. Solo es pertinente para el comportamiento de procesamiento de XAML cuando se procesa un objeto XAML determinado que forma parte de una producción de XAML y se convierte en un objeto al que se puede tener acceso en el gráfico de objetos de una aplicación. De forma predeterminada, la referencia de campo para este tipo de objeto se mantiene privada, lo que evita que los consumidores del control modifiquen el gráfico de objetos directamente. En su lugar, se espera que los consumidores de control modifiquen el gráfico de objetos mediante patrones estándar habilitados por los modelos de programación, por ejemplo, obteniendo la raíz del diseño, las colecciones de elementos secundarios, las propiedades públicas dedicadas, etc.  
  
 El valor `x:FieldModifier` del atributo varía según el lenguaje de programación y su finalidad puede variar en marcos de trabajo específicos. La cadena que se va a usar depende de cómo cada lenguaje <xref:System.CodeDom.Compiler.CodeDomProvider> implementa su y los convertidores de tipos que devuelve para definir <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> los <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>significados para y, y si ese idioma distingue entre mayúsculas y minúsculas.  
  
- Para C#, la cadena que <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se va a pasar a Designate es. `public`  
  
- Para Microsoft Visual Basic .net, la cadena que <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se va a pasar a Design es. `Public`  
  
- En C++el caso de/CLI, no existe ningún destino para XAML actualmente; por lo tanto, la cadena que se va a pasar no está definida.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> También puede especificar (`internal` en C# `Friend` ,en`NotPublic` Visual Basic), pero especificar esinusualporqueyaeselcomportamientopredeterminado.<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>es el comportamiento predeterminado porque es poco frecuente que el código fuera del ensamblado que compiló el XAML necesite tener acceso a un elemento creado en XAML. La arquitectura de seguridad de WPF junto con el comportamiento de la compilación de XAML no declarará los campos que almacenan `x:FieldModifier` las instancias de elemento como públicas, a menos que establezca específicamente para permitir el acceso público.  
  
 `x:FieldModifier`solo es pertinente para los elementos con una [Directiva x:Name](x-name-directive.md) porque ese nombre se usa para hacer referencia al campo después de ser público.  
  
 De forma predeterminada, la clase parcial para el elemento raíz es pública; sin embargo, puede hacer que sea no público mediante la [Directiva x:ClassModifier (](x-classmodifier-directive.md). La [Directiva x:ClassModifier (](x-classmodifier-directive.md) también afecta al nivel de acceso de la instancia de la clase de elemento raíz. Puede colocar `x:Name` y `x:FieldModifier` en el elemento raíz, pero esto solo crea una copia de campo pública del elemento raíz, con el nivel de acceso de la clase de elemento raíz verdadero controlado por la [Directiva x:ClassModifier (](x-classmodifier-directive.md).  
  
## <a name="see-also"></a>Vea también

- [Clases XAML y personalizadas para WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Código subyacente y XAML en WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:Name (Directiva)](x-name-directive.md)
- [Compilar una aplicación de WPF (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)
- [x:ClassModifier (Directiva)](x-classmodifier-directive.md)
