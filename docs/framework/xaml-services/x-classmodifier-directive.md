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
ms.openlocfilehash: a24277a4d5fbc4870157b6c8ba00ba71ba61e656
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837238"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier (Directiva)
Modifica el comportamiento de la compilación de XAML cuando también se proporciona `x:Class`. En concreto, en lugar de crear una `class` parcial que tenga un nivel de acceso `Public` (valor predeterminado), el `x:Class` proporcionado se crea con un nivel de acceso `NotPublic`. Este comportamiento afecta al nivel de acceso de la clase en los ensamblados generados.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*NotPublic*|La cadena exacta que se va a pasar para especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> frente a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varía en función del lenguaje de programación de código subyacente que se use. Vea la sección Comentarios.|  
  
## <a name="dependencies"></a>Dependencias  
 [x:Class](x-class-directive.md) también debe proporcionarse en el mismo elemento y dicho elemento debe ser el elemento raíz de una página. Para obtener más información, vea [\[sección de\] MS-XAML 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="remarks"></a>Notas  
 El valor de `x:ClassModifier` en .NET Framework uso de servicios XAML varía según el lenguaje de programación. La cadena que se va a usar depende de cómo implementa cada lenguaje su <xref:System.CodeDom.Compiler.CodeDomProvider> y los convertidores de tipos que devuelve para definir los significados para <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> y <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, y si ese idioma distingue entre mayúsculas y minúsculas.  
  
- En C#, la cadena que se va a pasar a designar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `internal`.  
  
- En el caso de Microsoft Visual Basic .NET, la cadena que se va a pasar a designar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `Friend`.  
  
- Para C++/CLI, no existe ningún destino que admita la compilación de XAML. por lo tanto, el valor que se va a pasar no está especificado.  
  
 También puede especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` en C#, `Public` en Visual Basic); sin embargo, la especificación de <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se realiza con poca frecuencia porque <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ya es el comportamiento predeterminado.  
  
 Otros valores con restricciones de nivel de acceso del código de usuario equivalentes, C#como `private` en, no son relevantes para `x:ClassModifier` porque las referencias de clase anidadas no se admiten en XAML y, por tanto, el modificador <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> tiene el mismo efecto.  
  
## <a name="security-notes"></a>Notas de seguridad  
 El nivel de acceso tal y como se declara en `x:ClassModifier` sigue sujeto a la interpretación de los marcos concretos y sus capacidades. WPF incluye funcionalidades para cargar y crear instancias de tipos donde se `internal``x:ClassModifier`, si se hace referencia a esa clase desde un recurso de WPF a través de una referencia de Pack URI. Como consecuencia de este caso, y potencialmente otros como el que implementan otros marcos de trabajo, no se basa exclusivamente en `x:ClassModifier` para bloquear todos los intentos de creación de instancias posibles.  
  
## <a name="see-also"></a>Vea también

- [x:Class (Directiva)](x-class-directive.md)
- [Código subyacente y XAML en WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier (Directiva)](x-fieldmodifier-directive.md)
- [Seguridad (WPF)](../wpf/security-wpf.md)
- [Tipos migrados de WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
