---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b22fb9ae24a04d9fe530811bf764352199c31813
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200815"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

El **- refonly** opción indica que la salida principal de la compilación debe ser un ensamblado de referencia en lugar de un ensamblado de implementación. El parámetro `-refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintaxis

```console
-refonly
```

## <a name="remarks"></a>Comentarios

Visual Basic admite la `-refout` cambiar comenzando con la versión 15.3.

Los ensamblados de referencia son solo metadatos de los ensamblados que contienen metadatos pero ningún código de implementación. Incluyen información de los tipos y miembros para todo excepto los tipos anónimos. El motivo de usar cuerpos `throw null` (en lugar de no usar ningún cuerpo) es que PEVerify pueda ejecutar y pasar (por lo tanto, validar la integridad de los metadatos).

Los ensamblados de referencia incluyen un nivel de ensamblado [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) atributo. Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo). Debido a este atributo, los tiempos de ejecución rechazarán cargar ensamblados de referencia para la ejecución (pero todavía se pueden cargar en un contexto de solo reflexión). Las herramientas que se reflejan en los ensamblados deben asegurarse de que cargan los ensamblados de referencia como de solo reflexión; en caso contrario, el runtime produce una <xref:System.BadImageFormatException>.

Las opciones `-refonly` y [`-refout`](refout-compiler-option.md) son mutuamente excluyentes.

## <a name="see-also"></a>Vea también
[-refout](refout-compiler-option.md)   
[Compilador de línea de comandos de Visual Basic](index.md)  
[Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)   
