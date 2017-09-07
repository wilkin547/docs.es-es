---
title: -noconfig (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /noconfig
dev_langs:
- CSharp
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 594e972dc834ab74412e30a48428f850ae02b5ac
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="noconfig-c-compiler-options"></a>/noconfig (Opciones del compilador de C#)
La opción **/noconfig** comunica al compilador que no compile con el archivo csc.rsp, que está ubicado y se carga desde el mismo directorio que el archivo csc.exe.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/noconfig  
```  
  
## <a name="remarks"></a>Comentarios  
 El archivo csc.rsp hace referencia a todos los ensamblados incluidos en .NET Framework. Las referencias reales que incluye el entorno de desarrollo Visual Studio de .NET dependen del tipo de proyecto.  
  
 Es posible modificar el archivo csc.rsp y especificar opciones de compiladores adicionales que puedan incluirse en cada compilación desde la línea de comandos con csc.exe (excepto la opción **/noconfig**).  
  
 El compilador procesa en último lugar las opciones que se pasan al comando **csc**. Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo csc.rsp.  
  
 Si no quiere que el compilador busque y use la configuración del archivo csc.rsp, especifique **/noconfig**.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)

