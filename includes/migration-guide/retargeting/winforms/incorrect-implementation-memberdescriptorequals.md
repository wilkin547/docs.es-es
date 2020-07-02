---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614816"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Implementación incorrecta de MemberDescriptor.Equals

#### <a name="details"></a>Detalles

En la implementación original del método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> se comparan dos propiedades de cadena diferentes de los objetos comparados: el nombre de la categoría y la cadena de descripción. La solución consiste en comparar la propiedad <xref:System.ComponentModel.MemberDescriptor.Category> del primer objeto con la propiedad <xref:System.ComponentModel.MemberDescriptor.Category> del segundo y la propiedad <xref:System.ComponentModel.MemberDescriptor.Description> del primero con la propiedad <xref:System.ComponentModel.MemberDescriptor.Description> del segundo.

#### <a name="suggestion"></a>Sugerencia

Si la aplicación depende de que <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> a veces devuelva `false` cuando los descriptores son equivalentes, y el destino es la versión 4.6.2 de .NET Framework o una versión posterior, tiene varias opciones:

- Realizar cambios de código para comparar los campos <xref:System.ComponentModel.MemberDescriptor.Category> y <xref:System.ComponentModel.MemberDescriptor.Description> de forma manual además de llamar al método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>.
- Excluir este cambio mediante la adición del valor siguiente al archivo app.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

Si la aplicación está destinada a .NET Framework 4.6.1 o una versión anterior y se ejecuta en .NET Framework 4.6.2 o una versión anterior, y quiere deshabilitar este cambio, puede establecer el modificador de compatibilidad en `false` mediante la adición del valor siguiente al archivo app.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
