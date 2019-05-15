---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 1c3c70b24de5163ca004b41a21017205a19d9730
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583376"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Hace que el compilador no hacen referencia automáticamente a las bibliotecas estándar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>Comentarios  
 El `-nostdlib` opción quita la referencia automática al ensamblado System.dll y evita que el compilador leer el archivo Vbc.rsp. El archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe, hace referencia a los ensamblados de .NET Framework usados e importa el `System` y `Microsoft.VisualBasic` espacios de nombres.  
  
> [!NOTE]
>  Los ensamblados de Mscorlib.dll y Microsoft.VisualBasic.dll siempre se hace referencia.  
  
> [!NOTE]
>  El `-nostdlib` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` sin hacer referencia a las bibliotecas estándar. Debe establecer el `_MYTYPE` constante de compilación condicional en la cadena "Empty" para quitar el `My` objeto.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
