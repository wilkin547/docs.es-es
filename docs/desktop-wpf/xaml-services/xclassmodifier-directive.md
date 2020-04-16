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
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433275"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier (Directiva)
Modifica el comportamiento `x:Class` de compilación XAML cuando también se proporciona. Específicamente, en lugar `class` de crear `Public` un parcial que tenga `x:Class` un nivel `NotPublic` de acceso (el valor predeterminado), el proporcionado se crea con un nivel de acceso. Este comportamiento afecta al nivel de acceso de la clase en los ensamblados generados.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|*NotPublic*|La cadena exacta que <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> va a pasar para especificar la cadena varíe, en función del lenguaje de programación de código subyacente que utilice. Vea la sección Comentarios.|

## <a name="dependencies"></a>Dependencias

[x:Class](xclass-directive.md) también debe proporcionarse en el mismo elemento y ese elemento debe ser el elemento raíz de una página. Para obtener más información, consulte [ \[MS-XAML\] Sección 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Observaciones

El valor `x:ClassModifier` del uso de los servicios XAML de .NET varía según el lenguaje de programación. La cadena que se va a <xref:System.CodeDom.Compiler.CodeDomProvider> usar depende de cómo cada lenguaje implementa <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>su y los convertidores de tipos que devuelve para definir los significados para y , y si ese lenguaje distingue mayúsculas de minúsculas.

- Para C- , la cadena <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`que se va a pasar para designar es .

- Para Microsoft Visual Basic .NET, la <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`cadena que se va a pasar para designar es .

- Para C++/CLI, no existen destinos que admitan la compilación de XAML; por lo tanto, el valor que se debe pasar no está especificado.

También puede <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> especificar`public` ( en `Public` C-, en Visual Basic); sin embargo, especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> hace con poca frecuencia porque ya es el comportamiento predeterminado.

Otros valores con restricciones de nivel de `private` acceso de código de `x:ClassModifier` usuario equivalentes, como en C-, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> no son relevantes para porque las referencias de clase anidadas no se admiten en XAML y, por lo tanto, el modificador tiene el mismo efecto.

## <a name="security-notes"></a>Notas de seguridad

El nivel de `x:ClassModifier` acceso declarado en sigue estando sujeto a la interpretación de marcos particulares y sus capacidades. WPFWPF incluye capacidades para `x:ClassModifier` `internal`cargar y crear instancias de tipos donde está , si se hace referencia a esa clase desde un recurso WPFWPF a través de una referencia URI de paquete. Como consecuencia de este caso y potencialmente otros como él implementados por `x:ClassModifier` otros marcos, no se basan exclusivamente en bloquear todos los posibles intentos de creación de instancias.

## <a name="see-also"></a>Consulte también

- [x:Class (Directiva)](xclass-directive.md)
- [Código subyacente y XAML en WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier (Directiva)](xfieldmodifier-directive.md)
- [Seguridad (WPF)](../../framework/wpf/security-wpf.md)
- [Tipos migrados de WPF a System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
