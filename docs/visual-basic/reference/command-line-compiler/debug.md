---
title: /Debug (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
caps.latest.revision: 18
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
ms.openlocfilehash: 7384e69f066022e861a4277f418df3f4d094c3be
ms.lasthandoff: 03/13/2017

---
# <a name="debug-visual-basic"></a>/debug (Visual Basic)
Hace que el compilador genere información de depuración y colocarla en los archivos de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/debug[+ | -]  
' -or-  
/debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. Especificar `+` o `/debug` hace que el compilador genere información de depuración y colocarlo en un archivo. pdb. Especificar `-` tiene el mismo efecto que si no se especifica `/debug`.|  
|`full` &#124; `pdbonly`|Opcional. Especifica el tipo de información de depuración generado por el compilador. Si no se especifica `/debug:pdbonly`, el valor predeterminado es `full`, lo que permite adjuntar un depurador al programa en ejecución. El `pdbonly` argumento permite depurar el código fuente cuando se inicia el programa en el depurador, pero sólo se mostrará código de lenguaje de ensamblado cuando el programa que se ejecuta está asociado al depurador.|  
  
## <a name="remarks"></a>Comentarios  
 Utilice esta opción para crear versiones de depuración. Si no se especifica `/debug`, `/debug+`, o `/debug:full`, no se podrá depurar el archivo de salida del programa.  
  
 De forma predeterminada, no se genera información de depuración (`/debug-`). Para emitir información de depuración, especifique `/debug` o `/debug+`.  
  
 Para obtener información sobre cómo configurar el rendimiento de depuración de una aplicación, consulte [Facilitar la depuración de una imagen](http://msdn.microsoft.com/library/7d90ea7a-150f-4f97-98a7-f9c26541b9a3).  
  
|Para establecer /debug en Visual Studio de entorno de desarrollo integrado|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en el **compilar** ficha.<br />3.  Haga clic en **opciones de compilación avanzadas**.<br />4.  Modifique el valor en el **generar información de depuración** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se incluye información de depuración en el archivo de salida `App.exe`.  
  
```  
vbc /debug /out:app.exe test.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
