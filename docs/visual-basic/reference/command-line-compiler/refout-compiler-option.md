---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21cea76f31bdf2ac5fcf434ee759f874f917617b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintaxis

```console
-refout:filepath
```

## <a name="arguments"></a>Argumentos

 `filepath` La ruta de acceso y el nombre del ensamblado de referencia. Debe estar en una subcarpeta del ensamblado principal. La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal. Todas las carpetas de `filepath` debe existir; el compilador no los crea. 

## <a name="remarks"></a>Comentarios

Visual Basic admite la `-refout` conmutador a partir de la versión 15.3.

Ensamblados de referencia son solo metadatos ensamblados que contienen metadatos pero ningún código de implementación. Incluyen información de los tipos y miembros para todo excepto los tipos anónimos. Los cuerpos de método se reemplazan con una sola `throw null` instrucción. La razón para usar `throw null` cuerpos de método (en contraposición a ningún cuerpos) es para que pueda ejecutar y pasar (, por tanto, validar la integridad de los metadatos) PEVerify.

Ensamblados de referencia incluyen un nivel de ensamblado [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) atributo. Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo). Debido a este atributo, rechazan tiempos de ejecución cargar los ensamblados de referencia para la ejecución (pero todavía se pueden cargar en un contexto de solo reflexión). Herramientas que se reflejan en los ensamblados deben asegurarse de que se cargan los ensamblados de referencia como de solo reflexión; en caso contrario, el runtime produce una <xref:System.BadImageFormatException>.

Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.

## <a name="see-also"></a>Vea también
[-refonly](refonly-compiler-option.md)   
[Compilador de línea de comandos de Visual Basic](index.md)  
[Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)  

