---
title: -pdb (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: 3081f4716e8cd858d789db6050e635af941aa05c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602568"
---
# <a name="-pdb-c-compiler-options"></a>-pdb (Opciones del compilador de C#)
La opción del compilador **-pdb** especifica el nombre y la ubicación del archivo de símbolos de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El nombre y la ubicación del archivo de símbolos de depuración.  
  
## <a name="remarks"></a>Comentarios  
 Al especificar [-debug (Opciones del compilador de C#)](./debug-compiler-option.md), el compilador creará un archivo .pdb en el mismo directorio en que el compilador creará el archivo de salida (.exe o .dll) con un nombre de archivo que es el mismo que el nombre del archivo de salida.  
  
 **-pdb** le permite especificar un nombre de archivo y una ubicación distintos del valor predeterminado para el archivo .pdb.  
  
 No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.  
  
## <a name="example"></a>Ejemplo  
 Compile `t.cs` y cree un archivo .pdb denominado tt.pdb:  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de proyectos y de soluciones](/visualstudio/ide/managing-project-and-solution-properties)
