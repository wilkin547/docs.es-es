---
title: /removeintchecks | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
dev_langs:
- VB
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
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
ms.openlocfilehash: 8e50200b8755ccc6b1c173024856955f5075b67e
ms.lasthandoff: 03/13/2017

---
# <a name="removeintchecks"></a>/removeintchecks
Activa para operaciones con enteros o desactivar la comprobación de errores de desbordamiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. El `/removeintchecks-` opción hace que el compilador compruebe todos los cálculos de enteros para los errores de desbordamiento. De manera predeterminada, es `/removeintchecks-`.<br /><br /> Especificar `/removeintchecks` o `/removeintchecks+` evita la comprobación de errores y realizar cálculos de enteros más rápidos. Sin embargo, sin la comprobación de errores, y si se sobrepasan las capacidades de tipo de datos, se pueden almacenar resultados incorrectos cuando se genera un error.|  
  
|Para establecer /removeintchecks en Visual Studio de entorno de desarrollo integrado|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en el **compilar** ficha.<br />3.  Haga clic en el botón **Avanzada** .<br />4.  Modificar el valor de la **Quitar comprobaciones de desbordamiento con enteros** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `Test.vb` y desactiva la comprobación de errores de desbordamiento de enteros.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
