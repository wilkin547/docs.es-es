---
description: Mas información sobre -nostdlib (Visual Basic)
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 4a00ad21bc0038a6bf42f1dd6943ccc15c1a8abb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434880"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)

Hace que el compilador no haga referencia automáticamente a las bibliotecas estándar.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>Comentarios  

 La opción `-nostdlib` quita la referencia automática al ensamblado System.dll e impide que el compilador lea el archivo Vbc.rsp. El archivo Vbc.rsp, que está en el mismo directorio que el archivo Vbc.exe, hace referencia a los ensamblados de .NET Framework que se usan habitualmente e importa los espacios de nombres `System` y `Microsoft.VisualBasic`.  
  
> [!NOTE]
> Siempre se hace referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
> [!NOTE]
> La opción `-nostdlib` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  

 El siguiente código compila `T2.vb` sin hacer referencia a las bibliotecas estándar. La constante de compilación condicional `_MYTYPE` se debe establecer en la cadena "Empty" para quitar el objeto `My`.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [-noconfig](noconfig.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Personalización de los objetos que están disponibles en My](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
