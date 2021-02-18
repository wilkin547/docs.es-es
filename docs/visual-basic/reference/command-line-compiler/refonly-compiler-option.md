---
description: Más información sobre -refonly (Visual Basic)
title: -refonly
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 283aa75fceead38c62c4cf10c1ffe08151aeac9c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474140"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

La opción **-refonly** indica que el resultado principal de la compilación debe ser un ensamblado de referencia, en lugar de un ensamblado de implementación. El parámetro `-refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintaxis

```console
-refonly
```

## <a name="remarks"></a>Comentarios

Visual Basic admite el modificador `-refonly` a partir de la versión 15.3.

Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca. Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API. Para obtener más información, consulte [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en la Guía de .NET.

Las opciones `-refonly` y [`-refout`](refout-compiler-option.md) son mutuamente excluyentes.

## <a name="see-also"></a>Vea también

- [/refout](refout-compiler-option.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
