---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005229"
---
# <a name="-removeintchecks"></a>-removeintchecks
Activa o desactiva la comprobación de errores de desbordamiento para operaciones de enteros.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. La opción `-removeintchecks-` hace que el compilador Compruebe todos los cálculos de enteros en busca de errores de desbordamiento. De manera predeterminada, es `-removeintchecks-`.<br /><br /> Si se especifica `-removeintchecks` o `-removeintchecks+`, se impide la comprobación de errores y se pueden realizar cálculos de enteros con mayor rapidez. Sin embargo, sin la comprobación de errores y si las capacidades del tipo de datos se desbordan, los resultados incorrectos pueden almacenarse sin producir un error.|  
  
|Para Set-removeintchecks (en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en el botón **Avanzada** .<br />4.  Modifique el valor de la casilla **quitar comprobaciones de desbordamiento de enteros** .|  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se compila `Test.vb` y se desactiva la comprobación de errores de desbordamiento de enteros.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
