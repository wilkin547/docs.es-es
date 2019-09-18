---
title: x:ClassModifier (Directiva)
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 5daff0567c1b1415fe994f6e39b4079cb2ab7346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053815"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier (Directiva)
Modifica el comportamiento de la compilación `x:Class` de XAML cuando también se proporciona. En concreto, en lugar de crear una `class` parcial que tenga `Public` un nivel de acceso (valor predeterminado), `x:Class` el proporcionado se crea `NotPublic` con un nivel de acceso. Este comportamiento afecta al nivel de acceso de la clase en los ensamblados generados.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*NotPublic*|Cadena exacta que se va a pasar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , en función del lenguaje de programación de código subyacente que se utilice. Vea la sección Comentarios.|  
  
## <a name="dependencies"></a>Dependencias  
 [x:Class](x-class-directive.md) también debe proporcionarse en el mismo elemento y dicho elemento debe ser el elemento raíz de una página. Para obtener más información, vea [ \[la sección\] MS-XAML 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Comentarios  
 El valor de `x:ClassModifier` en .NET Framework uso de servicios XAML varía según el lenguaje de programación. La cadena que se va a usar depende de cómo cada lenguaje <xref:System.CodeDom.Compiler.CodeDomProvider> implementa su y los convertidores de tipos que devuelve para definir <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> los <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>significados para y, y si ese idioma distingue entre mayúsculas y minúsculas.  
  
- Para C#, la cadena que <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> se va a pasar a Designate es. `internal`  
  
- Para Microsoft Visual Basic .net, la cadena que <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> se va a pasar a Design es. `Friend`  
  
- Para C++/CLI, no existe ningún destino que admita la compilación de XAML. por lo tanto, el valor que se va a pasar no está especificado.  
  
 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> También puede especificar (`public` en C#, `Public` en Visual Basic); sin embargo, la especificación <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> de se realiza con poca frecuencia <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> porque ya es el comportamiento predeterminado.  
  
 Otros valores con restricciones de nivel de acceso del código de usuario `private` equivalentes C#, como en, no `x:ClassModifier` son pertinentes para porque las referencias de clase anidadas no se admiten en <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> XAML y, por lo tanto, el modificador tiene el mismo efecto .  
  
## <a name="security-notes"></a>Notas de seguridad  
 El nivel de acceso tal y `x:ClassModifier` como se declara en todavía está sujeto a la interpretación de los marcos concretos y sus capacidades. WPF incluye funcionalidades para cargar y crear instancias de tipos `x:ClassModifier` donde `internal`es, si se hace referencia a esa clase desde un recurso de WPF a través de una referencia de pack uri. Como consecuencia de este caso, y potencialmente otros como el que implementan otros marcos de trabajo, no se base `x:ClassModifier` exclusivamente en bloquear todos los intentos de creación de instancias posibles.  
  
## <a name="see-also"></a>Vea también

- [x:Class (Directiva)](x-class-directive.md)
- [Código subyacente y XAML en WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier (Directiva)](x-fieldmodifier-directive.md)
- [Seguridad (WPF)](../wpf/security-wpf.md)
- [Tipos migrados de WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
