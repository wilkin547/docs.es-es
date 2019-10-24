---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 203380bbe2b2828e159ee36d795b6cd4a24e2917
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775654"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Indica si un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con la opción del compilador [-Platform: AnyCPU](../../../visual-basic/reference/command-line-compiler/platform.md) admite la selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. La opción está desactivada de forma predeterminada o si se especifica `-highentropyva-`. La opción está activada si se especifica `-highentropyva` o `-highentropyva+`.  
  
## <a name="remarks"></a>Comentarios  
 Si especifica esta opción, las versiones compatibles del kernel de Windows pueden usar los mayores grados de entropía cuando el kernel Aleatoriza el diseño del espacio de direcciones de un proceso como parte de ASLR. Si el kernel usa mayores grados de entropía, se puede asignar un número mayor de direcciones a las regiones de memoria, como pilas y montones. Como resultado, la ubicación de un área de memoria específica es más difícil de adivinar.  
  
 Cuando la opción está activada, el archivo ejecutable de destino y todos los módulos de los que depende deben ser capaces de controlar los valores de puntero que son superiores a 4 gigabytes (GB) cuando dichos módulos se ejecutan como procesos de 64 bits.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
