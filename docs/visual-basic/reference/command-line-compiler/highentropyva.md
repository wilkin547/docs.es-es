---
title: /highentropyva (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34987930b3afd6d95d12190172a5a5e512106f8a
ms.lasthandoff: 03/13/2017

---
# <a name="highentropyva-visual-basic"></a>/highentropyva (Visual Basic)
Indica si un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con el [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) entropía alta dirección Space Layout Randomization (ASLR) admite la opción del compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. La opción está desactivada de forma predeterminada o si especifica `/highentropyva-`. La opción está activada si especifica `/highentropyva` o `/highentropyva+`.  
  
## <a name="remarks"></a>Comentarios  
 Si especifica esta opción, las versiones compatibles del núcleo de Windows pueden usar niveles superiores de entropía cuando el kernel aleatoriamente el diseño del espacio de direcciones de un proceso como parte de ASLR. Si el kernel usa niveles superiores de la entropía, un mayor número de direcciones se puede asignar a las regiones de memoria como pilas y montones. Como resultado, es más difícil de adivinar la ubicación de un área de memoria específica.  
  
 Cuando está activada la opción en el archivo ejecutable de destino y los módulos que dependa debe ser capaz de controlar los valores de puntero son superiores a 4 gigabytes (GB), cuando estos módulos se ejecutan como procesos de 64 bits.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
