---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 819505df2e7d5f93302f9ed601de856e36ed7124
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005417"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Hace que el compilador no haga referencia automáticamente a las bibliotecas estándar.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>Comentarios  
 La opción `-nostdlib` quita la referencia automática al ensamblado System. dll y evita que el compilador Lea el archivo Vbc. rsp. El archivo Vbc. RSP, que se encuentra en el mismo directorio que el archivo Vbc. exe, hace referencia a los ensamblados .NET Framework utilizados con frecuencia e importa los espacios de nombres `System` y `Microsoft.VisualBasic`.  
  
> [!NOTE]
> Siempre se hace referencia a los ensamblados mscorlib. dll y Microsoft. VisualBasic. dll.  
  
> [!NOTE]
> La opción `-nostdlib` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `T2.vb` sin hacer referencia a las bibliotecas estándar. Debe establecer la constante de compilación condicional de `_MYTYPE` en la cadena "Empty" para quitar el objeto `My`.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
