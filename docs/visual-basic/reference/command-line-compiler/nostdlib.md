---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 19a70e500f6b75fd003bdb798f242cddb3926935
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964360"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Hace que el compilador no haga referencia automáticamente a las bibliotecas estándar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>Comentarios  
 La `-nostdlib` opción quita la referencia automática al ensamblado System. dll y evita que el compilador Lea el archivo Vbc. rsp. El archivo Vbc. RSP, que se encuentra en el mismo directorio que el archivo Vbc. exe, hace referencia a los ensamblados de .NET Framework utilizados `System` habitualmente `Microsoft.VisualBasic` e importa los espacios de nombres y.  
  
> [!NOTE]
> Siempre se hace referencia a los ensamblados mscorlib. dll y Microsoft. VisualBasic. dll.  
  
> [!NOTE]
> La `-nostdlib` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente se compila `T2.vb` sin hacer referencia a las bibliotecas estándar. Debe establecer la `_MYTYPE` constante de compilación condicional en la cadena "Empty" para quitar el `My` objeto.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
