---
title: /sdkpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 876922385124db3e8db12c93c75194da83d2526c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sdkpath"></a>/sdkpath
Especifica la ubicación de Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a>Argumentos  
 `path`  
 El directorio que contiene las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll a utilizar para la compilación. Esta ruta de acceso no se comprueba hasta que se cargue. Escriba el nombre de directorio entre comillas ("") si contiene un espacio.  
  
## <a name="remarks"></a>Comentarios  
 Esta opción indica el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador que cargue los archivos Mscorlib.dll y Microsoft.VisualBasic.dll desde una ubicación no predeterminada. El `/sdkpath` opción se ha diseñado para utilizarse con [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). El [!INCLUDE[Compact](~/includes/compact-md.md)] utiliza diferentes versiones de estas bibliotecas de compatibilidad para evitar el uso de tipos y características del lenguaje no se encuentran en los dispositivos.  
  
> [!NOTE]
>  El `/sdkpath` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos. El `/sdkpath` opción se establece cuando un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] se carga el proyecto de dispositivo.  
  
 Puede especificar que el compilador debe compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic mediante el uso de la `/vbruntime` opción del compilador. Para obtener más información, consulte [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `Myfile.vb` con el [!INCLUDE[Compact](~/includes/compact-md.md)], utiliza las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll se encuentra en el directorio de instalación predeterminado de la [!INCLUDE[Compact](~/includes/compact-md.md)] en la unidad C:. Normalmente, se usa la versión más reciente de la [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
