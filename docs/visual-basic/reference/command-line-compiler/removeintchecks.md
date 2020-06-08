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
ms.openlocfilehash: ec4722cb7088819dae95ca1b7cbc1469d957a7aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400479"
---
# <a name="-removeintchecks"></a>-removeintchecks
Activa o desactiva la comprobación de desbordamiento para operaciones con enteros.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. La opción `-removeintchecks-` hace que el compilador compruebe todos los cálculos de enteros en busca de errores de desbordamiento. De manera predeterminada, es `-removeintchecks-`.<br /><br /> Si especifica `-removeintchecks` o `-removeintchecks+`, se impide la comprobación de errores y puede realizar cálculos de enteros más rápido. Pero si se cancela la comprobación de errores y si se desbordan las capacidades de tipo de datos, es posible que se almacenen resultados incorrectos sin que se genere ningún error.|  
  
|Para definir -removeintchecks en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en el botón **Avanzada** .<br />4.  Modifique el valor del cuadro **Quitar comprobaciones de desbordamiento con enteros**.|  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `Test.vb` y desactiva la comprobación de errores de desbordamiento con enteros.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
