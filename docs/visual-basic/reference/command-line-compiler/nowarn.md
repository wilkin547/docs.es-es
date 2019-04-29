---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788991"
---
# <a name="-nowarn"></a>-nowarn
Suprime la capacidad del compilador para generar advertencias.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`numberList`|Opcional. Lista delimitada por comas de los números de Id. de advertencia que el compilador debe suprimir. Si no se especifican los identificadores de advertencia, se suprimen todas las advertencias.|  
  
## <a name="remarks"></a>Comentarios  
 El `-nowarn` opción hace que el compilador no genere advertencias. Para suprimir una advertencia individual, proporcione el identificador de advertencia para el `-nowarn` opción siguiendo los dos puntos. Separe varios números de advertencia con comas.  
  
 Deberá especificar solo la parte numérica del identificador de advertencia. Por ejemplo, especifique si desea suprimir BC42024, la advertencia para las variables locales no utilizadas, `-nowarn:42024`.  
  
 Para obtener más información sobre los números de Id. de advertencia, consulte [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Para establecer - nowarn en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Seleccione el **deshabilitar todas las advertencias** casilla para deshabilitar todas las advertencias.<br />     o bien<br />     Para deshabilitar una advertencia concreta, haga clic en **ninguno** en la lista desplegable junto a la advertencia.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y no muestra las advertencias.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y no muestra las advertencias para las variables locales no utilizadas (42024).  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
