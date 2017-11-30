---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e765f0007eea8e196b1a1b3b55b969c5b074b52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="removeintchecks"></a>/removeintchecks
Activa el error de desbordamiento para operaciones con enteros o desactivar la comprobación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. El `/removeintchecks-` opción hace que el compilador compruebe todos los cálculos de enteros para los errores de desbordamiento. De manera predeterminada, es `/removeintchecks-`.<br /><br /> Especificar `/removeintchecks` o `/removeintchecks+` evita la comprobación de errores y realizar cálculos de enteros más rápidos. Sin embargo, sin comprobación de errores, y si se sobrepasan las capacidades de tipo de datos, se pueden almacenar resultados incorrectos cuando se genera un error.|  
  
|Para establecer /removeintchecks en Visual Studio integra el entorno de desarrollo|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en el botón **Avanzada** .<br />4.  Modificar el valor de la **Quitar comprobaciones de desbordamiento con enteros** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `Test.vb` y desactiva la comprobación de errores de desbordamiento con enteros.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
