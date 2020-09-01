---
description: -pdb (Opciones del compilador de C#)
title: -pdb (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: 0dcafd0fd260488922c74a2330b312e80467e779
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124921"
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
  
## <a name="remarks"></a>Observaciones  
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
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
