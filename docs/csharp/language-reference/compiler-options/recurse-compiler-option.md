---
title: -recurse (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /recurse
dev_langs:
- CSharp
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
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
ms.openlocfilehash: 99664f8b32f5f9e5bf491c5bfde2c1649de42dd9
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="recurse-c-compiler-options"></a>/recurse (Opciones del compilador de C#)
La opción /recurse le permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado (dir) o del directorio del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumentos  
 `dir` (opcional)  
 El directorio en el que quiere que comience la búsqueda. Si no se especifica, la búsqueda comienza en el directorio del proyecto.  
  
 `file`  
 Los archivos que buscará. Se admiten los caracteres comodín.  
  
## <a name="remarks"></a>Comentarios  
 La opción **/recurse** le permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado (`dir`) o del directorio del proyecto.  
  
 Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar **/recurse**.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## <a name="example"></a>Ejemplo  
 Compila todos los archivos de C# en el directorio actual:  
  
```console  
csc *.cs  
```  
  
 Compila todos los archivos de C# en el directorio dir1\dir2 y los directorios que haya por debajo y genera dir2.dll:  
  
```console  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)

