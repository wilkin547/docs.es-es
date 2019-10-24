---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775565"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

La opción **-refonly** indica que la salida principal de la compilación debe ser un ensamblado de referencia en lugar de un ensamblado de implementación. El parámetro `-refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintaxis

```console
-refonly
```

## <a name="remarks"></a>Comentarios

Visual Basic admite el modificador de `-refonly` a partir de la versión 15,3.

Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca. Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API. Para obtener más información, consulte [ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en .net Guide.

Las opciones `-refonly` y [`-refout`](refout-compiler-option.md) son mutuamente excluyentes.

## <a name="see-also"></a>Vea también

- [/refout](refout-compiler-option.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
