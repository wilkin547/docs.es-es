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
ms.openlocfilehash: 25368d23c398fb3674d5c2d75d4997f917a1c3d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937353"
---
# <a name="-sdkpath"></a>-sdkpath
Especifica la ubicación de mscorlib. dll y Microsoft. VisualBasic. dll.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argumentos  
 `path`  
 Directorio que contiene las versiones de mscorlib. dll y Microsoft. VisualBasic. dll que se van a usar para la compilación. Esta ruta de acceso no se comprueba hasta que se carga. Escriba el nombre del directorio entre comillas ("") si contiene un espacio.  
  
## <a name="remarks"></a>Comentarios  
 Esta opción indica al compilador de Visual Basic que cargue los archivos mscorlib. dll y Microsoft. VisualBasic. dll desde una ubicación no predeterminada. La `-sdkpath` opción se ha diseñado para usarse con [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). El .NET Compact Framework usa versiones diferentes de estas bibliotecas de compatibilidad para evitar el uso de tipos y características de lenguaje que no se encuentran en los dispositivos.  
  
> [!NOTE]
> La `-sdkpath` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos. La `-sdkpath` opción se establece cuando se carga un proyecto de dispositivo Visual Basic.  
  
 Puede especificar que el compilador debe compilar sin una referencia a la biblioteca en tiempo `-vbruntime` de ejecución de Visual Basic mediante la opción del compilador. Para obtener más información, vea [-vbruntime (](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código se compila `Myfile.vb` con el .NET Compact Framework, con las versiones de mscorlib. dll y Microsoft. VisualBasic. dll que se encuentran en el directorio de instalación predeterminado del .NET Compact Framework en la unidad C. Normalmente, se usaría la versión más reciente de la .NET Compact Framework.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
