---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005398"
---
# <a name="-nowarn"></a>-nowarn
Suprime la capacidad del compilador para generar advertencias.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`numberList`|Opcional. Lista delimitada por comas de los números de ID. de advertencia que el compilador debe suprimir. Si no se especifican los identificadores de advertencia, se suprimen todas las advertencias.|  
  
## <a name="remarks"></a>Comentarios  
 La opción `-nowarn` hace que el compilador no genere advertencias. Para suprimir una advertencia individual, proporcione el identificador de advertencia a la opción `-nowarn` que va detrás del signo de dos puntos. Separe varios números de advertencia con comas.  
  
 Solo tiene que especificar la parte numérica del identificador de advertencia. Por ejemplo, si desea suprimir BC42024, la advertencia para las variables locales no utilizadas, especifique `-nowarn:42024`.  
  
 Para obtener más información sobre los números de identificador de advertencia, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Para establecer-nowarn en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Active la casilla **deshabilitar todas las advertencias** para deshabilitar todas las advertencias.<br />     o bien<br />     Para deshabilitar una advertencia concreta, haga clic en **ninguno** en la lista desplegable que se muestra junto a la advertencia.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y no muestra ninguna advertencia.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se compila `T2.vb` y no se muestran las advertencias de las variables locales no utilizadas (42024).  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
