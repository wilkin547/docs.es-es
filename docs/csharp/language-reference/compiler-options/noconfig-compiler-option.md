---
title: -noconfig (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 2d6d0c52be2306292224d7831f8818c6f865f2f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602742"
---
# <a name="-noconfig-c-compiler-options"></a>-noconfig (Opciones del compilador de C#)
La opción **-noconfig** comunica al compilador que no compile con el archivo csc.rsp, que está ubicado y se carga desde el mismo directorio que el archivo csc.exe.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Comentarios  
 El archivo csc.rsp hace referencia a todos los ensamblados incluidos en .NET Framework. Las referencias reales que incluye el entorno de desarrollo Visual Studio de .NET dependen del tipo de proyecto.  
  
 Es posible modificar el archivo csc.rsp y especificar opciones de compiladores adicionales que puedan incluirse en cada compilación desde la línea de comandos con csc.exe (excepto la opción **-noconfig**).  
  
 El compilador procesa en último lugar las opciones que se pasan al comando **csc**. Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo csc.rsp.  
  
 Si no quiere que el compilador busque y use la configuración del archivo csc.rsp, especifique **-noconfig**.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de proyectos y de soluciones](/visualstudio/ide/managing-project-and-solution-properties)
