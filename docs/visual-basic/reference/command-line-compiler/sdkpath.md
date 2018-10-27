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
ms.openlocfilehash: bf665082f079901ec45122ce7797090b7519fafe
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50046804"
---
# <a name="-sdkpath"></a>-sdkpath
Especifica la ubicación de mscorlib.dll y Microsoft.VisualBasic.dll.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argumentos  
 `path`  
 El directorio que contiene las versiones de mscorlib.dll y Microsoft.VisualBasic.dll a utilizar para la compilación. No se comprueba esta ruta de acceso hasta que se carga. Escriba el nombre de directorio entre comillas ("") si contiene un espacio.  
  
## <a name="remarks"></a>Comentarios  
 Esta opción indica al compilador de Visual Basic para cargar el archivo mscorlib.dll y Microsoft.VisualBasic.dll archivos desde una ubicación no predeterminada. El `-sdkpath` opción se ha diseñado para usarse con [- netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). El [!INCLUDE[Compact](~/includes/compact-md.md)] utiliza diferentes versiones de estas bibliotecas de compatibilidad para evitar el uso de tipos y características de lenguaje no se encuentran en los dispositivos.  
  
> [!NOTE]
>  El `-sdkpath` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos. El `-sdkpath` opción se establece cuando se carga un proyecto de dispositivo de Visual Basic.  
  
 Puede especificar que el compilador debe compilar sin referencia alguna a la biblioteca en tiempo de ejecución de Visual Basic utilizando la `-vbruntime` opción del compilador. Para obtener más información, consulte [- vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `Myfile.vb` con el [!INCLUDE[Compact](~/includes/compact-md.md)], utilizando las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll se encuentra en el directorio de instalación predeterminada de la [!INCLUDE[Compact](~/includes/compact-md.md)] en la unidad C:. Normalmente, se usa la versión más reciente de la [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
