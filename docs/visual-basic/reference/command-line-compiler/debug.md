---
title: /debug (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7430a3ac85a86ed5528af9ea830da530208749eb
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)
Hace que el compilador generar información de depuración y almacenarla en los archivos de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-debug[+ | -]  
' -or-  
-debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|de esquema JSON|  
|---|---|  
|`+` &#124; `-`|Opcional. Especificar `+` o `/debug` hace que el compilador generar información de depuración y almacenarla en un archivo .pdb. Especificar `-` tiene el mismo efecto que si no se especifica `/debug`.|  
|`full` &#124; `pdbonly`|Opcional. Especifica el tipo de información de depuración generado por el compilador. Si no se especifica `/debug:pdbonly`, el valor predeterminado es `full`, lo que permite adjuntar un depurador al programa en ejecución. El `pdbonly` argumento permite depurar el código fuente cuando se inicia el programa en el depurador, pero se mostrará el código de lenguaje de ensamblado solo cuando el programa en ejecución se adjunta al depurador.|  
  
## <a name="remarks"></a>Comentarios  
 Use esta opción para crear versiones de depuración. Si no se especifica `/debug`, `/debug+`, o `/debug:full`, no se podrá depurar el archivo de salida del programa.  
  
 De forma predeterminada, no se emite información de depuración (`/debug-`). Para emitir información de depuración, especifique `/debug` o `/debug+`.  
  
 Para obtener información sobre cómo configurar el rendimiento de depuración de una aplicación, consulte [Facilitar la depuración de una imagen](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
|Para establecer - depurar en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Opciones de compilación avanzadas**.<br />4.  Modifique el valor en el **generar información de depuración** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se incluye información de depuración en el archivo de salida `App.exe`.  
  
```  
vbc -debug -out:app.exe test.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
