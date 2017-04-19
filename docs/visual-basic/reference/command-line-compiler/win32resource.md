---
title: /win32resource | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
dev_langs:
- VB
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
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
ms.openlocfilehash: 37902590d5a05d7fdb2a521f3c3de2ad88c2c502
ms.lasthandoff: 03/13/2017

---
# <a name="win32resource"></a>/win32resource
Inserta un archivo de recursos de Win32 en el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El nombre del archivo de recursos para agregar al archivo de salida. Encierre el nombre de archivo entre comillas ("") si contiene espacios.  
  
## <a name="remarks"></a>Comentarios  
 Puede crear un archivo de recursos de Win32 con el compilador de recursos de Microsoft Windows (RC).  
  
 Un recurso de Win32 puede contener la versión o información de mapa de bits (icono) que ayuda a identificar la aplicación en **Explorador de archivos**. Si no se especifica `/win32resource`, el compilador genera información de versión basada en la versión del ensamblado. El `/win32resource` y `/win32icon` opciones son mutuamente excluyentes.  
  
 Consulte [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) para hacer referencia a un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] archivo de recursos, o [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) para adjuntar un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] archivo de recursos.  
  
> [!NOTE]
>  El `/win32resource` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y adjunta un archivo de recursos Win32 `Rf.res`:  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
