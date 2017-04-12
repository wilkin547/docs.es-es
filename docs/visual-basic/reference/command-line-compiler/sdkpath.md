---
title: /sdkpath | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
dev_langs:
- VB
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3584daa49bca699f022a1afd34e3d450b8442060
ms.lasthandoff: 03/13/2017

---
# <a name="sdkpath"></a>/sdkpath
Especifica la ubicación de Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a>Argumentos  
 `path`  
 El directorio que contiene las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll a utilizar para la compilación. Esta ruta de acceso no se comprueba hasta que se carga. Escriba el nombre del directorio entre comillas ("") si contiene espacios.  
  
## <a name="remarks"></a>Comentarios  
 Esta opción indica el [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador que cargue los archivos Mscorlib.dll y Microsoft.VisualBasic.dll desde una ubicación no predeterminada. El `/sdkpath` opción se diseñó para utilizarse con [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). El [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] utiliza versiones diferentes de estas bibliotecas de compatibilidad para evitar el uso de tipos y características de lenguaje que no se encuentran en los dispositivos.  
  
> [!NOTE]
>  El `/sdkpath` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos. El `/sdkpath` opción se establece cuando un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] se carga un proyecto de dispositivo.  
  
 Puede especificar que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic utilizando el `/vbruntime` opción del compilador. Para obtener más información, consulte [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `Myfile.vb` con el [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], utilizando las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll que se encuentra en el directorio de instalación predeterminado de la [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] en la unidad C:. Normalmente, utilizaría la versión más reciente de la [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)   
 [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
