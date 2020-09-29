---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 4d88c302281097fabd0eb361d60319bc8a0daf8d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058071"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)

Indica si un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con la opción del compilador [-platform:anycpu](platform.md) admite la selección aleatoria del diseño del espacio de direcciones de alta entropía (ASLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  

 `+` &#124; `-`  
 Opcional. La opción está desactivada de forma predeterminada o si se especifica `-highentropyva-`. La opción está activada si se especifica `-highentropyva` o `-highentropyva+`.  
  
## <a name="remarks"></a>Comentarios  

 Si se especifica esta opción, las versiones compatibles del kernel de Windows pueden usar niveles superiores de entropía cuando el kernel seleccione de forma aleatoria el diseño del espacio de direcciones de un proceso como parte de ASLR. Si el kernel usa niveles superiores de entropía, se puede asignar un mayor número de direcciones a las regiones de memoria como pilas y montones. Como resultado, la ubicación de un área de memoria específica es más difícil de adivinar.  
  
 Si la opción está activada, el archivo ejecutable de destino y todos los módulos de los que depende deben ser capaces de controlar los valores de puntero que son superiores a 4 gigas (GB), cuando dichos módulos se ejecutan como un proceso de 64 bits.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
