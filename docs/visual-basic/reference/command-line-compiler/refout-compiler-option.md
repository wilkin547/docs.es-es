---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582874"
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

Los ensamblados de referencia son ensamblados de solo metadatos que contienen metadatos pero no código de implementación. Incluyen información de tipo y miembro para todo excepto los tipos anónimos. Sus cuerpos de método se reemplazan por una única instrucción `throw null`. El motivo por el que se usa `throw null` cuerpos de método (no en lugar de cuerpos) es para que PEVerify pueda ejecutarse y pasarse (con lo que se valida la integridad de los metadatos).

Los ensamblados de referencia incluyen un atributo [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) de nivel de ensamblado. Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo). Debido a este atributo, los tiempos de ejecución rechazan la carga de ensamblados de referencia para su ejecución (pero todavía se pueden cargar en un contexto de solo reflexión). Las herramientas que reflejan en los ensamblados deben asegurarse de que cargan los ensamblados de referencia como solo reflexión. de lo contrario, el tiempo de ejecución produce una <xref:System.BadImageFormatException>.

Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.

## <a name="see-also"></a>Vea también

- [/refonly](refonly-compiler-option.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
