---
title: -nullable (opciones del compilador de C#)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: a68255dba18a022784cd4aaf0027c371893c577b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "84449802"
---
# <a name="-nullable-c-compiler-options"></a>-nullable (opciones del compilador de C#)

La opción **-nullable** le permite especificar el contexto que admite un valor NULL que quiera.

## <a name="syntax"></a>Sintaxis

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a>Argumentos

`+` &#124; `-`  
Si se especifica `+`, o simplemente **-nullable**, el compilador habilitará el contexto que admite un valor NULL. Si se especifica `-`, que se aplica si no se especifica **-nullable**, se deshabilita el contexto que admite un valor NULL.

`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`  
Especifica la opción de contexto que admite un valor NULL. Es similar a `+` o `-` en cuanto a habilitación y deshabilitación, pero permite una mayor granularidad de la especificidad del contexto que admite un valor NULL. El argumento `enable`, que se aplica del mismo modo que al especificar **-nullable**, habilita el contexto que admite un valor NULL. Si se especifica `disable`, se deshabilitará el contexto que admite un valor NULL. Al proporcionar el argumento `warnings`, **-nullable:warnings**, se habilita el contexto de advertencia que admite un valor NULL. Al especificar el argumento `annotations`, **-nullable:warnings**, se habilita el contexto de anotación que admite un valor NULL.

## <a name="remarks"></a>Comentarios

El análisis de flujo se utiliza para inferir la nulabilidad de las variables del código ejecutable. La nulabilidad inferida de una variable es independiente de la nulabilidad declarada de dicha variable. Las llamadas de métodos se analizan incluso cuando se omiten de forma condicional. Es el caso de <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> en modo de versión.

La invocación de métodos anotados con los siguientes atributos también afectará al análisis de flujo:

- Condiciones previas simples: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute>
- Condiciones posteriores simples: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute>
- Condiciones posteriores condicionales: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute>
- <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (por ejemplo, `DoesNotReturnIf(false)` para <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) y <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- Condiciones posteriores de miembros: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> y <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])>

### <a name="to-set-this-compiler-option-in-a-project"></a>Cómo establecer esta opción del compilador en un proyecto

Edite el archivo *.csproj* para agregar la etiqueta `<Nullable>` dentro de una jerarquía `Project/PropertyGroup`:

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Tipos de referencia que aceptan valores null](../../nullable-references.md)
