---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 552e611f222bfcc3ce12520ecdb891fd7b8b21de
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775546"
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintaxis

```console
-refout:filepath
```

## <a name="arguments"></a>Argumentos

`filepath`  
Ruta de acceso y nombre de archivo del ensamblado de referencia. Por lo general, debe estar en una subcarpeta del ensamblado principal. La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal. Todas las carpetas de `filepath` deben existir; el compilador no los crea.

## <a name="remarks"></a>Comentarios

Visual Basic admite el modificador de `-refout` a partir de la versión 15,3.

Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca. Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API. Para obtener más información, consulte [ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en .net Guide.

Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.

## <a name="see-also"></a>Vea también

- [/refonly](refonly-compiler-option.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
