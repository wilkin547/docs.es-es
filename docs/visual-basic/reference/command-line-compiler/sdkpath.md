---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004694"
---
# <a name="-sdkpath"></a>-sdkpath
Especifica la ubicación de mscorlib.dll y Microsoft.VisualBasic.dll.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argumentos  
 `path`  
 Directorio que contiene las versiones de mscorlib.dll y Microsoft.VisualBasic.dll que se van a usar para la compilación. Esta ruta de acceso no se comprueba hasta que se carga. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").  
  
## <a name="remarks"></a>Comentarios  
 Esta opción indica al compilador de Visual Basic que cargue los archivos mscorlib.dll y Microsoft.VisualBasic.dll desde una ubicación no predeterminada. La opción `-sdkpath` se ha diseñado para usarse con [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). En .NET Compact Framework se usan otras versiones de estas bibliotecas de compatibilidad para evitar el uso de tipos y características del lenguaje que no se encuentran en los dispositivos.  
  
> [!NOTE]
> La opción `-sdkpath` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos. La opción `-sdkpath` se establece cuando se carga un proyecto de dispositivo de Visual Basic.  
  
 Puede especificar que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic mediante la opción del compilador `-vbruntime`. Para obtener más información, vea [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `Myfile.vb` con .NET Compact Framework, mediante las versiones de mscorlib.dll y Microsoft.VisualBasic.dll que se encuentran en el directorio de instalación predeterminado de .NET Compact Framework en la unidad C. Normalmente, se usaría la versión más reciente de .NET Compact Framework.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
