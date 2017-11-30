---
title: /nostdlib (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9d76563a5b3d439495899e07ce2df59c0acd75e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nostdlib-visual-basic"></a>/nostdlib (Visual Basic)
Hace que el compilador no automáticamente hacen referencia a las bibliotecas estándar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a>Comentarios  
 El `/nostdlib` opción quita la referencia automática al ensamblado System.dll e impide que el compilador pueda leer el archivo Vbc.rsp. El archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe: hace referencia a utilizados habitualmente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados e importaciones el `System` y `Microsoft.VisualBasic` los espacios de nombres.  
  
> [!NOTE]
>  Siempre hacen referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
> [!NOTE]
>  El `/nostdlib` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` sin hacer referencia a las bibliotecas estándar. Debe establecer el `_MYTYPE` constante de compilación condicional en la cadena "Vacío" Si desea quitar el `My` objeto.  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
