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
ms.openlocfilehash: c086a031d5cef4563a6769e7683dcb1110b8fe49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788770"
---
# <a name="-removeintchecks"></a>-removeintchecks
Activa el error de desbordamiento para operaciones con enteros o desactivar la comprobación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. El `-removeintchecks-` opción hace que el compilador compruebe todos los cálculos de enteros para los errores de desbordamiento. De manera predeterminada, es `-removeintchecks-`.<br /><br /> Especificar `-removeintchecks` o `-removeintchecks+` evita la comprobación de errores y realizar los cálculos de enteros más rápidos. Sin embargo, sin comprobación de errores, y si se sobrepasan las capacidades de tipo de datos, se podrán almacenar resultados incorrectos sin provocar un error.|  
  
|Para establecer - removeintchecks en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en el botón **Avanzada** .<br />4.  Modificar el valor de la **Quitar comprobaciones de desbordamiento con enteros** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `Test.vb` y desactiva la comprobación de errores de desbordamiento con enteros.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
