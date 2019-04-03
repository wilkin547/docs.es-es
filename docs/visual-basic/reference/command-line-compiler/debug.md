---
title: /debug (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 9bf7170cee31f92481b15fb1227f21895cd3734d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827983"
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)
Hace que el compilador genere información de depuración y colocarla en los archivos de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-debug[+ | -]  
' -or-  
-debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|de esquema JSON|  
|---|---|  
|`+` &#124; `-`|Opcional. Especificar `+` o `/debug` hace que el compilador genere información de depuración y lo coloca en un archivo. pdb. Especificar `-` tiene el mismo efecto que si no se especifica `/debug`.|  
|`full` &#124; `pdbonly`|Opcional. Especifica el tipo de información de depuración generado por el compilador. Si no especifica `/debug:pdbonly`, el valor predeterminado es `full`, lo que permite adjuntar un depurador al programa en ejecución. El `pdbonly` argumento permite depurar el código fuente cuando se inicia el programa en el depurador, pero muestra código de lenguaje ensamblador solo cuando el programa que se ejecuta está asociado al depurador.|  
  
## <a name="remarks"></a>Comentarios  
 Use esta opción para crear versiones de depuración. Si no especifica `/debug`, `/debug+`, o `/debug:full`, podrá depurar el archivo de salida del programa.  
  
 De forma predeterminada, no se emite información de depuración (`/debug-`). Para emitir información de depuración, especifique `/debug` o `/debug+`.  
  
 Para obtener información sobre cómo configurar el rendimiento de depuración de una aplicación, consulte [Facilitar la depuración de una imagen](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
|Para establecer - depurar en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Opciones de compilación avanzadas**.<br />4.  Modifique el valor en el **generar información de depuración** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente incluye información de depuración en el archivo de salida `App.exe`.  
  
```  
vbc -debug -out:app.exe test.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
