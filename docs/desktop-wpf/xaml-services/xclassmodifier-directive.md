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
ms.openlocfilehash: 73732a06029cca3a4c6c6d82762d5263c5b8c955
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544822"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier (Directiva)
Modifica el comportamiento de la compilación de XAML cuando `x:Class` también se proporciona. En concreto, en lugar de crear una parcial `class` que tenga un `Public` nivel de acceso (valor predeterminado), el proporcionado `x:Class` se crea con un `NotPublic` nivel de acceso. Este comportamiento afecta al nivel de acceso de la clase en los ensamblados generados.

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

[x:Class](xclass-directive.md) también debe proporcionarse en el mismo elemento y dicho elemento debe ser el elemento raíz de una página. Para obtener más información, vea [ \[ la \] sección MS-XAML 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Comentarios

El valor de `x:ClassModifier` en el uso de los servicios XAML de .net varía según el lenguaje de programación. La cadena que se va a usar depende de cómo cada lenguaje implementa su <xref:System.CodeDom.Compiler.CodeDomProvider> y los convertidores de tipos que devuelve para definir los significados para <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> y <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , y si ese idioma distingue entre mayúsculas y minúsculas.

- En C#, la cadena que se va a pasar a designar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `internal` .

- Para Microsoft Visual Basic .NET, la cadena que se va a pasar a Design <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `Friend` .

- En C++/CLI, no existe ningún destino que admita la compilación de XAML. por lo tanto, el valor que se va a pasar no está especificado.

También puede especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` en C#, `Public` en Visual Basic); sin embargo, la especificación de <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se realiza con poca frecuencia porque <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ya es el comportamiento predeterminado.

Otros valores con restricciones de nivel de acceso del código de usuario equivalentes, como `private` en C#, no son pertinentes para `x:ClassModifier` porque las referencias de clase anidadas no se admiten en XAML y, por lo tanto, el <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modificador tiene el mismo efecto.

## <a name="security-notes"></a>Notas de seguridad

El nivel de acceso tal y como se declara en `x:ClassModifier` todavía está sujeto a la interpretación de los marcos concretos y sus capacidades. WPF incluye funcionalidades para cargar y crear instancias de tipos donde `x:ClassModifier` es `internal` , si se hace referencia a esa clase desde un recurso de WPF a través de una referencia de pack uri. Como consecuencia de este caso, y potencialmente otros como el que implementan otros marcos de trabajo, no se base exclusivamente en `x:ClassModifier` bloquear todos los intentos de creación de instancias posibles.

## <a name="see-also"></a>Vea también

- [x:Class (Directiva)](xclass-directive.md)
- [Código subyacente y XAML en WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [x:FieldModifier (Directiva)](xfieldmodifier-directive.md)
- [Seguridad (WPF)](/dotnet/desktop/wpf/security-wpf)
- [Tipos migrados de WPF a System.Xaml](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
