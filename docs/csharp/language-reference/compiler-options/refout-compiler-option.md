---
description: -refout (Opciones del compilador de C#)
title: -refout (Opciones del compilador de C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 424782e4607fea63130e95ab09a671c75fe1404d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128719"
---
# <a name="-refout-c-compiler-options"></a>-refout (Opciones del compilador de C#)

La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse. Esto se traduce en `metadataPeStream` en la API de emisión. Esta opción corresponde a la propiedad de proyecto [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) de MSBuild.

## <a name="syntax"></a>Sintaxis

```console
-refout:filepath
```

## <a name="arguments"></a>Argumentos

 `filepath` La ruta de archivo del ensamblado de referencia. Generalmente debe coincidir con el ensamblado principal. La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.

## <a name="remarks"></a>Observaciones

Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca. Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API. Para obtener más información, consulte [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en la Guía de .NET.

Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
