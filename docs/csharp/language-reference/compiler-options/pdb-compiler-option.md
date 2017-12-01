---
title: -pdb (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 108244d7de49c2ff4df1ac7202e77958743b32df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pdb-c-compiler-options"></a>/pdb (Opciones del compilador de C#)
La opción del compilador **/pdb** especifica el nombre y la ubicación del archivo de símbolos de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/pdb:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El nombre y la ubicación del archivo de símbolos de depuración.  
  
## <a name="remarks"></a>Comentarios  
 Al especificar [/debug (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), el compilador creará un archivo .pdb en el mismo directorio en que el compilador creará el archivo de salida (.exe o .dll) con un nombre de archivo que es el mismo que el nombre del archivo de salida.  
  
 **/pdb** le permite especificar un nombre de archivo y una ubicación distintos del valor predeterminado para el archivo .pdb.  
  
 No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.  
  
## <a name="example"></a>Ejemplo  
 Compile `t.cs` y cree un archivo .pdb denominado tt.pdb:  
  
```console  
csc /debug /pdb:tt t.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
